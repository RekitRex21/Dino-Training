# Qwen3 Repetition Loop Fix

When rex-dino-qwen3 gets stuck in repetition loop:

## Symptoms
- Repeats phrases like "Final Answer", "boxed code", self-reinforcing comments
- Common with Qwen3 quantized models (Q4/Q5 GGUF)

## Fixes

### 1. Use Repetition Penalty
```bash
ollama run rex-dino-qwen3 --verbose --repeat-penalty 1.2 "your prompt"
```

### 2. Add Temperature
```bash
ollama run rex-dino-qwen3 --verbose --temperature 0.7 --repeat-penalty 1.15 "prompt"
```

### 3. Limit Context
```bash
ollama run rex-dino-qwen3 --verbose --num-ctx 4096 "prompt"
```

### 4. Kill Stuck Process
```bash
pkill -f ollama
# or Ctrl+C in terminal
```

## Prevention in Prompts
Add to coding prompts:
"Do not use boxed answers or repeat phrases like 'Final Answer'. Output only the function code and brief explanation."

## Notes
- Default temperature is low (~0.0-0.2) - very deterministic, prone to loops
- 0.7-1.0 adds creativity to escape loops
- Repetition penalty 1.1-1.3 is recommended
