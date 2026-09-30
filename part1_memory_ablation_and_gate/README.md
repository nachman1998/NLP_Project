# Parametric memory vs. retrieved passages: Llama-2-7B

`llama7b_two_experiments.ipynb` runs two experiments on `NousResearch/Llama-2-7b-hf`:

1. **Neuron attribution and ablation.** Rank all 352,256 FFN neurons by their attribution to the answer, ablate them strongest first, and track facts recalled from memory, rescued by a true passage, or lost.
2. **False passages under ablation.** At k = 0, 10k, 20k and 30k ablated neurons, compare M1 (plain RAG), M2 (gate → discard the passage) and M3 (counter-example demo).

## Data
- `data/facts.csv`: 246 facts (82 subjects; relations: capital, located_in, descriptive_context; 82 each). Each fact has a cloze `prompt`, the `target_token`, a `true_context` passage, and a `false_context` passage that plants a `false_target`.
- `data/wikitext.json`: WikiText passages for the perplexity (fluency) guard.

## Run
```bash
pip install torch   # the CUDA build for your machine
pip install -r requirements.txt
jupyter notebook llama7b_two_experiments.ipynb
```
Needs a CUDA GPU with at least 16 GB (or several smaller GPUs; the model is split across them). No Hugging Face token is needed. Outputs (CSVs and figures) go to `results_llama7b/`. An interrupted run resumes from there, and `RUN_GPU = False` redraws the figures from the saved CSVs.
