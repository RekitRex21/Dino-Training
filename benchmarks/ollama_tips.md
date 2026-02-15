# Ollama Performance Tips

## Speed Optimization
```bash
export OLLAMA_NUM_PARALLEL=2  # or 1-3
ollama run rex-dino-qwen3 --verbose "prompt"
```

## Repetition Loop Fix
```bash
ollama run rex-dino-qwen3
/set parameter repeat_penalty 1.2
/set parameter temperature 0.7
```

## Create Tuned Model
```bash
cat <<EOF > temp_modelfile
FROM rex-dino-qwen3
PARAMETER temperature 0.7
PARAMETER repeat_penalty 1.2
EOF
ollama create rex-dino-qwen3-tuned -f temp_modelfile
```

## API Call
```bash
curl http://localhost:11434/api/generate -d '{
  "model": "rex-dino-qwen3",
  "prompt": "your prompt",
  "options": {"temperature": 0.7, "repeat_penalty": 1.2},
  "stream": false
}'
```
