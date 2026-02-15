# Local Model Benchmarks - Dino AI
# Generated: 2026-02-15

## Benchmark Summary

| Model | Base | TPS | Load Time | Total Time | Tokens |
|-------|------|-----|-----------|------------|--------|
| **rex-dino-qwen3** | **qwen3:1.7b** | **8.19 tok/s** | **2.18s** | **1m13s** | **403** |
| rex-dino | phi3:mini | 5.02 tok/s | 32.6s | 2m44s | 615 |
| rex-dino-qwen3 | qwen3:8b | 4.85 tok/s | 48s | 2m46s | 523 |
| rex-dino-qwen3:4b | qwen3:4b | 2.41 tok/s | 53.5s | 23m12s | 3090 |

## WINNER: qwen3:1.7b 🏆

## Details

### Test Command
```bash
ollama run [model] "Write a 200-word story about robots" --verbose
```

### rex-dino-qwen3 (qwen3:1.7b) - CHAMPION! 🏆
- **Date**: 2026-02-15
- **Model**: rex-dino-qwen3 (qwen3:1.7b base)
- **TPS**: 8.19 tokens/second ⭐ NEW BEST!
- **Load Duration**: 2.18 seconds ⭐ NEW BEST!
- **Total Duration**: 1m13s ⭐ NEW BEST!
- **Prompt Eval Rate**: 15.63 tokens/s
- **Eval Count**: 403 tokens

### rex-dino (phi3:mini)
- **Date**: 2026-02-14
- **Model**: rex-dino:latest (phi3:mini base)
- **TPS**: 5.02 tokens/second
- **Load Duration**: 32.620 seconds
- **Total Duration**: 2m44.23s
- **Prompt Eval Rate**: 7.07 tokens/s
- **Eval Count**: 615 tokens

### rex-dino-qwen3 (qwen3:8b)
- **Date**: 2026-02-14
- **Model**: rex-dino-qwen3:latest (qwen3:8b base)
- **TPS**: 4.85 tokens/second
- **Load Duration**: 48.09 seconds
- **Total Duration**: 2m46.35s
- **Prompt Eval Rate**: 6.74 tokens/s
- **Eval Count**: 523 tokens

### rex-dino-qwen3:4b (qwen3:4b) - SLOWEST
- **Date**: 2026-02-15
- **Model**: rex-dino-qwen3:4b (qwen3:4b base)
- **TPS**: 2.41 tokens/second
- **Load Duration**: 53.46 seconds
- **Total Duration**: 23m12.14s
- **Prompt Eval Rate**: 6.24 tokens/s
- **Eval Count**: 3090 tokens

## System Specs (for reference)
- CPU: Intel E6440 (Haswell 4th gen, 4 cores)
- RAM: 8GB
- Storage: HDD
- OS: Fedora (customized)

## Conclusions

1. **qwen3:1.7b is the CHAMPION** - 8.19 TPS, 2s load!
2. **phi3:mini is second** - 5 TPS but 32s load
3. **qwen3:8b is third** - similar speed but 48s load
4. **qwen3:4b is TOO SLOW** - only 2.4 TPS!

## Recommendation

**Use qwen3:1.7b (rex-dino-qwen3)** for CPU inference:
- Fastest TPS (8.19)
- Fastest load (2.18s)
- Small model size (~1.7GB)
- Best performance on consumer hardware

## Tips for Faster Performance
1. Limit threads: `export OLLAMA_NUM_PARALLEL=2`
2. Use Q4 quantization for 20-30% speed gain
3. Shorter prompts for quicker tests
