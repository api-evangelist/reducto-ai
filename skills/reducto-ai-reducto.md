---
name: reducto
description: Use when processing documents (PDFs, images, spreadsheets, DOCX, and 30+ formats) to extract structured data, parse content into chunks, classify documents, split into sections, or fill forms. Agents should reach for Reducto when building document intake pipelines, extracting fields from invoices/contracts/forms, preparing documents for RAG, or automating document workflows.
metadata:
    mintlify-proj: reducto
    version: "1.0"
---

# Reducto Skill Reference

## Product Summary

Reducto is the agentic document platform for processing PDFs, images, spreadsheets, DOCX, and 30+ file types. It provides five core capabilities: **Parse** (convert to structured JSON with text, tables, figures), **Extract** (pull specific fields using a schema), **Split** (divide into sections), **Classify** (categorize document type), and **Edit** (fill forms, modify documents).

**Base URL:** `https://platform.reducto.ai`  
**Auth:** `Authorization: Bearer $REDUCTO_API_KEY` (set env var `REDUCTO_API_KEY`)  
**SDKs:** Python (`pip install reductoai`), Node.js (`npm install reductoai`), Go (`go get github.com/reductoai/reducto-go-sdk`)  
**CLI:** `pip install reducto-cli` → `reducto login` → `reducto parse ./document.pdf`  
**MCP:** `uvx mcp-server-reducto --login` (for Claude Code, Cursor, Codex, VS Code)  
**Primary docs:** https://docs.reducto.ai

---

## When to Use

Reach for Reducto when:

- **Parsing documents:** Convert PDFs, images, or spreadsheets into structured markdown with text, tables, figures, and layout preserved. Use for RAG pipelines, document viewers, or feeding content to LLMs.
- **Extracting fields:** Pull specific data (invoice totals, contract dates, form fields) into JSON using a schema. Extract runs Parse internally, so it only returns what Parse sees.
- **Classifying documents:** Route documents by type (invoice vs. contract vs. receipt) before processing. Classify is synchronous and costs only 0.5 credits per page of context.
- **Splitting documents:** Divide long documents into named sections (Executive Summary, Financial Statements, Risk Factors) by page range.
- **Filling forms:** Programmatically fill PDF forms or modify DOCX documents with natural language instructions.
- **Building workflows:** Chain Parse → Extract → Split into reusable pipelines deployed from Studio with a single `pipeline_id`.
- **Batch processing:** Process many documents in parallel with async endpoints and webhooks.

Do **not** use Reducto for: authentication, user management, or non-document tasks.

---

## Quick Reference

### Core Endpoints

| Endpoint | Method | Input | Output | Use when |
|----------|--------|-------|--------|----------|
| `/parse` | POST | file_id, URL, or `jobid://` | Chunks with text, tables, figures, bounding boxes | Converting documents to structured content |
| `/extract` | POST | file_id, URL, `jobid://`, or array of job IDs | JSON matching your schema | Pulling specific fields |
| `/split` | POST | file_id, URL, or `jobid://` | Section names and page ranges | Dividing documents into sections |
| `/classify` | POST | file_id or URL | Category name | Routing documents by type |
| `/edit` | POST | file_id or URL | Download URL for edited document | Filling forms or modifying documents |
| `/upload` | POST (multipart) | Local file | `reducto://` file_id | Uploading local files before processing |

### Input Formats

All endpoints accept one of these input formats:

- **Upload response:** `reducto://abc123def456` (from `/upload`)
- **Public URL:** `https://example.com/document.pdf`
- **Presigned URL:** S3, GCS, or Azure Blob presigned URLs
- **Previous job:** `jobid://7600c8c5-a52f-49d2-8a7d-d75d1b51e141` (reuse parsed content)
- **Job array:** `["jobid://job-1", "jobid://job-2"]` (combine multiple documents)

### SDK Naming

| SDK | Property names | Install | Notes |
|-----|---------------|---------|-------|
| Python | snake_case | `pip install reductoai` | Auto-reads `REDUCTO_API_KEY` |
| Node.js | snake_case | `npm install reductoai` | All methods return promises |
| Go | PascalCase | `go get github.com/reductoai/reducto-go-sdk` | Wrap values with `reducto.F()` |
| REST | snake_case in JSON | - | Bearer token in Authorization header |

