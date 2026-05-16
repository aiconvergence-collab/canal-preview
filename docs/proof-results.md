# CANAL Proof Results

This page summarizes the current private-branch proof snapshot.

## Main Claim

CANAL lets local llama.cpp models answer long-context retrieval tasks while
keeping the live GPU KV cache bounded.

Short description:

> KV overflow + retrieval + RAM/SSD-backed KV storage + RAM compression.

## Strongest Long-Context Result

| Field | Value |
|---|---|
| Model | Qwen 3.6 27B Q5_K_M |
| Hardware | single RTX 3090 |
| Task | MRCR-v2 8-needle |
| Rows | 500-599 |
| Context cap | 1,010,000 |
| Result | 100/100 |
| Mean sequence score | 0.999759977026 |

## Current Branch Validation

### Near-1M MRCR Retrieval

| Check | Result |
|---|---:|
| Qwen 3.6 current-branch MRCR revalidation | 25/25 |
| Mistral Small 3.1 near-1M MRCR | 20/20 |
| Gemma 4 26B near-1M MRCR | 20/20 |
| Opus-distilled 35B A3B near-1M MRCR | 20/20 |

### Codebase And Product Hardening

| Check | Result |
|---|---:|
| Qwen 3.6 codebase QA with CANAL | 5/5 |
| Qwen 2.5 Coder codebase QA with CANAL | 5/5 |
| No-CANAL codebase control | 0/5, prompt too long |
| Real-document QA curated profile | passed |
| Qwen 3.6 server near-1M | passed |
| SSD server safety | 5/5 |
| Authenticated server-abuse smoke | passed |
| Binary-only package proof with Qwen 3.6 | passed |
| Clean-folder binary package smoke | passed |
| Clean real-document QA profile | passed |

## Why The Control Matters

The no-CANAL control failed with a prompt-too-long error on the same codebase
QA task where CANAL passed. That is the key comparison:

- without CANAL: prompt does not fit
- with CANAL: task runs and answers pass

## Current Evidence Policy

Raw result artifacts are retained in the private development environment. The
binary preview includes a proof script so a qualified tester can reproduce a
small proof without receiving private source code.
