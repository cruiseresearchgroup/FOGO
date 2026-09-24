# FOGO: Forgetting-aware Orthogonalization Optimizer

Official PyTorch implementation of **FOGO** (NeurIPS 2026), a continual-learning
optimizer that treats forgetting as a general optimization phenomenon rather
than a problem specific to continual learning.

**Overview.** FOGO operates at the optimizer level and is architecture-agnostic.
It combines spectral orthogonalization of the momentum update with a compact
codebook memory of past-task update directions, so that new updates are steered
away from directions that matter for earlier tasks while the memory footprint
stays small and does not scale with a replay buffer. Because FOGO only changes
the update rule, it can be dropped into existing continual-learning pipelines
and architectures.

The paper evaluates FOGO on Class-IL and Task-IL benchmarks (CIFAR-10 /
CIFAR-100), imbalanced streams, Domain-IL, continual VQA with a multimodal LLM,
and language-model pretraining.

> **Code status.** The repository is being cleaned up for the camera-ready
> release; expect rough edges. Configs, scripts, and logs will be added
> progressively.

> If FOGO helps your work, please cite the paper and give the repository a star.
>
> ```bibtex
> @inproceedings{nguyen2026fogo,
>   title     = {{FOGO}: Forgetting-aware Orthogonalization Optimizer},
>   author    = {Nguyen, Toan and Liu, Yang and Le, Trung and De Melo, Celso and Salim, Flora D.},
>   booktitle = {Advances in Neural Information Processing Systems (NeurIPS)},
>   year      = {2026}
> }
> ```
