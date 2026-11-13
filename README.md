# ai-infra-digest

A daily digest of new releases from the projects that run LLM inference and
training on GPUs: vLLM, llama.cpp, ROCm, PyTorch, SGLang, Transformers and
TensorRT-LLM.

**Everything in `digests/` is generated automatically by an agent and an LLM.**
No human writes or edits the daily files. Commits titled
`chore(bot): daily digest YYYY-MM-DD` come from that agent. Bullets can still be
wrong or miss something important, so treat them as pointers and read the
linked release notes before acting on anything.

## How it works

```
VPS (systemd timer, 07:00 WIB)
  -> GitHub REST API: releases published in the last 24 hours
       vllm-project/vllm, ggml-org/llama.cpp, ROCm/ROCm, pytorch/pytorch,
       sgl-project/sglang, huggingface/transformers, NVIDIA/TensorRT-LLM
  -> 9Router (self-hosted OpenAI-compatible LLM router on the same VPS)
  -> Gemini flash: 3-5 bullets per release from the release notes only
  -> digests/YYYY/MM/YYYY-MM-DD.md + index below
  -> git commit + push to this repo (deploy key scoped to this repo)
```

Rules the agent follows:

- It summarizes only text that appears in the release notes. Each bullet is
  checked before it is written: any version number or `#PR` reference that is
  not in the notes gets the bullet dropped.
- Every release links to its source.
- Repos that ship many builds a day (llama.cpp) are grouped into one entry
  with a link to each build.
- A day with no new releases gets no commit and no placeholder file.
- If the LLM is unavailable, that day is skipped instead of being published
  without summaries.

## Index

<!-- index:start -->
- [2026-11-13](digests/2026/11/2026-11-13.md)
<!-- index:end -->
