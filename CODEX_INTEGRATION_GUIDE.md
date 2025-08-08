# 🤖 Codex Integration Guide for Dental Claims Automation Platform

This guide is your blueprint to successfully build the **Dental Claims Automation Platform** using **OpenAI Codex** (or GPT-4/GPT-4o) as your pair programmer.

---

## 🧠 Objective

To guide Codex in generating **modular, production-grade code** for every microservice in the monorepo using:
- Detailed feature prompts
- Sample inputs/outputs
- Test specifications
- API contracts
- Dev and deployment infrastructure

---

## 📁 Project Structure (Recap)

```
dental_claims_monorepo/
├── services/
│   └── <module_name>/
│       ├── README.md
│       ├── features.md
│       ├── codex_prompt.md
├── shared/
│   ├── contracts/
│   │   ├── openapi/
│   │   └── asyncapi/
│   ├── libs/
├── infra/
├── qa/
├── ops/
├── CODEX_INTEGRATION_GUIDE.md
├── EXPECTED_FEATURES_AND_REQUIREMENTS.md
```

---

## 🚀 How to Use Codex Effectively

### 🔁 Workflow

1. **Choose a service** (e.g., `claim-assembly`)
2. Open the file: `services/claim-assembly/codex_prompt.md`
3. Feed the entire prompt to Codex or GPT-4o in chunks
4. Ask Codex to:
   - Generate data models (DTOs/entities)
   - Build REST APIs with OpenAPI annotations
   - Write tests and validators
   - Generate sample seed data
   - Generate database migration files
5. Review and test the generated code locally

---

### 🛠️ Example Prompt Flow for `claim-assembly`

Start Codex prompt:

```
POST /generate_claim
Goal: Assemble a dental insurance claim (ADA format or 837D EDI-ready JSON) from input treatment, patient, and policy data.
```

Ask:
- ✅ Generate FastAPI route with input validation
- ✅ Build a Pydantic model for the claim
- ✅ Write unit test using `pytest`
- ✅ Store claim in Postgres with SQLAlchemy
- ✅ Emit event `claim.ready_for_submission` to Kafka

---

## 🧪 Codex Output Requirements

Each generated feature should include:
- ✅ Data models (DTOs or ORMs)
- ✅ Endpoint (with FastAPI/Spring/NestJS decorators)
- ✅ Business logic
- ✅ Test case (unit and edge cases)
- ✅ Error handling
- ✅ Logging
- ✅ Example input/output JSON
- ✅ Docstring or Swagger/OpenAPI annotations

---

## 🧬 Prompt Examples for Codex

### 🏁 Start Small

> "Create a FastAPI POST endpoint to receive patient insurance info and store it in Postgres."

### ⚙️ Systemic Feature

> "Given this codex_prompt.md for 'payments', generate the full ERA parsing service that reads an uploaded 835 file and posts the results to the ledger."

### 🧪 Testing

> "Generate pytest unit tests for the CDT validation rule engine using mock CDT codes and payer rules."

### 🧠 AI-Assisted Coding

> "Create a Python function that uses an OpenAI model to classify dental claim denial reasons from raw text."

---

## 🖼️ Codex Session Best Practices

| Tip | Description |
|-----|-------------|
| 🔄 Break prompts | Split features into chunks |
| 📄 Use examples | Codex responds best to concrete input/output |
| 🧪 Ask for tests | Always ask for unit tests |
| 🧼 Request cleanups | e.g. "Add logging", "Add OpenAPI docstrings" |
| 🔄 Review output | Copy/paste small pieces, verify, refine |
| 🔗 Chain tasks | "Now write the migration file", "Add async handling" |

---

## 📦 Codex Completion Checklist

For each feature in a module:
- [ ] Prompt reviewed and clear
- [ ] Codex generates models, endpoints, tests
- [ ] Stored in the right file/module
- [ ] Verified locally with `make test` or Docker Compose
- [ ] API visible in Swagger UI or testable in Postman
- [ ] Event emitted if needed
- [ ] Integrated with other modules (e.g., Kafka, DB, filesystem)

---

## 🧰 Suggested Tools

- 🧠 Codex in VS Code (GitHub Copilot or GPT-4 via ChatGPT sidebar)
- 🧪 Test locally with Docker Compose
- 🔄 Copy/paste OpenAPI specs from `/shared/contracts/openapi/`
- ✅ Validate output with `pytest`, Postman, or Swagger UI

---

## 🧾 Codex Output Audit Questions

- Does the response have examples?
- Are the inputs strongly typed?
- Are all edge cases and validation handled?
- Does it produce a meaningful error if things go wrong?
- Is the logic clean and testable?

---

## 💡 Pro Tip

Ask Codex:
> “How would you build this feature in a production-grade microservice with testability, observability, and error handling?”

---

Once this guide and the prompts are paired with Codex, you’ll be able to rapidly construct the entire dental claims platform service-by-service with intelligent automation and reliable results.

