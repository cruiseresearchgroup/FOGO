# FOGO: Forgetting-aware Orthogonalization Optimizer

Official PyTorch implementation of **FOGO** (NeurIPS 2026), a continual-learning
optimizer that treats forgetting as a general *optimization* phenomenon rather
than a problem specific to continual learning.

<p align="center">
  <img src="assets/overview.png" width="100%" alt="FOGO overview">
</p>

**Overview.** FOGO operates at the optimizer level and is architecture-agnostic.
(Left) Each momentum update is *spectrally orthogonalized* so that no single
direction dominates the step, giving a flat-spectrum update with bounded
interference. (Middle) A *compact codebook memory* stores random-projection
summaries of past-task update directions; new updates are projected away from
the protected subspace, so the memory footprint stays in the sub-MB range
instead of scaling with a replay buffer. (Right) A spectral-scaling rule keeps
the protection operator at a fixed target radius regardless of the number of
tasks, so plasticity does not collapse as the stream grows.

Because FOGO changes only the update rule, it composes with existing
continual-learning methods and architectures. The paper evaluates it on
Class-IL and Task-IL (CIFAR-10 / CIFAR-100), imbalanced streams, Domain-IL,
continual VQA with LLaVA-1.5-7B, and GPT-2 pretraining, and frames it as a
plasticity--performance trade-off complementary to branch-freezing methods such
as InfLoRA and O-LoRA.

> **Code status.** The repository is being cleaned up for the camera-ready
> release; expect rough edges. The release will include the FOGO variants used
> in the paper, the GPM reproduction, and per-seed configs and logs in a single
> script.

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
