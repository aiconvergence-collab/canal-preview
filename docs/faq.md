# FAQ

## Is CANAL open source?

Not currently. This public repo is a preview and evidence page. It does not
contain the private CANAL implementation.

## Is CANAL the same as a bigger context window?

No. CANAL keeps the live GPU KV cache bounded and retrieves older useful
context from RAM or SSD.

## Is this unlimited context?

No. CANAL is long-context infrastructure, not unlimited context.

## Does CANAL replace model quality?

No. A stronger model can still answer better than a weaker model. CANAL helps
the model access more relevant old context.

## What hardware was tested?

The primary local proof machine uses an RTX 3090 24GB and 64GB RAM.

## Can this run on Mac?

Maybe later. The current validated path is Linux plus NVIDIA CUDA.

## Why binary preview first?

The binary lets testers run the software without exposing the private source
code.

