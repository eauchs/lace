# LACE — Latent Adaptive Compression Engine

Semantic compression under physical channel constraints.
Does forced bottleneck induce structured semantic emergence?

## Result

47 concepts emerge spontaneously from 198 operational tasks.
Domain clustering: real (mean coherence 68.4%).
Retrieval/inference separation: not significant (permutation test p̂=0.61).

First layer of emergence = domain. Second layer = open question.

## Dataset & weights

→ [ox-ox/lace-semantic-compression](https://huggingface.co/datasets/ox-ox/lace-semantic-compression)

## Architecture

Weighted BoW encoder → Spherical VQ codebook (K=512) → MLP decoder  
Channel budget: 9 bits (log₂ 512), equivalent to a 50-byte LoRa frame.

## Related

Patent FR2511116 — Hybrid State-Preserving Gateway for LLM over 2G/SMS  
llama.cpp PR #20075 — Synchronized SSM Checkpointing
