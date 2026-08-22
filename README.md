# reducto-ai (reducto-ai)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Reducto is an AI document-parsing platform that turns unstructured PDFs, images, spreadsheets, slides, and forms into LLM-ready layout, structured data, and form completions. The API exposes Parse, Extract, Split, Edit, Classify, and Pipeline endpoints — each with sync and async variants — plus an Upload API, Webhooks API, and Jobs API. Used by Scale AI, Vanta, Harvey, Medallion, Toast, JLL, Vise, Newfront, and Legora to power document AI in finance, healthcare, insurance, legal, government, and logistics.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/reducto-ai/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/reducto-ai/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### Reducto Parse API

Parse documents (PDFs, images, spreadsheets, slides, text files) and capture layout, structure, OCR text, tables, figures, equations, lists, and LLM-optimized chunks. Supports agentic OCR with error correction, intelligent ordering, figure summarization, embedding optimization, automatic page rotation, multilingual processing across 100+ languages, and synchronous or asynchronous execution.

- **Human URL:** [https://docs.reducto.ai/parse/overview](https://docs.reducto.ai/parse/overview)

#### Tags

- Document AI
- Parse
- OCR
- LLM
- PDF

#### Properties

- [Documentation](https://docs.reducto.ai/parse/overview)
- [API Reference](https://docs.reducto.ai/api-reference/parse)
- [API Reference](https://docs.reducto.ai/api-reference/async-parse)
- [Documentation](https://docs.reducto.ai/parse/response-format)
- [Documentation](https://docs.reducto.ai/parse/best-practices)
- [OpenAPI](openapi/reducto-parse-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/reducto-parse-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/reducto-parse-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/reducto-parse-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [J S O N- L D](json-ld/reducto-context.jsonld)

### Reducto Extract API

Extract structured data from documents using a caller-supplied JSON Schema. Supports Deep Extract for harder documents, Array Extract for repeating sections, and Citations that pin each extracted field to a page and bounding box in the source document.

- **Human URL:** [https://docs.reducto.ai/extract/overview](https://docs.reducto.ai/extract/overview)

#### Tags

- Document AI
- Extract
- Structured Data
- JSON Schema

#### Properties

- [Documentation](https://docs.reducto.ai/extract/overview)
- [API Reference](https://docs.reducto.ai/api-reference/extract)
- [API Reference](https://docs.reducto.ai/api-reference/extract-async)
- [Documentation](https://docs.reducto.ai/extract/response-format)
- [Documentation](https://docs.reducto.ai/extraction/best-practices-extract)
- [Documentation](https://docs.reducto.ai/configs/extract/deep-extract)
- [Documentation](https://docs.reducto.ai/configs/extract/array-extraction)
- [Documentation](https://docs.reducto.ai/configs/extract/citations)
- [OpenAPI](openapi/reducto-extract-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/reducto-extract-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/reducto-extract-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/reducto-extract-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Reducto Split API

Automatically separate multi-document files and long forms into individual logical units using rules-based Split or Deep Split, then route each unit to downstream Parse, Extract, or Edit operations inside a Pipeline.

- **Human URL:** [https://docs.reducto.ai/split](https://docs.reducto.ai/split)

#### Tags

- Document AI
- Split
- Document Classification

#### Properties

- [Documentation](https://docs.reducto.ai/split)
- [API Reference](https://docs.reducto.ai/api-reference/split)
- [API Reference](https://docs.reducto.ai/api-reference/split-async)
- [Documentation](https://docs.reducto.ai/configs/split/configuration)
- [Documentation](https://docs.reducto.ai/configs/split/deep-split)
- [OpenAPI](openapi/reducto-split-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/reducto-split-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/reducto-split-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Reducto Edit API

Fill detected blanks, tables, and checkboxes inside documents from a provided form schema, without requiring per-document templates. Beta endpoint priced at 4 credits per page.

- **Human URL:** [https://docs.reducto.ai/editing/edit-overview](https://docs.reducto.ai/editing/edit-overview)

#### Tags

- Document AI
- Edit
- Forms
- Form Filling

#### Properties

- [Documentation](https://docs.reducto.ai/editing/edit-overview)
- [API Reference](https://docs.reducto.ai/api-reference/edit)
- [API Reference](https://docs.reducto.ai/api-reference/edit-async)
- [Documentation](https://docs.reducto.ai/configs/edit/form-schema)
- [OpenAPI](openapi/reducto-edit-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/reducto-edit-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/reducto-edit-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Reducto Pipeline API

Compose Parse, Split, Extract, Edit, and Classify into a single multi-step workflow with chained outputs. Supports priority requests on Growth, and on-premise / VPC deployments on Enterprise.

- **Human URL:** [https://docs.reducto.ai/workflows/pipeline-basics](https://docs.reducto.ai/workflows/pipeline-basics)

#### Tags

- Document AI
- Workflow
- Pipeline

#### Properties

- [Documentation](https://docs.reducto.ai/workflows/pipeline-basics)
- [API Reference](https://docs.reducto.ai/api-reference/pipeline)
- [API Reference](https://docs.reducto.ai/api-reference/pipeline-async)
- [Documentation](https://docs.reducto.ai/workflows/multi-document-pipelines)
- [Documentation](https://docs.reducto.ai/workflows/chaining-endpoints)
- [OpenAPI](openapi/reducto-pipeline-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/reducto-pipeline-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/reducto-pipeline-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Reducto Classify API

Classify documents into a defined set of categories and run citation lookups against parsed content. Billed at 0.5 credits per page of context (default 5 pages = 2.5 credits per document).

- **Human URL:** [https://docs.reducto.ai/classify/overview](https://docs.reducto.ai/classify/overview)

#### Tags

- Document AI
- Classify
- Document Classification
- Citations

#### Properties

- [Documentation](https://docs.reducto.ai/classify/overview)
- [Documentation](https://docs.reducto.ai/classify/best-practices)
- [Documentation](https://docs.reducto.ai/classify/response-format)
- [Documentation](https://docs.reducto.ai/configs/classify/configuration)
- [OpenAPI](openapi/reducto-classify-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/reducto-classify-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/reducto-classify-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Reducto Jobs API

Retrieve, cancel, and list async jobs created by parse_async, extract_async, split_async, edit_async, and pipeline_async. Pairs with direct or Svix-backed webhooks for completion notifications.

- **Human URL:** [https://docs.reducto.ai/workflows/async-overview](https://docs.reducto.ai/workflows/async-overview)

#### Tags

- Document AI
- Jobs
- Async

#### Properties

- [Documentation](https://docs.reducto.ai/workflows/async-overview)
- [API Reference](https://docs.reducto.ai/api-reference/get-jobs)
- [API Reference](https://docs.reducto.ai/api-reference/cancel-job)
- [API Reference](https://docs.reducto.ai/api-reference/retrieve-parse)
- [OpenAPI](openapi/reducto-jobs-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/reducto-jobs-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/reducto-jobs-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Reducto Upload API

Upload files directly to Reducto storage and receive a reducto://upload reference usable across Parse, Split, Extract, Edit, Pipeline, and Classify. Includes large-file (chunked) upload support.

- **Human URL:** [https://docs.reducto.ai/upload/overview](https://docs.reducto.ai/upload/overview)

#### Tags

- Document AI
- Upload
- Storage

#### Properties

- [Documentation](https://docs.reducto.ai/upload/overview)
- [Documentation](https://docs.reducto.ai/upload/large-files)
- [API Reference](https://docs.reducto.ai/api-reference/upload)
- [OpenAPI](openapi/reducto-upload-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/reducto-upload-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/reducto-upload-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Reducto Webhooks API

Configure webhook endpoints for asynchronous job completion. Supports direct webhooks and Svix-backed delivery, plus a hosted Webhook Portal for end-customer subscription management.

- **Human URL:** [https://docs.reducto.ai/workflows/direct-webhooks](https://docs.reducto.ai/workflows/direct-webhooks)

#### Tags

- Document AI
- Webhooks
- Async

#### Properties

- [Documentation](https://docs.reducto.ai/workflows/direct-webhooks)
- [Documentation](https://docs.reducto.ai/workflows/svix-webhooks)
- [Documentation](https://docs.reducto.ai/api-reference/webhook-portal)
- [API Reference](https://docs.reducto.ai/api-reference/upload)
- [OpenAPI](openapi/reducto-webhooks-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/reducto-webhooks-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/reducto-webhooks-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Reducto Platform API

Platform health, version, and metrics endpoints for operating and monitoring Reducto, including Prometheus and streaq metrics exposed by on-premise deployments.

- **Human URL:** [https://docs.reducto.ai/api-reference/get-version](https://docs.reducto.ai/api-reference/get-version)

#### Tags

- Document AI
- Platform
- Observability

#### Properties

- [API Reference](https://docs.reducto.ai/api-reference/get-version)
- [Documentation](https://docs.reducto.ai/reference/version-pinning)
- [Documentation](https://docs.reducto.ai/onprem/observability)
- [OpenAPI](openapi/reducto-platform-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/reducto-platform-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/reducto-platform-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Portal](https://reducto.ai)
- [Documentation](https://docs.reducto.ai)
- [Documentation](https://docs.reducto.ai/overview)
- [Getting Started](https://docs.reducto.ai/quickstart)
- [Getting Started](https://docs.reducto.ai/studio-quickstart)
- [Console](https://studio.reducto.ai)
- [Sign Up](https://studio.reducto.ai)
- [Pricing](https://reducto.ai/pricing)
- [Blog](https://reducto.ai/blog)
- [Support](https://reducto.ai/contact)
- [Support](mailto:support@reducto.ai)
- [Status Page](https://status.reducto.ai)
- [Trust Center](https://trust.reducto.ai)
- [Documentation](https://docs.reducto.ai/security/policies)
- [Documentation](https://docs.reducto.ai/security/eu-data-residency)
- [Documentation](https://docs.reducto.ai/security/filing-complaints)
- [Documentation](https://docs.reducto.ai/enterprise/enterprise-readiness)
- [Privacy Policy](https://reducto.ai/privacy)
- [Terms of Service](https://reducto.ai/terms)
- [Rate Limits](https://docs.reducto.ai/reference/rate-limits)
- [Documentation](https://docs.reducto.ai/reference/credit-usage)
- [Documentation](https://docs.reducto.ai/reference/page-billing-breakdown)
- [Documentation](https://docs.reducto.ai/reference/error-codes)
- [F A Q](https://docs.reducto.ai/reference/faq)
- [Glossary](https://docs.reducto.ai/reference/glossary)
- [Documentation](https://docs.reducto.ai/reference/version-pinning)
- [C L I](https://docs.reducto.ai/cli)
- [M C P](https://docs.reducto.ai/mcp-server)
- [Documentation](https://docs.reducto.ai/agent-guide)
- [OpenAPI](https://docs.reducto.ai/openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI](https://docs.reducto.ai/openapi-legacy.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://llms.reducto.ai)
- [Documentation](https://docs.reducto.ai/llms.txt)
- [Code Examples](https://docs.reducto.ai/cookbooks/overview)
- [Code Examples](https://docs.reducto.ai/cookbooks/batch-processing)
- [Code Examples](https://docs.reducto.ai/cookbooks/financial-analysis)
- [Code Examples](https://docs.reducto.ai/cookbooks/form-filling)
- [Code Examples](https://docs.reducto.ai/cookbooks/identity-verification)
- [Code Examples](https://docs.reducto.ai/cookbooks/invoice-extraction)
- [Code Examples](https://docs.reducto.ai/cookbooks/multilingual-processing)
- [Code Examples](https://docs.reducto.ai/cookbooks/multimodal-rag-image-results)
- [Code Examples](https://docs.reducto.ai/cookbooks/redlined-legal-contracts)
- [Code Examples](https://docs.reducto.ai/cookbooks/web-browsing-browserbase)
- [Documentation](https://docs.reducto.ai/onprem/enterprise_deployment_options)
- [Documentation](https://docs.reducto.ai/onprem/hybrid-vpc-deployment)
- [Documentation](https://docs.reducto.ai/onprem/hybrid-vpc-aws)
- [Documentation](https://docs.reducto.ai/onprem/hybrid-vpc-azure)
- [Documentation](https://docs.reducto.ai/onprem/hybrid-vpc-gcs)
- [Documentation](https://docs.reducto.ai/onprem/hybrid-vpc-box)
- [Documentation](https://docs.reducto.ai/onprem/security_model)
- [Changelog](https://docs.reducto.ai/onprem/changelog)
- [Plans](plans/reducto-plans-pricing.yml)
- [Rate Limits](rate-limits/reducto-rate-limits.yml)
- [Fin Ops](finops/reducto-finops.yml)
- [Features](undefined)
- [Use Cases](undefined)
- [Integrations](undefined)
- [Solutions](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
