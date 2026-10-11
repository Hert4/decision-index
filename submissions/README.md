# Submissions

| model | model repo | results | engine / code | hardware | settings |
|---|---|---|---|---|---|
| linne-oak-1.0 | [MISA-core/linne-oak-1-0](https://huggingface.co/MISA-core/linne-oak-1-0) @ f5e11b6 (weights) | [MISA-core/linne-oak-1-0-decision-index/runs/linne-oak-1-0](https://huggingface.co/datasets/MISA-core/linne-oak-1-0-decision-index/tree/main/runs/linne-oak-1-0) (public 0.3: 63.94, complete) | kit 0.3 (62d2f51), in-process `linne_engine:LinneEngine` with `noncausal=1` (`linne_engine.py` + `nc_hook.py` in the model repo) | 4x H200 (4 processes, 1 per GPU) | bf16; full-attention layers bidirectional over the prompt; one forward pass per question, no generated tokens; softmax (temperature 1) over the option-label logits with the model's logit soft-capping (30); token budget 16384 per batch; nothing truncated; 0 errors, 0 unsupported |