### CLI Commands

```bash
reducto parse ./document.pdf              # Parse to <filename>.parse.md
reducto parse ./docs                      # Batch parse directory
reducto extract ./invoice.pdf -s schema.json  # Extract with schema
reducto edit ./form.pdf -i "Fill Name: John"  # Edit document
```

### MCP Tools (for agents)

```text
parse_document(document_url="...", table_output_format="html", page_range="1-5")
extract_data(document_url="...", schema={...}, citations=True)
split_document(document_url="...", categories=[...])
classify_document(document_url="...", categories=[...])
edit_document(document_url="...", edit_instructions="...")
upload_file("./document.pdf" or "https://example.com/doc.pdf")
get_job(job_id="...")
```

---

## Decision Guidance

### When to Use Parse vs Extract

| Situation | Use | Why |
|-----------|-----|-----|
| Need all content (text, tables, figures) for RAG or LLM context | Parse | Returns everything with layout and structure |
| Need specific fields (invoice total, contract date) | Extract | Returns only what you ask for, typed and structured |
| Debugging extraction issues | Parse first | Extract can only return what Parse sees. If Parse doesn't find it, Extract can't extract it. |

### When to Use Sync vs Async

| Situation | Use | Why |
|-----------|-----|-----|
| Single document, <5 pages, need result immediately | Sync (`/parse`, `/extract`) | Faster, simpler, no polling |
| Large document (>50 pages) or batch processing | Async (`/parse_async`, `/extract_async`) | Avoids timeouts, supports webhooks |
| High-volume production workload | Async + Svix webhooks | Reliable delivery, retry logic, dashboard |
| Prototyping or internal integration | Async + direct webhooks | Simpler setup, no external service |

### When to Use Chunking Modes

| Mode | Use | Output |
|------|-----|--------|
| `disabled` (default) | Single document for LLM context | One chunk for entire document |
| `variable` | RAG pipelines, semantic search | Chunks at section/table/figure boundaries |
| `page` | Page-by-page processing | One chunk per page |
| `section` | Split at headers | Chunks at section headers |

### When to Use Table Formats

| Format | Use | Best for |
|--------|-----|----------|
| `dynamic` (default) | Most workflows | Auto-selects HTML or Markdown |
| `html` | Complex tables with merged cells | Preserves structure |
| `md` | Simple tables, Markdown workflows | Clean, readable |
| `json` | Programmatic cell access | Structured data extraction |
| `csv` | Export to spreadsheets | Tabular data |

### When to Use Agentic Processing

| Situation | Use | Cost |
|-----------|-----|------|
| r-1 handles it well (most cases) | No agentic mode | Standard |
| Custom prompt needed (domain-specific notation, special formatting) | Agentic with custom prompt | +latency |
| Advanced chart extraction (structured series data) | Agentic + `advanced_chart_agent` | +latency, +cost |
| General accuracy boost (legacy Parse only) | Agentic without prompt | +latency (r-1 ignores this) |

---

## Workflow

### Typical Parse → Extract Flow

1. **Understand the document:** What type is it? What fields do you need? Is it a single page or 100+ pages?
2. **Check existing content:** If you've already parsed this document, reuse the `job_id` with `jobid://` to skip re-parsing.
3. **Upload if needed:** For local files, call `/upload` first to get a `reducto://` file_id.
4. **Parse:** Call `/parse` with the file_id or URL. Check `result.type`: if `"url"`, fetch from `result.url`.
5. **Inspect in Studio:** Open the `studio_link` to visually verify the parse output.
6. **Extract:** If you need specific fields, call `/extract` with your JSON schema. Pass `jobid://` from the parse result to skip re-parsing.
7. **Verify:** Check that extracted values match what you see in the Parse output. If a value is missing, adjust Parse configuration (e.g., enable agentic mode for tables, change table format to HTML).
8. **Deploy:** For production, create a pipeline in Studio and deploy with a `pipeline_id` for reusable workflows.

### Typical Classify → Extract Flow

1. **Classify:** Call `/classify` with your document and a list of categories + criteria.
2. **Route:** Based on the category, choose the right extraction schema.
3. **Extract:** Call `/extract` with the category-specific schema.

### Batch Processing with Async

