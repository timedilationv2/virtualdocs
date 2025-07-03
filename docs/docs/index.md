# VirtualDocs – API and GenAI Testing for SaaS Platforms

VirtualDocs is a documentation system and execution model designed for engineering teams testing mission-critical APIs and generative AI endpoints.

This documentation provides a reference framework for defining, validating, and managing tests across microservices, AI endpoints, and CI/CD environments.

---

=== "Purpose"

    Modern software systems increasingly rely on interconnected services and AI systems.
    VirtualDocs focuses on:

    - Testable, predictable behavior in both REST APIs and GenAI systems
    - Regulated, auditable test processes
    - Developer-friendly tooling for real-world workflows

---

=== "Audience"

    This documentation is designed for:

    - Backend engineers testing SaaS microservices
    - ML engineers testing prompts and completions
    - QA teams writing integration test suites
    - DevOps teams automating validation pipelines

---

=== "Core Capabilities"

    - YAML and SDK-based test definitions
    - Prompt structure validation for GenAI
    - Multi-env auth handling (token, OAuth2)
    - Semantic and regex-based output checks

---

=== "File Structure"

    ```
    virtualdocs/
    ├── tests/
    │   ├── get-patient.yaml
    │   ├── llm-prompt-check.yaml
    ├── .env
    └── mkdocs.yml
    ```
