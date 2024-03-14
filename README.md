# HumanExtension

Official code for Exploring Language Model’s Code Generation Ability with Auxiliary Functions (NAACL 2024, Findings)

## Experimental setup

| Model | Size (B) | Huggingface identifier |
|-------|----------|------------------------|
| InCoder | 1 | `facebook/incoder-1B` |
| InCoder | 6 | `facebook/incoder-6B` |
| CodeGenMulti | 2 | `Salesforce/codegen-2B-multi` |
| CodeGenMulti | 16 | `Salesforce/codegen-16B-multi` |
| CodeGenMono | 2 | `Salesforce/codegen-2B-mono` |
| CodeGenMono | 16 | `Salesforce/codegen-16B-multi` |
| SantaCoder | 1 | `bigcode/santacoder` |
| StarCoder | 16 | `bigcode/starcoder` |
| CodeLLaMA | 7 | `codellama/CodeLlama-7b-hf` |
| CodeLLaMA | 13 | `codellama/CodeLlama-13b-hf` |
| CodeLLaMA | 34 | `codellama/CodeLlama-34b-hf` |
| CodeLLaMAPython | 7 | `codellama/CodeLlama-7b-Python-hf` |
| CodeLLaMAPython | 13 | `codellama/CodeLlama-13b-Python-hf` |
| CodeLLaMAPython | 34 | `codellama/CodeLlama-34b-Python-hf` |
| CodeLLaMAInstruct | 7 | `codellama/CodeLlama-7b-Instruct-hf` |
| CodeLLaMAInstruct | 13 | `codellama/CodeLlama-13b-Instruct-hf` |
| CodeLLaMAInstruct | 34 | `codellama/CodeLlama-34b-Instruct-hf` |

## Warmup. Reproduce HumanEval result

```bash
PYTHONPATH=. python examples/run.py \
  --dataset humaneval \
  --method direct \
  --model facebook/incoder-1B \
  --output_dirpath outputs
```

## Evaluation

```bash
PYTHONPATH=. python examples/run.py \
  --dataset humanextension \
  --method direct \
  --model facebook/incoder-1B \
  --output_dirpath outputs

PYTHONPATH=. python examples/run.py \
  --dataset humanextension \
  --method irrelevant \
  --model facebook/incoder-1B \
  --output_dirpath outputs

PYTHONPATH=. python examples/run.py \
  --dataset humanextension \
  --method step_by_step \
  --model facebook/incoder-1B \
  --output_dirpath outputs

PYTHONPATH=. python examples/run.py \
  --dataset humanextension \
  --method oracle \
  --model facebook/incoder-1B \
  --output_dirpath outputs
```
