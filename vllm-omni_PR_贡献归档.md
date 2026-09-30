# vLLM-Omni Community Contributions

> Role: **Contributor** (vllm-project/vllm-omni)
> **12 merged PRs** in mainline, spanning **v0.22.0 → v0.28.0**
> Focus areas: Diffusion model (HunyuanImage family) inference performance · Ascend/NPU adaptation · CI & accuracy testing · framework alignment

---

## 1. Diffusion Model (HunyuanImage etc.) Inference Optimization

| # | PR | What it does | Improvement |
|---|----|--------------|-------------|
| #4981 | Enable Diffusion Image models asynchronous output | Enable asynchronous output for diffusion image models | Decouple the generation path from the response path; output no longer blocks subsequent requests, boosting concurrent throughput |
| #5502 | Add vae-patch-parallel-size and vae-use-tiling for HunyuanImage Benchmark | Add VAE patch-parallel-size and VAE tiling support to the HunyuanImage benchmark | Extends the large-scale inference benchmark to support VAE parallel sharding and tiled decoding |

## 2. NPU / Ascend Adaptation

| # | PR | What it does | Improvement |
|---|----|--------------|-------------|
| #5436 | Adapt HunyuanImage3.0 test for npu | Port the HunyuanImage3.0 test to the NPU platform | Unlocks the diffusion inference pipeline on domestic Ascend hardware |
| #6350 | Fix npu moe registration | Fix MoE (Mixture-of-Experts) model registration on NPU | Ensures mixture-of-experts models load and run correctly on Ascend |

## 3. CI & Accuracy Testing

| # | PR | What it does | Improvement |
|---|----|--------------|-------------|
| #3790 | [CI][Accuracy] Add HunyuanImage3 pixel accuracy test and nightly CI | Add HunyuanImage3 pixel-accuracy test plus a nightly CI job | Establishes an automated quality gate that prevents regressions |
| #3795 | Add hunyuan online accuracy test | Add an online accuracy test for Hunyuan | Extends accuracy verification to online inference scenarios |
| #5981 | [Bugfix] Fix HunyuanImage3 accuracy test | Fix the HunyuanImage3 accuracy test | Corrects the test cases so the accuracy check remains trustworthy |
| #5143 | Fix hunyuan ci | Fix the Hunyuan CI workflow | Restores/fixes the CI pipeline |
| #3896 | Fix hunyuan resolve stop token ids | Fix Hunyuan stop-token-id resolution | Corrects the stop-condition logic, improving generation quality and consistency |
| #4174 | [BugFix] fix hunyuan image3 offline cot | Fix the offline Chain-of-Thought (CoT) logic for HunyuanImage3 | Fixes the reasoning-chain logic in offline inference |

## 4. Framework Alignment & Engineering

| # | PR | What it does | Improvement |
|---|----|--------------|-------------|
| #5449 | Fix missing sequence_parallel_size in deploy config output | Fix the missing `sequence_parallel_size` in the deploy-config output | Completes the deploy-config output |

---

### Notes

- All 12 PRs above are **merged** (confirmed via GitHub API, `merged_at` non-null), spanning v0.22.0 → v0.28.0. Closed-without-merge PRs were excluded.
- PR titles are the original GitHub titles (some slightly condensed); the "what it does / improvement" columns summarize the technical value from the PR semantics. Concrete performance numbers (throughput/latency gains) should be taken from each PR's benchmark results — no unverified metrics are claimed here.
- The anonymous account `BLANKETusers` is the commit account. For your profile page, prefer your real account name together with the fact "12 merged PRs" listed here.
- Reference: `https://github.com/vllm-project/vllm-omni/pulls?q=is%3Apr+state%3Aclosed+author%3ABLANKETusers`
