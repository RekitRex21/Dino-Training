# SWE-bench Performance Estimates for rex-dino-qwen3

## Overview
- Model: rex-dino-qwen3 (fine-tuned qwen3:1.7B)
- Hardware: Dell Latitude E6440 (older laptop, CPU-only)

## Estimated Performance on SWE-bench Verified

| Setup | Estimated % Resolved |
|-------|---------------------|
| Raw / zero-shot | 1-3% |
| With agent scaffold | 5-12% |
| Best-case fine-tuned + optimized | ~15% (easier splits) |

## Comparison with Other Small Models

| Model | Expected % |
|-------|------------|
| Tiny/small (0.5B-4B) | 0-8% (full), 10-20% (Mini) |
| Qwen3-4B base | 5-15% |
| Qwen3-8B / Qwen2.5-Coder-7B | 15-30% |
| Mid-large (32B+) | 40-55% |
| Top (2026) | 74% (Claude Opus) |

## Key Insights
- SWE-bench requires repo understanding, file editing, testing
- Small models struggle with long context and tool use
- 1.7B model ranks near bottom but better than random
- Great for local prototyping, not leaderboard competitive
