# CANAL

**Long-context local inference for llama.cpp.**

CANAL is a private llama.cpp branch that extends local context by moving old KV
cache data out of GPU memory, storing it in RAM or SSD, and retrieving useful
older context when the model needs it.

Short technical description:

> KV overflow + retrieval + RAM/SSD-backed KV storage + RAM compression.

CANAL is not publicly released yet. This repo is the public preview page and
evidence summary. It does **not** contain the private CANAL source code.

## Why It Exists

Local models are limited by GPU memory. Long prompts, large document packs, and
big codebase questions can exceed the live KV cache that fits on a normal GPU.

CANAL aims to keep the live GPU KV cache bounded while preserving access to
older important context.

## Current Proof Snapshot

| Check | Result |
|---|---:|
| Qwen 3.6 27B near-1M MRCR | 100/100 |
| Mistral Small 3.1 near-1M MRCR | 20/20 |
| Gemma 3 near-1M MRCR | 20/20 |
| Opus-distilled 35B A3B near-1M MRCR | 20/20 |
| Qwen 3.6 codebase QA with CANAL | 5/5 |
| Qwen 2.5 Coder codebase QA with CANAL | 5/5 |
| No-CANAL codebase control | 0/5, prompt too long |
| Real-document QA curated profile | passed |
| Binary-only package proof | passed |
| Clean-folder binary smoke | passed |

Tested primary hardware:

- NVIDIA RTX 3090 24GB
- 64GB system RAM
- Linux + CUDA

More detail: [docs/proof-results.md](docs/proof-results.md)

## What CANAL Is Not

CANAL is not:

- unlimited context
- perfect recall
- a replacement for model quality
- compressed-domain attention
- a public production release today

Known limits: [docs/known-limits.md](docs/known-limits.md)

## Private Binary Preview

The first preview is binary-only. That means testers can run CANAL without
receiving the private C++ source code.

Preview package includes:

- CANAL `llama-server`
- CANAL `llama-completion`
- required shared libraries
- one-command proof script
- review docs

Private preview details: [docs/private-beta.md](docs/private-beta.md)

## Early Use Cases

- Legal discovery and contract review
- Medical or insurance record review
- Internal company knowledge bases
- Large codebase question answering
- Research archive analysis
- Compliance logs and audit trails
- Long chat or support-ticket history

## Request Access

CANAL is currently available only as a controlled binary preview by request.

Send:

- GPU model
- system RAM
- operating system
- models you run locally
- what long-context workflow you want to test

## FAQ

See [docs/faq.md](docs/faq.md).

## Source Status

This public repo intentionally does not include CANAL source code. Source access
is not part of the public preview.