1. **Submit jobs:** Call `/parse_async` or `/extract_async` for each document. Get back `job_id` immediately.
2. **Configure webhooks:** Include `webhook` config with Svix or direct URL.
3. **Wait for delivery:** Reducto sends results to your webhook when complete.
4. **Poll if needed:** If not using webhooks, call `/job/{job_id}` to check status.

---

## Common Gotchas

- **Extract can only return what Parse sees.** If a value doesn't appear in the Parse output, no schema tweaking will extract it. Always verify the data exists in Parse first.
- **Large documents return `result.type: "url"`.** Don't assume content is inline. Check `result.type` and fetch from `result.url` if needed.
- **Default chunking is `disabled`.** The entire document becomes one chunk. For RAG, set `retrieval.chunking.chunk_mode: "variable"`.
- **Agentic mode adds latency.** Don't enable it as a general accuracy boost. Use it only for custom prompts or specialized augmentation.
- **Citations and chunking are mutually exclusive.** If you enable `settings.citations.enabled`, chunking is automatically disabled.
- **Array extraction requires at least one top-level array in schema.** If your schema has no arrays, the endpoint returns an error.
- **Edit uses `document_url`, not `input`.** Unlike other endpoints, Edit's input parameter is named `document_url`.
- **Classify is synchronous only.** No async variant. It costs 0.5 credits per page of context (first 5 pages by default).
- **Password-protected PDFs need the password.** Pass `settings.document_password` to unlock them.
- **File size limits:** 100MB direct upload, 5GB via presigned URL.
- **Deprecated patterns:** `array_extract` is deprecated; use `deep_extract` instead for iterative refinement.
- **r-1 is the default for new pipelines.** Existing pipelines can continue using legacy Parse or migrate. r-1 handles text, tables, figures, layout, and formatting in one pass.

---

## Verification Checklist

Before submitting work with Reducto:

- [ ] API key is set as `REDUCTO_API_KEY` environment variable or passed explicitly
- [ ] Document is uploaded or a public/presigned URL is provided
- [ ] For Extract, verified that the data exists in the Parse output (check `studio_link`)
- [ ] Response `result.type` is checked; if `"url"`, content is fetched from `result.url`
- [ ] For large documents, async endpoints are used instead of sync
- [ ] Webhooks are configured for production batch jobs (Svix preferred over direct)
- [ ] Table format is appropriate for the document type (HTML for complex tables, Markdown for simple)
- [ ] Chunking mode is set correctly for the use case (variable for RAG, disabled for single-document LLM context)
- [ ] Agentic mode is only enabled when a custom prompt or specialized augmentation is needed
- [ ] For Edit, `document_url` parameter is used (not `input`)
- [ ] For Classify, at least two categories are provided
- [ ] Error handling wraps API calls in try/catch (Python) or try/except (JavaScript)
- [ ] Rate limits and throttling are understood (check `/reference/rate-limits`)
- [ ] Results are persisted if needed (`settings.persist_results: true` for indefinite retention)

---

## Resources

**Comprehensive navigation:** https://docs.reducto.ai/llms.txt

**Critical documentation:**
- [Agent Guide](/agent-guide) — Dense reference for all endpoints, parameters, and response shapes
- [Parse Overview](/parse/overview) — Full Parse configuration, chunking, table formats, agentic modes
- [Extract Overview](/extract/overview) — Schema design, citations, array extraction, deep extract

**Quick starts:**
- [API Quickstart](/quickstart) — 5-minute parse example in Python, Node.js, Go, cURL
- [CLI Quickstart](/cli) — Terminal-first workflow for local files
- [MCP Server](/mcp-server) — Agent tool calling for Claude Code, Cursor, Codex, VS Code

**Workflows:**
- [Async Processing](/workflows/async-overview) — Webhooks, polling, batch processing
- [Pipeline Basics](/workflows/pipeline-basics) — Composing multi-step workflows in Studio
- [Cookbooks](/cookbooks/overview) — End-to-end examples (invoice extraction, form filling, RAG)

**Reference:**
- [Error Codes](/reference/error-codes) — Troubleshooting HTTP status codes
- [Rate Limits](/reference/rate-limits) — Request quotas and concurrency
- [Credit Usage](/reference/credit-usage) — How credits are calculated per endpoint

---

> For additional documentation and navigation, see: https://docs.reducto.ai/llms.txt