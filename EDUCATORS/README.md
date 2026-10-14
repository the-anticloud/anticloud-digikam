# Educators — DIGIKAM

**Project:** DIGIKAM  
**Category:** CAMERAS  
**Upstream:** see BENCH.json  
**Pinned commit:** `see BENCH.json`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `17fbecc150793c6f05a1a8df39e3e6030318502c5ef01b56cce3c2d59c1e1d29`  
**Date:** October 2026

## Teaching with DIGIKAM

The project is usable as a worked example of offline-first packaging with a
cryptographic audit chain. It ships with the assurance suite, the evidence
register and the ledger, so students can verify claims rather than take them on
faith.

## Suggested exercises

1. Run `python tools/run_bench.py --out BENCH.json` and read the 16 results.
2. Recompute the SHA3-256 of a row's evidence file and compare to the register.
3. Walk the AIOSS chain from genesis to head `17fbecc150793c6f05a1a8df39e3e6030318502c5ef01b56cce3c2d59c1e1d29` and confirm every link.
4. Break one artifact and observe the chain fail to verify.

## Licence for teaching

Apache 2.0 terms apply to academic and teaching use. See `24_ANTICOMMONS_LICENSE`.
