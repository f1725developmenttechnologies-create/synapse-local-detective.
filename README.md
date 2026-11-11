# synapse-local-detective.
# Synapse Local Detective 🕵️‍♂️🛡️

**The first Zero-Trust AI auditing Skill for UGREEN AI NAS.**

> *Cloud AI hallucinates. Synapse Local Detective is a zero-trust AI agent for UGREEN NAS. It connects scattered files into unified reports, verifying every claim with SHA-256. 100% local, zero hallucinations.*

---

## 📌 The Problem
Freelancers, researchers, and small teams use NAS devices to store chaotic folders of multi-modal files (receipts, PDFs, whiteboard photos, meeting notes). When they try to use AI to synthesize this data, they face two massive risks:
1.  **Data Privacy:** Cloud-based AI requires uploading sensitive data to third-party servers.
2.  **AI Hallucinations:** Generative AI frequently invents facts or mixes up sources, making it useless for forensic or legal auditing.

## 💡 The Solution: Zero-Trust Synthesis
**Synapse Local Detective** is an autonomous multi-agent Skill that runs entirely on the local NAS. It doesn't just "chat" with your files. It acts as a forensic auditor.
*   It clusters related files across different formats (images, PDFs, text).
*   It extracts the data using local OCR and Document Agents.
*   **Crucially**, it generates a unified report where every single synthesized sentence is cryptographically tied to a **SHA-256 hash** of the source file. 
*   If a claim cannot be verified by a local file, it is explicitly flagged as `[UNVERIFIED]` rather than guessed.

## 🧠 Architecture & Workflow (Nonacortex 5-3-1)
The Skill operates using a sequential orchestration of UGOS native agents, orchestrated via the `SKILL.md` file:

1.  **Ingestion & Hashing:** The **File Agent** scans the target directory, cataloging files and generating a SHA-256 hash map.
2.  **Multi-Modal Extraction:** The **Document Agent** parses PDFs, while the **Photo Agent** performs local OCR on receipts and whiteboards.
3.  **Semantic Clustering:** The orchestrator groups extracted data by semantic similarity (e.g., matching a photo of a receipt to a PDF invoice).
4.  **Zero-Trust Synthesis:** A unified summary is generated. A strict verification logic ensures every claim is linked to a source hash.
5.  **Output:** The **Knowledge Agent** saves the final cited report to the NAS, awaiting user confirmation. The Skill remains strictly read-only until this final step.

## 🚀 Scalability & UGOS Integration
While this Round 1 submission is designed to leverage native UGOS AI agents, its architecture is built for the Linux foundation of UGOS:
*   **Native Execution:** Perfect for lightweight, everyday document auditing via UGOS agents.
*   **Containerized Scaling (Future Roadmap):** If granted NAS access in Round 2, the SHA-256 hashing and semantic clustering logic can be deployed as a lightweight **Docker container**. This allows the system to run heavier local LLMs (like Qwen) and embedding models natively in an isolated Linux VM, ensuring 100% data sovereignty and leveraging the full open-source power of UGOS.

## 🛠️ Built With
*   **Markdown / YAML** (SKILL.md Orchestration)
*   **UGOS Native Agents** (File, Document, Photo, Knowledge)
*   **SHA-256 Cryptography** (Zero-Trust Verification)
*   **Local LLM / Embedding Models** (Semantic Clustering)
*   **Python** (Future Docker roadmap)

## 🏆 Hackathon Context
Built for the **UGREEN AI NAS Hackathon 2026**.
*   **Track:** Automate Your Workflow
*   **Developer:** Freddy Adrián Sánchez Colmenares / F1725 Development Technologies.

---
*“Trust is not given to AI; it is cryptographically verified.”*