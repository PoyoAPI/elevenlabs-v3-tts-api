# ElevenLabs v3 TTS cURL Examples

Use these requests to submit a generation task and poll for the result.

## Text To Speech

```bash
export POYO_API_KEY="YOUR_POYO_API_KEY_HERE"
export POYO_BASE_URL="https://api.poyo.ai"

curl --fail-with-body --request POST \
  --url "$POYO_BASE_URL/api/generate/submit" \
  --header "Authorization: Bearer $POYO_API_KEY" \
  --header "Content-Type: application/json" \
  --data '{
  "model": "elevenlabs-v3-tts",
  "input": {
    "text": "This is a short product narration draft generated from a backend API workflow.",
    "voice": "Rachel",
    "stability": 0.45,
    "timestamps": true,
    "language_code": "en",
    "apply_text_normalization": "auto"
  }
}'
```

Store the returned `data.task_id`, then poll:

```bash
curl --fail-with-body --request GET \
  --url "$POYO_BASE_URL/api/generate/status/task-unified-example" \
  --header "Authorization: Bearer $POYO_API_KEY"
```

## Narration With Timestamps

```json
{
  "model": "elevenlabs-v3-tts",
  "input": {
    "text": "Use timestamps when the generated narration needs captions, editing markers, or timeline alignment.",
    "voice": "Rachel",
    "timestamps": true,
    "language_code": "en",
    "apply_text_normalization": "auto"
  }
}
```

## Expected Submit Response

```json
{
  "code": 200,
  "data": {
    "task_id": "task-unified-example",
    "status": "not_started",
    "created_time": "2026-07-04T08:00:00"
  }
}
```

## Expected Status Response

```json
{
  "code": 200,
  "data": {
    "task_id": "task-unified-example",
    "status": "finished",
    "progress": 100,
    "files": [
      {
        "file_url": "https://storage.poyo.ai/generated/output-file",
        "file_type": "media"
      }
    ],
    "error_message": null
  }
}
```
