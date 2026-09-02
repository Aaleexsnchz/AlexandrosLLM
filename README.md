# AlexandrosLLM

Building a GPT-style large language model from scratch in PyTorch — tokenizer, attention, transformer blocks, pretraining and finetuning — implemented step by step rather than assembled from high-level libraries.

The path follows Sebastian Raschka's *Build a Large Language Model (From Scratch)*, extended with my own notes, experiments and benchmarks along the way.

## Status

Early. The repository is scaffolding only; implementation starts with the roadmap below.

## Why

Reading about self-attention is not the same as implementing it. The goal is a working, readable GPT that I understand line by line, with every component written by hand and verified against the reference implementation where one exists.

Non-goals: competitive scale, novel architectures, a production-ready library.

## Roadmap

- [ ] **Text data** — byte-pair encoding, sliding-window sampling, token and positional embeddings
- [ ] **Attention** — simplified self-attention, scaled dot-product, causal masking, multi-head attention
- [ ] **GPT architecture** — layer normalization, GELU, feed-forward blocks, residual connections, full transformer stack
- [ ] **Pretraining** — training loop, cross-entropy loss, temperature and top-k sampling, loading OpenAI GPT-2 weights
- [ ] **Finetuning for classification** — adapting the pretrained model to a labelled task
- [ ] **Instruction finetuning** — supervised instruction tuning and evaluation

Alongside these: notes on what was non-obvious, and benchmarks comparing my implementations against the reference.

## Requirements

- Python 3.12
- [uv](https://docs.astral.sh/uv/) for dependency and environment management

## Getting started

```bash
git clone https://github.com/Aaleexsnchz/AlexandrosLLM.git
cd AlexandrosLLM
uv sync
uv run main.py
```

`uv sync` creates the virtual environment and installs dependencies from `pyproject.toml`; there is no separate activation step when running through `uv run`.

## Reference

Sebastian Raschka, *Build a Large Language Model (From Scratch)*, Manning, 2024 — [book](https://www.manning.com/books/build-a-large-language-model-from-scratch) · [official code](https://github.com/rasbt/LLMs-from-scratch)

## License

Apache License 2.0. See [LICENSE](LICENSE).
