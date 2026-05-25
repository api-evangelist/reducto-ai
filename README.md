# Reducto (reducto-ai)
Reducto is an AI document-parsing platform that turns unstructured PDFs, images, spreadsheets, slides, and forms into LLM-ready layout, structured data, and form completions. The API exposes Parse, Extract, Split, Edit, Classify, and Pipeline endpoints — each with sync and async variants — plus an Upload API, Webhooks API, and Jobs API. Used by Scale AI, Vanta, Harvey, Medallion, Toast, JLL, Vise, Newfront, and Legora to power document AI in finance, healthcare, insurance, legal, government, and logistics.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/reducto-ai/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

 - Document AI, Parse, Extract, Split, Edit, Classify, OCR, PDF, Forms, LLM, Structured Data

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### Reducto Parse API
Parse documents (PDFs, images, spreadsheets, slides, text files) and capture layout, structure, OCR text, tables, figures, equations, lists, and LLM-optimized chunks. Supports agentic OCR with error correction, intelligent ordering, figure summarization, embedding optimization, automatic page rotation, multilingual processing across 100+ languages, and synchronous or asynchronous execution.

**Human URL:** [https://docs.reducto.ai/parse/overview](https://docs.reducto.ai/parse/overview)

- [Documentation — Parse Overview](https://docs.reducto.ai/parse/overview)
- [API Reference — Parse](https://docs.reducto.ai/api-reference/parse)
- [API Reference — Async Parse](https://docs.reducto.ai/api-reference/async-parse)
- [Documentation — Response Format](https://docs.reducto.ai/parse/response-format)
- [Documentation — Best Practices](https://docs.reducto.ai/parse/best-practices)
- [OpenAPI](openapi/reducto-parse-api-openapi.yml)
- [JSON Schema — Parse](json-schema/reducto-parse-schema.json)
- [JSON-LD](json-ld/reducto-context.jsonld)
- [Naftiko Capability — Parse](capabilities/parse-parse.yaml)

### Reducto Extract API
Extract structured data from documents using a caller-supplied JSON Schema. Supports Deep Extract for harder documents, Array Extract for repeating sections, and Citations that pin each extracted field to a page and bounding box in the source document.

**Human URL:** [https://docs.reducto.ai/extract/overview](https://docs.reducto.ai/extract/overview)

- [Documentation — Extract Overview](https://docs.reducto.ai/extract/overview)
- [API Reference — Extract](https://docs.reducto.ai/api-reference/extract)
- [API Reference — Extract Async](https://docs.reducto.ai/api-reference/extract-async)
- [Documentation — Response Format](https://docs.reducto.ai/extract/response-format)
- [Documentation — Best Practices](https://docs.reducto.ai/extraction/best-practices-extract)
- [Documentation — Deep Extract](https://docs.reducto.ai/configs/extract/deep-extract)
- [Documentation — Array Extraction](https://docs.reducto.ai/configs/extract/array-extraction)
- [Documentation — Citations](https://docs.reducto.ai/configs/extract/citations)
- [OpenAPI](openapi/reducto-extract-api-openapi.yml)
- [JSON Schema — Extract](json-schema/reducto-extract-schema.json)
- [Naftiko Capability — Extract](capabilities/extract-extract.yaml)

### Reducto Split API
Automatically separate multi-document files and long forms into individual logical units using rules-based Split or Deep Split, then route each unit to downstream Parse, Extract, or Edit operations inside a Pipeline.

**Human URL:** [https://docs.reducto.ai/split](https://docs.reducto.ai/split)

- [Documentation — Split](https://docs.reducto.ai/split)
- [API Reference — Split](https://docs.reducto.ai/api-reference/split)
- [API Reference — Split Async](https://docs.reducto.ai/api-reference/split-async)
- [Documentation — Configuration](https://docs.reducto.ai/configs/split/configuration)
- [Documentation — Deep Split](https://docs.reducto.ai/configs/split/deep-split)
- [OpenAPI](openapi/reducto-split-api-openapi.yml)
- [Naftiko Capability — Split](capabilities/split-split.yaml)

### Reducto Edit API
Fill detected blanks, tables, and checkboxes inside documents from a provided form schema, without requiring per-document templates. Beta endpoint priced at 4 credits per page.

**Human URL:** [https://docs.reducto.ai/editing/edit-overview](https://docs.reducto.ai/editing/edit-overview)

- [Documentation — Edit Overview](https://docs.reducto.ai/editing/edit-overview)
- [API Reference — Edit](https://docs.reducto.ai/api-reference/edit)
- [API Reference — Edit Async](https://docs.reducto.ai/api-reference/edit-async)
- [Documentation — Form Schema](https://docs.reducto.ai/configs/edit/form-schema)
- [OpenAPI](openapi/reducto-edit-api-openapi.yml)
- [Naftiko Capability — Edit](capabilities/edit-edit.yaml)

### Reducto Pipeline API
Compose Parse, Split, Extract, Edit, and Classify into a single multi-step workflow with chained outputs. Supports priority requests on Growth and on-premise / VPC deployments on Enterprise.

**Human URL:** [https://docs.reducto.ai/workflows/pipeline-basics](https://docs.reducto.ai/workflows/pipeline-basics)

- [Documentation — Pipeline Basics](https://docs.reducto.ai/workflows/pipeline-basics)
- [API Reference — Pipeline](https://docs.reducto.ai/api-reference/pipeline)
- [API Reference — Pipeline Async](https://docs.reducto.ai/api-reference/pipeline-async)
- [Documentation — Multi-Document Pipelines](https://docs.reducto.ai/workflows/multi-document-pipelines)
- [Documentation — Chaining Endpoints](https://docs.reducto.ai/workflows/chaining-endpoints)
- [OpenAPI](openapi/reducto-pipeline-api-openapi.yml)
- [Naftiko Capability — Pipeline](capabilities/pipeline-pipeline.yaml)

### Reducto Classify API
Classify documents into a defined set of categories and run citation lookups against parsed content. Billed at 0.5 credits per page of context (default 5 pages = 2.5 credits per document).

**Human URL:** [https://docs.reducto.ai/classify/overview](https://docs.reducto.ai/classify/overview)

- [Documentation — Classify Overview](https://docs.reducto.ai/classify/overview)
- [Documentation — Best Practices](https://docs.reducto.ai/classify/best-practices)
- [Documentation — Response Format](https://docs.reducto.ai/classify/response-format)
- [Documentation — Configuration](https://docs.reducto.ai/configs/classify/configuration)
- [OpenAPI](openapi/reducto-classify-api-openapi.yml)
- [Naftiko Capability — Classify](capabilities/classify-classify.yaml)

### Reducto Jobs API
Retrieve, cancel, and list async jobs created by parse_async, extract_async, split_async, edit_async, and pipeline_async. Pairs with direct or Svix-backed webhooks for completion notifications.

**Human URL:** [https://docs.reducto.ai/workflows/async-overview](https://docs.reducto.ai/workflows/async-overview)

- [Documentation — Async Overview](https://docs.reducto.ai/workflows/async-overview)
- [API Reference — Get Jobs](https://docs.reducto.ai/api-reference/get-jobs)
- [API Reference — Cancel Job](https://docs.reducto.ai/api-reference/cancel-job)
- [API Reference — Retrieve Parse](https://docs.reducto.ai/api-reference/retrieve-parse)
- [OpenAPI](openapi/reducto-jobs-api-openapi.yml)
- [Naftiko Capability — Jobs](capabilities/jobs-jobs.yaml)

### Reducto Upload API
Upload files directly to Reducto storage and receive a `reducto://upload` reference usable across Parse, Split, Extract, Edit, Pipeline, and Classify. Includes large-file (chunked) upload support.

**Human URL:** [https://docs.reducto.ai/upload/overview](https://docs.reducto.ai/upload/overview)

- [Documentation — Upload Overview](https://docs.reducto.ai/upload/overview)
- [Documentation — Large Files](https://docs.reducto.ai/upload/large-files)
- [API Reference — Upload](https://docs.reducto.ai/api-reference/upload)
- [OpenAPI](openapi/reducto-upload-api-openapi.yml)
- [Naftiko Capability — Upload](capabilities/upload-upload.yaml)

### Reducto Webhooks API
Configure webhook endpoints for asynchronous job completion. Supports direct webhooks and Svix-backed delivery, plus a hosted Webhook Portal for end-customer subscription management.

**Human URL:** [https://docs.reducto.ai/workflows/direct-webhooks](https://docs.reducto.ai/workflows/direct-webhooks)

- [Documentation — Direct Webhooks](https://docs.reducto.ai/workflows/direct-webhooks)
- [Documentation — Svix Webhooks](https://docs.reducto.ai/workflows/svix-webhooks)
- [Documentation — Webhook Portal](https://docs.reducto.ai/api-reference/webhook-portal)
- [OpenAPI](openapi/reducto-webhooks-api-openapi.yml)
- [Naftiko Capability — Webhooks](capabilities/webhooks-webhooks.yaml)

### Reducto Platform API
Platform health, version, and metrics endpoints for operating and monitoring Reducto, including Prometheus and streaq metrics exposed by on-premise deployments.

**Human URL:** [https://docs.reducto.ai/api-reference/get-version](https://docs.reducto.ai/api-reference/get-version)

- [API Reference — Get Version](https://docs.reducto.ai/api-reference/get-version)
- [Documentation — Version Pinning](https://docs.reducto.ai/reference/version-pinning)
- [Documentation — Observability](https://docs.reducto.ai/onprem/observability)
- [OpenAPI](openapi/reducto-platform-api-openapi.yml)

## Common Properties

- [Portal](https://reducto.ai)
- [Documentation](https://docs.reducto.ai)
- [Quickstart](https://docs.reducto.ai/quickstart)
- [Studio Quickstart](https://docs.reducto.ai/studio-quickstart)
- [Console — Reducto Studio](https://studio.reducto.ai)
- [SignUp — Reducto Studio](https://studio.reducto.ai)
- [Pricing](https://reducto.ai/pricing)
- [Blog](https://reducto.ai/blog)
- [Support — Contact](https://reducto.ai/contact)
- [Support — Email](mailto:support@reducto.ai)
- [Status Page](https://status.reducto.ai)
- [Trust Center](https://trust.reducto.ai)
- [Security Policies](https://docs.reducto.ai/security/policies)
- [EU Data Residency](https://docs.reducto.ai/security/eu-data-residency)
- [Enterprise Readiness](https://docs.reducto.ai/enterprise/enterprise-readiness)
- [Privacy Policy](https://reducto.ai/privacy)
- [Terms of Service](https://reducto.ai/terms)
- [Rate Limits Docs](https://docs.reducto.ai/reference/rate-limits)
- [Credit Usage Docs](https://docs.reducto.ai/reference/credit-usage)
- [Page Billing Breakdown](https://docs.reducto.ai/reference/page-billing-breakdown)
- [Error Codes](https://docs.reducto.ai/reference/error-codes)
- [FAQ](https://docs.reducto.ai/reference/faq)
- [Glossary](https://docs.reducto.ai/reference/glossary)
- [CLI — Reducto CLI](https://docs.reducto.ai/cli)
- [MCP — Reducto MCP Server](https://docs.reducto.ai/mcp-server)
- [Agent Guide](https://docs.reducto.ai/agent-guide)
- [OpenAPI (full)](https://docs.reducto.ai/openapi.json)
- [OpenAPI (legacy)](https://docs.reducto.ai/openapi-legacy.json)
- [LLMs Center](https://llms.reducto.ai)
- [llms.txt](https://docs.reducto.ai/llms.txt)
- [Cookbooks Overview](https://docs.reducto.ai/cookbooks/overview)
- [Plans](plans/reducto-plans-pricing.yml)
- [Rate Limits](rate-limits/reducto-rate-limits.yml)
- [FinOps](finops/reducto-finops.yml)

## Pricing Snapshot

| Plan | Credit Price | Sync RPS | Highlights |
|---|---|---|---|
| Standard | 15,000 free, then $0.015/credit | 1 | Parse, Extract, Edit, Split, Classify, Pipeline; up to 5 Studio seats |
| Growth | Volume discount (custom) | 10 | Zero data retention, BAA, EU data residency, 5 priority requests, unlimited Studio seats |
| Enterprise | Custom | 100+ | VPC + on-premises, custom MSA/SLA, RBAC, SSO/SAML, dedicated support |

| Operation | Credits |
|---|---|
| Parse (standard / complex / agentic) | 1 / 2 / 4 per page |
| Parse — spreadsheets (accurate / fast) | 1 per 1,000 cells / 1 per 5,000 cells |
| Parse — text files | 0.5 per page |
| Extract (standard) | 2 per page |
| Extract — Deep Extract | 4 per page + 0.1 per field (min 30 per document) |
| Split (standard / Deep Split) | 2 / 4 per page |
| Edit (beta) | 4 per page |
| Classify | 0.5 per page of context (default 5 pages = 2.5 per document) |
| Pipeline | Sum of component-operation credits |

## Maintainers

- **Kin Lane** — info@apievangelist.com — [apievangelist.com](https://apievangelist.com)
