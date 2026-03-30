# LLM4ML
A curated collection of research, methods, and design patterns on using Large Language Models (LLMs) to solve machine learning problems

---

## 📊 LLM for Tabular Data

Papers on applying Large Language Models to tabular data prediction, few-shot learning, feature engineering, and data imputation.

| Paper | Venue | Year | Description |
|-------|-------|------|-------------|
| [TabPFN-2.5: Advancing the State of the Art in Tabular Foundation Models](https://arxiv.org/abs/2511.08667) | arXiv | 2025 | Next-gen tabular foundation model (up to 50K rows, 2K features). SOTA on TabArena, 100% win rate vs default XGBoost on small/medium datasets. Includes distillation to MLP/tree ensembles for low-latency deployment. |
| [STUNT: Few-shot Tabular Learning with Self-generated Tasks from Unlabeled Tables](https://arxiv.org/abs/2303.00918) | ICLR 2023 | 2023 | Meta-learning framework that self-generates few-shot tasks by treating random columns as pseudo-labels from unlabeled tables. Also introduces an unsupervised validation scheme for hyperparameter search. |
| [FeatLLM: LLMs Can Automatically Engineer Features for Few-Shot Tabular Learning](https://arxiv.org/abs/2404.09491) | arXiv | 2024 | Uses LLMs as in-context feature engineers; a simple downstream model (e.g., linear regression) operates on generated features at inference—no per-sample LLM calls. Outperforms TabLLM and STUNT by ~10% on average. |
| [TABLET: Learning From Instructions For Tabular Data](https://arxiv.org/abs/2304.13188) | arXiv | 2023 | Benchmark of 20 tabular datasets with natural-language instructions. In-context instructions boost zero-shot F1 by 44% (Flan-T5 11B) and 13% (ChatGPT), but reveals LLMs often ignore fine-grained instructions. |
| [LIFT: Language-Interfaced Fine-Tuning for Non-Language ML Tasks](https://arxiv.org/abs/2206.06565) | NeurIPS 2022 | 2022 | Fine-tunes pretrained LMs on tabular tasks using only natural-language interfaces—no architectural changes or custom losses. Matches strong baselines across low-dimensional classification and regression tasks. |
| [TP-BERTa: Making Pre-trained LMs Great on Tabular Prediction](https://arxiv.org/abs/2403.01841) | ICLR 2024 | 2024 | BERT pre-trained for tabular data with *relative magnitude tokenization* for numerics and *intra-feature attention* to fuse feature names with values. Leads among tabular DNNs and rivals GBDTs. |
| [Tabular Transfer Learning via Prompting LLMs](https://openreview.net/pdf?id=bo4pauxnIR) | COLM 2024 | 2024 | Zero/few-shot cross-table transfer via structured prompting alone—no fine-tuning. Shows promise and limitations of prompt-based transfer across heterogeneous table schemas. |

---

## 🌳 LLM for Decision Tree

Papers on using Large Language Models to construct, induce, prune, or enhance decision trees and tree ensembles.

| Paper | Venue | Year | Description |
|-------|-------|------|-------------|
| [GPTree: Towards Explainable Decision-Making via LLM-powered Decision Trees](https://arxiv.org/abs/2411.08257) | arXiv | 2024 | Combines explainability of decision trees with LLM reasoning. Dynamically splits samples using a tree structure—no feature engineering or prompt chaining needed. Includes an expert-in-the-loop feedback mechanism. Achieves 7.8% precision identifying "unicorn" startups, surpassing GPT-4o few-shot and top human experts. |
| [LLEGO: Decision Tree Induction Through LLMs via Semantically-Aware Evolution](https://arxiv.org/abs/2503.14217) | arXiv | 2025 | Evolutionary (genetic programming) approach to decision tree induction that integrates LLMs as sources of semantic priors. Introduces *fitness-guided crossover* and *diversity-guided mutation* operators via structured natural-language prompts, improving generalization and search efficiency over conventional GP methods. |
| [MAPLE: Multi-Agent Prior Learning for Constructing Tree Ensembles](https://openreview.net/pdf?id=bBIA4TVEBG) | ICLR 2026 Workshop | 2026 | Framework that integrates learned feature priors from multiple agents directly into bagging/boosting tree ensemble construction. Leverages multiple inductive bias sources to improve predictive performance and robustness while preserving diversity and remaining computationally efficient. |
| [FORESTLLM: LLMs Make Random Forest Great on Few-shot Tabular Learning](https://arxiv.org/abs/2601.11311) | arXiv | 2025 | Combines decision forest inductive biases with LLM semantic reasoning. LLM acts as offline model designer (semantic splits + leaf stabilization); no LLM needed at test time. SOTA on few-shot tabular benchmarks. |
| [LLM-Forest: Ensemble LLMs with Graph-Augmented Prompts for Data Imputation](https://aclanthology.org/2025.findings-acl.361.pdf) | Findings of ACL 2025 | 2025 | Ensemble framework for tabular data imputation using graph-augmented prompts that encode feature correlations. Aggregates predictions from multiple LLMs for robust missing value estimation. |

---

## 🧠 LLM as Prior Knowledge

Papers on using Large Language Models to elicit, construct, or aggregate prior distributions and domain knowledge for probabilistic and Bayesian models.

| Paper | Venue | Year | Description |
|-------|-------|------|-------------|
| [LLM-Prior: A Framework for Knowledge-Driven Prior Elicitation and Aggregation](https://arxiv.org/abs/2508.03766) | arXiv | 2025 | Proposes LLMPrior, an operator that converts unstructured context (text, data, figures) into valid probability distributions by coupling an LLM with a tractable generative model (e.g., GMM/Mixture Density Network). Extends to multi-agent settings via Logarithmic Opinion Pooling and a federated prior aggregation algorithm (Fed-LLMPrior) robust to agent heterogeneity. |
| [AutoElicit: Using LLMs for Expert Prior Elicitation in Predictive Modelling](https://arxiv.org/abs/2411.17284) | arXiv | 2024 | Extracts knowledge from LLMs to construct informative priors for interpretable linear models via Bayesian inference. Priors are refinable through natural language. Outperforms in-context learning on low-label regimes and saves over 6 months of labelling effort in a real healthcare application (UTI detection from sensor data). |

---

## 🔬 LLM for Bayesian Optimization & Gaussian Processes

Papers on using Large Language Models to design acquisition functions, adapt GP kernels, or guide the Bayesian optimization loop.

| Paper | Venue | Year | Description |
|-------|-------|------|-------------|
| [EvolCAF: Evolve Cost-aware Acquisition Functions Using Large Language Models](https://arxiv.org/abs/2404.16906) | arXiv | 2024 | Integrates LLMs with evolutionary computation to automatically design cost-aware acquisition functions for Bayesian optimization. Uses crossover and mutation in algorithmic space to minimize reliance on domain expertise, outperforming human-designed EIpu and EI-cool across 12 synthetic and 3 real-world HPO tasks. |
| [FunBO: Discovering Acquisition Functions for Bayesian Optimization with FunSearch](https://openreview.net/pdf?id=XjbJR9374o) | ICML 2025 | 2025 | Uses FunSearch (LLM-driven program search) to discover novel acquisition functions written as executable code. Discovered AFs generalize both in- and out-of-distribution, outperforming established general-purpose AFs and rivaling task-specific learned AFs. |
| [CAKE: Adaptive Kernel Design for Bayesian Optimization with LLMs](https://arxiv.org/abs/2509.17998) | arXiv | 2025 | Proposes Context-Aware Kernel Evolution (CAKE), using LLMs as crossover/mutation operators to adaptively generate and refine GP kernels from observed data. Pairs with BAKER (BIC-based kernel ranking) to select the best kernel per iteration. Consistently outperforms baselines on HPO, controller tuning, and photonic chip design. |



