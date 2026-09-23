# Sentinel: AI-Based Fake Identity & Document Screening System

Sentinel is an automated, zero-trust document screening and identity verification ecosystem built for border security checkpoints (SIH 2026 · Problem Statement ID: 26188 · Ministry of Home Affairs - Sashastra Seema Bal). It authenticates passports, visas, and national identity documents in under 3 seconds to detect forgeries, visual tampering, and identity impersonation.

---

## The Architecture

The ecosystem is built using a decoupled microservice architecture combining high-concurrency orchestration with an AI forensic vision pipeline:

- **Core Backend Orchestrator (Go & Gin Framework):** Handles API routing, deterministic checksum/format validations (ICAO 9303 MRZ), role-based access control (RBAC), and MongoDB audit logging without relying on ML inference for static rules.
- **AI & Forensic Inference Engine (Python, FastAPI & PyTorch):** Executes automated OCR field extraction, Error Level Analysis (ELA), CNN visual forgery detection, and facial biometric matching.
- **Multi-Role Web UI (React 19 & Tailwind CSS):** Delivers real-time risk scores, ELA heatmaps, and dedicated operational portals for frontline officers, checkpoint supervisors, and central intelligence command.

---

## Active Repositories

- **[`ps188-backend`](https://github.com/CHAINTRAC/ps188-backend)**: Core API orchestrator written in Go (Gin Framework), managing verification rule evaluation, JWT authentication, MongoDB records, and threat blacklist lookups.
- **[`passport-model`](https://github.com/CHAINTRAC/passport-model)**: AI & Computer Vision microservice executing OCR (EasyOCR), forensic forgery analysis (CNN + ELA), and facial biometric verification (FaceNet / PyTorch).
- **[`ps188-ui`](https://github.com/CHAINTRAC/ps188-ui)**: Frontline React 19 web portal providing interactive dashboards and real-time decision workflows for Verifiers, Admins, and SuperAdmins.
