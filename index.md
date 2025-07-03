# VirtualDocs – API and Generative AI Testing for SaaS Platforms

VirtualDocs is a documentation system and execution model designed for modern engineering teams testing mission-critical APIs and large-scale Generative AI interfaces.

This documentation provides a reference-level, no-nonsense framework for defining, validating, and managing tests across microservices, AI endpoints, and multi-environment deployments. Whether you're testing REST APIs, validating JSON responses, benchmarking token outputs from language models, or integrating with CI/CD pipelines — VirtualDocs is designed to scale.

---

## Purpose

Modern software systems increasingly rely on deeply interconnected services and AI systems. The complexity of these integrations demands not just correctness, but resilience, reproducibility, and observability across all surfaces.

VirtualDocs is focused on:

- Enabling testable, predictable behavior in both deterministic APIs and probabilistic AI systems
- Supporting regulated environments where auditability and traceability are required (healthcare, finance, govtech)
- Providing clean and developer-centric tooling with real-world flexibility

---

## Audience

This documentation is intended for:

- Backend developers maintaining SaaS microservices or domain APIs
- ML engineers deploying or fine-tuning GenAI models behind public endpoints
- QA and DevOps engineers building automated test suites for infrastructure validation
- Technical leads responsible for compliance, stability, and monitoring of live services

---

## Core Capabilities

### 1. API Test Design (YAML / SDK)

- Human-readable YAML test definitions
- Request-response validation with schema support
- Header and body assertions
- Status code verification
- Custom test naming, grouping, and tagging

### 2. GenAI Prompt Testing (Planned SDK / YAML Spec)

- Prompt and completion structure definitions
- Token budget constraints
- Latency benchmarking
- Output matching (regex, semantic match, exact string)
- Hallucination detection workflows (planned)
- System prompt conditioning tests

### 3. Execution Environment

- Environment variable support (`.env`, CI secrets)
- Profile switching (staging, production, preview)
- Support for test bundles and batch runs
- CLI-based execution (planned)
- Python SDK-based test automation

### 4. Authentication

- Bearer Token
- OAuth2 with token injection
- Dynamic token fetching via pre-request hooks
- Header templates per environment

### 5. Output & Reporting (Planned)

- Terminal output with summary tables
- JSON output for CI consumption
- Future: HTML or markdown reports with pass/fail visualization
- CI pipeline integration (GitHub Actions, CircleCI, GitLab, Jenkins)

---

## File Structure Example
virtualdocs/
├── tests/
│   ├── get-user.yaml
│   ├── post-comment.yaml
│   ├── llm-check-prompt.yaml
├── .env
└── virtualdocs.yml

---

## Example: REST API Test

```yaml
name: Get Patient Record
request:
  method: GET
  url: https://api.healthcare-platform.com/patients/12345
  headers:
    Authorization: "Bearer {{ env.TOKEN }}"
expect:
  status: 200
  json:
    patient_id: "12345"
    name: "John Doe"
    active: true

## Example: GenAI Prompt Test (Planned Syntax)

name: LLM Welcome Prompt
model: openai:gpt-4
prompt: |
  You are a friendly medical assistant. Greet the user and ask how you can help.
expect:
  contains: "Hello"
  token_limit: 150
  latency_ms: < 1000
  no_hallucination:
    disallowed_terms:
      - cancer cure
      - unverified treatment

GEN AI

Example: GenAI Prompt Test (Planned Syntax)

name: LLM Welcome Prompt
model: openai:gpt-4
prompt: |
  You are a friendly medical assistant. Greet the user and ask how you can help.
expect:
  contains: "Hello"
  token_limit: 150
  latency_ms: < 1000
  no_hallucination:
    disallowed_terms:
      - cancer cure
      - unverified treatment


⸻

Principles

VirtualDocs is built on a few core principles:
	1.	Predictability
API and AI systems should not behave randomly in production. Variance should be observable and controlled.
	2.	Readability
Tests should be written, reviewed, and versioned like code — even by non-developers if needed.
	3.	Portability
All tests are environment-agnostic and execution-tool agnostic. You can run them locally or in CI.
	4.	Observability
Tests should not only pass or fail — they should expose why, and how they relate to previous runs.
	5.	Privacy-Aware
Especially in healthcare, finance, or education — test systems must respect the boundaries of production data.


