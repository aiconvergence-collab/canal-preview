# Private Binary Preview

CANAL is not publicly released yet.

The first preview is binary-only. This lets testers run CANAL without receiving
the private C++ source code.

## Tester Requirements

- Linux
- NVIDIA GPU, ideally 24GB VRAM or larger
- 64GB system RAM recommended
- local GGUF model
- comfort running one shell command

## What Testers Receive

- CANAL `llama-server`
- CANAL `llama-completion`
- required shared libraries
- one-command proof script
- review docs

## What Testers Run

```bash
MODEL=/path/to/model.gguf ./run-private-beta-proof-binary.sh
```

Optional MRCR proof:

```bash
MODEL=/path/to/model.gguf \
MRCR_DATASET=/path/to/MRCR-v2_8needle.clean.jsonl \
MRCR_LIMIT=3 \
./run-private-beta-proof-binary.sh
```

## What Testers Send Back

- GPU model
- system RAM
- model file name and quantization
- exact command used
- result folder
- `step-summary.tsv`
- any out-of-memory, prompt-too-long, or SSD file messages

## Source Rule

The public preview does not include source. Source access is not part of the
public beta.

