# Object Hallucination in Vision-Language Models

This repository contains a focused study of object hallucination in open vision-language models (VLMs). The goal is to analyze when and why a model describes objects that are not actually present in the image, and to study how this behavior depends on visual evidence, prompt formulation, scene complexity, and language priors.

The paper for this project is included in the repository as:
- `paper.pdf`

## Problem statement

Vision-language models (VLMs) can produce fluent descriptions and answers that are not fully supported by the image. We focus on one specific failure mode: object hallucination, where a model claims that an object is present even though it is absent under the chosen ground-truth annotation.

For example, an image containing a dog and frisbee may produce “dog, frisbee, tennis ball”; the tennis ball is hallucinated. Missing an object is an omission, calling a dog a cat is a recognition error, changing a red car to blue is an attribute error, and reversing a spatial relation is a relation error. Keeping these categories separate lets us ask a more useful question: when visual evidence becomes uncertain or incomplete, what does a VLM rely on when generating an answer?

We are interested in empirical understanding rather than architecture design. We can vary visual and linguistic conditions, compare publicly available models, and examine whether consistent patterns emerge across benchmarks and model families.

## Research objective

We investigate when and why object hallucination occurs in open VLMs, with particular attention to:

- visual evidence
- scene complexity
- language priors
- object frequency and co-occurrence
- prompt formulation
- model characteristics

The project can include controlled experiments, benchmark evaluations, and ablation studies to understand the root causes of hallucinated object predictions.

## Repository structure

- `Datasets/` - dataset folders or evaluation data
- `notebooks/` - analysis and experiment notebooks
- `results/` - experiment outputs, plots, and result artifacts
- `paper.pdf` - project paper

## Simple setup

1. Clone the repository.
2. Create a virtual environment.
3. Install the required Python dependencies.

Example:

```bash
python -m venv .venv
source .venv/bin/activate   # On Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install torch torchvision transformers pillow matplotlib pandas numpy jupyter
```

If your project uses additional dependencies, install them as needed from the notebook or script headers.

## Before running experiments

Important: update the file paths in scripts and notebooks before executing any experiment.

Common paths you may need to change:

- dataset directory
- model checkpoint path
- output/results directory
- cache directory
- annotation files

Example variables to update:

```python
DATA_DIR = "/path/to/your/Datasets"
RESULTS_DIR = "/path/to/your/results"
MODEL_DIR = "/path/to/your/checkpoints"
```

If you are using notebooks, check the first few cells and modify all absolute paths before running the cells.

## Running the project

- Open the notebooks in `notebooks/`
- Update the paths in the notebook configuration cells
- Run the notebook or script
- Save outputs to `results/`

## Notes

- This repository is intended for research and experimentation.
- Results depend on the specific model, dataset, and evaluation setup.
- Always confirm that local paths and checkpoints are valid before running longer experiments.

## Citation / references

See the included `paper.pdf` for the full write-up and literature references related to object hallucination in VLMs.
