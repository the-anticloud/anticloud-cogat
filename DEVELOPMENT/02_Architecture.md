# Technical Architecture — COGAT

**Upstream:** [https://github.com/cognitiveatlas/cogat](https://github.com/cognitiveatlas/cogat)
**License:** Apache 2.0
**Category:** PSYCHOLOGY
**Anticloud Integration:** PAX L5 Narrow L2 General 27B + AIOSS + Offline-First

## Upstream Description

Cognitive Atlas ontology and tools

## Anticloud Architectural Changes

1. PAX L5 Narrow L2 General 27B local therapy session transcription — never leaves device
2. AIOSS patient record audit chain (HIPAA-aligned)
3. AES-256 encryption for all session notes and assessments
4. Single-binary clinic deployment with no cloud dependency
5. Zero-telemetry: removes all upstream analytics and data sharing
6. Offline sentiment and risk assessment inference
7. Anonymized local analytics replacing cloud reporting dashboards
8. Audit log for every record access (GDPR Article 30 aligned)

## Integration Points

- **PAX Inference Socket:** Local HTTP endpoint at `127.0.0.1:11434/v1/chat` — same OpenAI-compatible API, zero cloud
- **AIOSS Hook:** Every write operation calls `aioss_append(event, payload)` before commit
- **Encryption Layer:** All file I/O routed through `anticloud_crypto.encrypt_at_rest()`
- **Single Binary Build:** `pyinstaller anticloud_cogat.spec` or `go build -o cogat`

## Deployment Modes

| Mode | Hardware | Notes |
| --- | --- | --- |
| Edge CPU | Raspberry Pi 4 / Intel NUC | Full feature set, PAX on CPU |
| Desktop GPU | RTX 3060 / A10 | PAX GPU inference, <1s latency |
| Server | 2× A100 | Full batch throughput |
| Air-gapped | Any x86/ARM | Zero network dependency |