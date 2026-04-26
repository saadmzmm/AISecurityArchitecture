# AISecurityArchitecture

A production-ready FastAPI microservice demonstrating advanced LLM security techniques, including Prompt Injection defense, RAG Data Poisoning mitigation, and LLM-as-a-Judge guardrails.

## Architecture Highlights
* **Layer 1: Cryptographic Data Provenance:** Uses SHA-256 hashing to verify internal document integrity before feeding data to the LLM (Mitigating Indirect Prompt Injection / Data Poisoning).
* **Layer 2: Dual-Model Guardrail (LLM-as-a-Judge):** A semantic firewall that analyzes network payloads for malicious intent (Obfuscation, Persona Overrides, Direct Extraction) before routing to the worker model.
* **Layer 3: FastAPI Web Server:** A RESTful API built to handle JSON payloads and fail securely (HTTP 403/422) during cyber attacks.

## Vulnerabilities Mitigated
* **Cognitive Overload & String Manipulation:** Blocked via intent-based semantic filtering.
* **Payload Splitting (Smuggling):** Blocked via token-reassembly analysis in the Bouncer model.
* **RAG Data Poisoning:** Blocked via cryptographic hash verification.

## How to Run Locally
1. Clone the repo.
2. Run `pip install -r requirements.txt` (fastapi, uvicorn, google-genai, pydantic).
3. Set your API key: `export GEMINI_API_KEY="your_key"`
4. Boot the server: `uvicorn day4_finaproductapi:app --reload`
5. Visit `http://127.0.0.1:8000/docs` to test attacks against the API.

<img width="800" height="450" alt="VideoProject-ezgif com-video-to-gif-converter" src="https://github.com/user-attachments/assets/9185e5e7-4460-4524-8da5-f0e946e9cc69" />


