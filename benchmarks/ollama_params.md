# Ollama CLI Parameters Guide

## Known Limitations
- `ollama run` does NOT support `--repeat-penalty`, `--temperature` as CLI flags
- These options only work via:
  - Modelfile when creating model
  - API (/api/generate or /api/chat)
  - Interactive mode with slash commands

## Interactive Mode Fix
```bash
# Start interactive session
ollama run rex-dino-qwen3

# Set parameters (in session)
/set parameter repeat_penalty 1.2
/set parameter temperature 0.7

# Then paste your prompt
```

## Alternative: Create Tuned Model Variant
```bash
cat <<EOF > temp_modelfile
FROM rex-dino-qwen3
PARAMETER temperature 0.7
PARAMETER repeat_penalty 1.2
PARAMETER top_p 0.9
EOF

ollama create rex-dino-qwen3-tuned -f temp_modelfile
ollama run rex-dino-qwen3-tuned --verbose "prompt"
```

## API Workaround
```bash
curl http://localhost:11434/api/generate -d '{
  "model": "rex-dino-qwen3",
  "prompt": "YOUR PROMPT",
  "options": {
    "temperature": 0.7,
    "repeat_penalty": 1.2
  },
  "stream": false
}'
```

## Quick Summary
- Use interactive mode + /set for parameter tuning
- Or create a tuned model variant with Modelfile
- CLI flags don't work for sampling parameters
