# Submissions

| model | model repo | results | engine / code | hardware | settings |
|---|---|---|---|---|---|
| oak1.1 | [PNPM244/oak1.1](https://huggingface.co/PNPM244/oak1.1) @ 739b007 | [PNPM244/oak1.1-decision-index/runs/oak1.1](https://huggingface.co/datasets/PNPM244/oak1.1-decision-index/tree/main/runs/oak1.1) (public 0.3: 68.19, complete) | kit 0.3 (62d2f51), in-process `linne_engine:LinneEngine` with `noncausal=1`, `layout=header` (`linne_engine.py` + `nc_hook.py` in the model repo) | 4x H200 (4 processes, 1 per GPU) | bf16; full-attention layers bidirectional over the prompt; question-first layout (up to 4 question instructions of the request, 150 characters each, before the state); one forward pass per question, no generated tokens; softmax (temperature 1) over the option-label logits with the model's logit soft-capping (30); token budget 16384 per batch; nothing truncated; 0 errors, 0 unsupported |
