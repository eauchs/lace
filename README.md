# LACE — Latent Adaptive Compression Engine

Semantic compression under physical channel constraints.  
**Does forced bottleneck induce structured cognitive emergence?**

---

## Result (v2)

**Yes — under the right constraint regime.**

A phase transition governs emergence. Below a critical ratio N/K ≈ 25–30, VQ codebooks spontaneously separate retrieval-type and inference-type communications into distinct Voronoi regions — without explicit supervision.

**Cognitive Emergence Law:**
```
N/K < C · d_cog
```
where:
- `d_cog` = intrinsic cognitive separability of the input domain (Cohen's d = 2.45 on raw BPE tokens)
- `C_emp = 0.391 ≈ 1/e = 0.368` (6.3% deviation explained by mean-field corrections)

**Key findings:**
- N/K < 25–30 is the only robust boundary (validated on 128 points, K×N×D sweep)
- Random reward outperforms MiniLM reward (2/3 vs 1/3 seeds significant at K=128, N/K=1.55)
- Cognitive structure is a property of **operational language under compression**, not an artifact of supervision
- d_cog is recoverable from raw syntactic features alone (CV accuracy 74.8%)
- 46 active codes out of 512 — 15 retrieval-dominant, 15 inference-dominant, 16 mixed

**Optimal deployment parameter: K=16 (p=0.0034, survives Bonferroni correction)**

---

## v1 Result (for reference)

47 concepts emerge spontaneously from 198 operational tasks.  
Domain clustering: real (mean coherence 68.4%).  
Retrieval/inference separation: not significant at K=512 (p̂=0.61).  
→ v1 conclusion inverted by v2: compression was insufficient, not excessive.

---

## Architecture

```
Weighted BoW encoder → Spherical VQ codebook (K=16–512) → MLP decoder
Channel budget: 4–9 bits, equivalent to a 9–50 byte LoRa frame.
```

---

## Paper

**LACE v2 — Cognitive Phase Transitions in Semantically Constrained Vector Quantization**

> Lafargue, T. (2026). *Cognitive Phase Transitions in Semantically Constrained Vector Quantization: Emergent Retrieval/Inference Separation Under Physical Bandwidth Constraints* (2.0). Zenodo. https://doi.org/10.5281/zenodo.19664121

- Zenodo DOI: [10.5281/zenodo.19664121](https://doi.org/10.5281/zenodo.19664121)
- HAL preprint: [hal-05596229](https://hal.science/hal-05596229)
- License: CC BY 4.0

---

## Dataset & Weights

→ [ox-ox/lace-semantic-compression](https://huggingface.co/datasets/ox-ox/lace-semantic-compression)

---

## Related Work

- Patent FR2511116 — Hybrid State-Preserving Gateway for LLM inference over 2G/SMS/LoRa/satellite
- llama.cpp PR [#20075](https://github.com/ggml-org/llama.cpp/pull/20075) — Synchronized SSM Checkpointing for speculative decoding on hybrid MoE/SSM models
- llama.cpp PR [#20649](https://github.com/ggml-org/llama.cpp/pull/20649) — Mistral Small 4 (119B MoE) flake8 fix

---

## Citation

```bibtex
@misc{lafargue2026lace,
  author       = {Lafargue, Théophile},
  title        = {Cognitive Phase Transitions in Semantically Constrained Vector Quantization:
                  Emergent Retrieval/Inference Separation Under Physical Bandwidth Constraints},
  year         = {2026},
  version      = {2.0},
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.19664121},
  url          = {https://doi.org/10.5281/zenodo.19664121}
}
```

---

*ox-ox / Théophile Lafargue — Pépite Paris-Saclay, Université Paris-Saclay*
