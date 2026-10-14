# Students — COGAT

**Project:** COGAT  
**Category:** PSYCHOLOGY  
**Upstream:** see BENCH.json  
**Pinned commit:** `fabc06a7979c1caf964e4f41f36c6e534437afe5`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `90824c9223f5cc901b8fea934766e16ede5b06a02b5b425c8269f3c149b819d2`  
**Date:** October 2026

## What this project gives you

A complete worked example of offline-first packaging with a cryptographic audit
chain: source pinned at `fabc06a7979c1caf964e4f41f36c6e534437afe5`, a 16-check assurance suite, an evidence register
with per-check hashes, and an AIOSS ledger chain ending at `90824c9223f5cc901b8fea934766e16ede5b06a02b5b425c8269f3c149b819d2`.

## Learn by verifying

```
python tools/run_bench.py --out BENCH.json
```

Then take any row from `ISOLATED_LAB_RESULTS/03_Result_Register.md`, recompute
the SHA3-256 of its evidence file, and confirm it matches. If it does not match,
the record has been altered — that is the whole point of the chain.

## Licence

Apache 2.0 terms apply to study and teaching use.
