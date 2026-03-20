# Scalable, Context-Sensitive Psychiatric Assessment With Large Language Models and Brief Audio Diaries

This repository contains the public notebooks and outputs for the paper "Scalable, context-sensitive psychiatric assessment with large language models and brief audio diaries."

## Repository Contents

- `llm_prediction_per_domain_per_subject_per_day.ipynb`
  - Runs domain-level LLM scoring separately for each diary/transcript.
- `llm_prediction_reasoning_per_domain.ipynb`
  - Selects exemplar high- and low-scoring subjects for each domain.
  - Uses model-based reasoning to generate qualitative summaries.
- `Results/llm_prediction_per_domain_per_subject_per_day.csv`
  - Released daily diary domain predictions for 108 subjects across 1,337 diary rows.
  - Includes per-domain scores from 6 LLMs plus mean scores across those models.

## Domains

The notebooks score five broad DPDS domains:

- Negative Affectivity
- Antagonism
- Detachment
- Disinhibition
- Anankastia

## Released Output File

`Results/llm_prediction_per_domain_per_subject_per_day.csv` contains:

- `subject` and `day` identifiers
- Domain predictions from 6 LLMs:
  - `claude_sonnet_4`
  - `gemini_flash`
  - `gpt_5`
  - `grok3`
  - `llama_maverick`
  - `qwen3_235B`
- Mean domain scores across those 6 LLMs:
  - `neg_avg`
  - `ant_avg`
  - `det_avg`
  - `dis_avg`
  - `ank_avg`

## Running the Notebooks

This is a notebook-first project rather than a packaged Python library.

Typical workflow:

1. Clone the repository.
2. Create a Python environment with Jupyter.
3. Install the notebook dependencies.
4. Create a local `Data/` directory with the required restricted inputs.
5. Add your OpenRouter API key in the notebook before running model calls.

Core Python packages used by the notebooks include:

- `openai`
- `tiktoken`
- `requests`
- `numpy`
- `pandas`
- `jsonschema`
- `tenacity`
- `tqdm`
- `ipython`
- `jupyter`
