# Submissions

| model | model repo | results | engine / code | hardware | settings |
|---|---|---|---|---|---|
| misa-ai-2.0-decision-plus | [misa-jsc/misa-ai-2.0-decision-plus](https://huggingface.co/misa-jsc/misa-ai-2.0-decision-plus) @ 73b5e65 | [misa-jsc/misa-ai-2.0-decision-plus-decision-index/runs/misa-ai-2.0-decision-plus](https://huggingface.co/datasets/misa-jsc/misa-ai-2.0-decision-plus-decision-index/tree/main/runs/misa-ai-2.0-decision-plus) (public 0.3: 63.94, complete) | kit 0.3 (62d2f51), in-process `linne_engine:LinneEngine` with `noncausal=1` (`linne_engine.py` + `nc_hook.py` in the model repo) | 4x H200 (4 processes, 1 per GPU) | bf16; full-attention layers bidirectional over the prompt; one forward pass per question, no generated tokens; softmax (temperature 1) over the option-label logits with the model's logit soft-capping (30); token budget 16384 per batch; nothing truncated; 0 errors, 0 unsupported |
