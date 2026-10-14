# Build and Test

**Project:** `COGAT`
**Upstream:** https://github.com/cognitiveatlas/cogat
**License:** Apache 2.0

## Quick Start

```bash
git clone https://github.com/cognitiveatlas/cogat
cd cogat
pip install -r requirements-anticloud.txt
python anticloud_main.py --offline --pax-local
```

## Anticloud Improvements Applied

1. PAX L5 Narrow L2 General 27B local therapy session transcription — never leaves device
2. AIOSS patient record audit chain (HIPAA-aligned)
3. AES-256 encryption for all session notes and assessments
4. Single-binary clinic deployment with no cloud dependency
5. Zero-telemetry: removes all upstream analytics and data sharing
6. Offline sentiment and risk assessment inference
7. Anonymized local analytics replacing cloud reporting dashboards
8. Audit log for every record access (GDPR Article 30 aligned)

## Benchmark Targets

| Metric | Target |
| --- | --- |
| Latency | Primary inference task: <5s on CPU, <1s on GPU |
| Throughput | Batch processing: >100 items/hour on single CPU server |
| Memory | <8GB RAM for standard deployment |
| Accuracy | Task-specific accuracy within 5% of cloud-API baseline |

## Build Status

Not yet measured. Run verified build and record actual figures above.
