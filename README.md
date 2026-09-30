# NLP Project

When a retrieved passage disagrees with what a language model already knows, which one wins, and can we control it?

| Part | Directory | What it does |
|---|---|---|
| 1 | [`part1_memory_ablation_and_gate/`](part1_memory_ablation_and_gate/) | Llama-2-7B: FFN neuron attribution and ablation (does a true passage rescue forgotten facts?), and false passages under ablation, comparing plain RAG, a gate that discards suspect passages, and a counter-example demo |
| 2 | [`part2_head_identification_and_steering/`](part2_head_identification_and_steering/) | Memory and context attention heads: identification, validation, and prompt steering (KnownFact-NQ-swap) |

Each directory has its own README with instructions for running it.
