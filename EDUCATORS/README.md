# Educators — COGAT

**Project:** COGAT  
**Category:** PSYCHOLOGY  
**Upstream:** see BENCH.json  
**Pinned commit:** `fabc06a7979c1caf964e4f41f36c6e534437afe5`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `90824c9223f5cc901b8fea934766e16ede5b06a02b5b425c8269f3c149b819d2`  
**Date:** October 2026

## Teaching with COGAT

The project is usable as a worked example of offline-first packaging with a
cryptographic audit chain. It ships with the assurance suite, the evidence
register and the ledger, so students can verify claims rather than take them on
faith.

## Suggested exercises

1. Run `python tools/run_bench.py --out BENCH.json` and read the 16 results.
2. Recompute the SHA3-256 of a row's evidence file and compare to the register.
3. Walk the AIOSS chain from genesis to head `90824c9223f5cc901b8fea934766e16ede5b06a02b5b425c8269f3c149b819d2` and confirm every link.
4. Break one artifact and observe the chain fail to verify.

## Licence for teaching

Apache 2.0 terms apply to academic and teaching use. See `24_ANTICOMMONS_LICENSE`.
