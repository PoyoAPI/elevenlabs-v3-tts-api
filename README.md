# ElevenLabs v3 TTS API Examples for PoYo

[![Model page](https://img.shields.io/badge/Model%20page-elevenlabs--v3--tts-84cc16)](https://poyo.ai/models/elevenlabs-v3-tts)
[![API docs](https://img.shields.io/badge/API%20docs-docs.poyo.ai-22d3ee)](https://docs.poyo.ai/api-manual/music-series/elevenlabs-v3-tts)
[![License: MIT](https://img.shields.io/badge/License-MIT-111827)](LICENSE)
[![Main examples](https://img.shields.io/badge/Main%20examples-PoyoAPI%2Fpoyo--examples-0f172a?logo=github)](https://github.com/PoyoAPI/poyo-examples)

Focused server-side examples for building expressive text-to-speech workflows with ElevenLabs v3 TTS on PoYo.

ElevenLabs v3 TTS is useful for creator tools, product narration, voiceovers, dialogue drafts, and apps that need generated speech as part of a larger media workflow.

[Model Page](https://poyo.ai/models/elevenlabs-v3-tts) | [Docs](https://docs.poyo.ai/api-manual/music-series/elevenlabs-v3-tts) | [Get API Key](https://poyo.ai/dashboard/api-key) | [Pricing](https://poyo.ai/pricing) | [Main Examples](https://github.com/PoyoAPI/poyo-examples)

## What This Repo Covers

- Text-to-speech with `elevenlabs-v3-tts`
- Voice and stability controls
- Optional timestamps for downstream editing
- Polling and webhook handling for production audio generation
- cURL and Node.js backend examples

## Quick Start

```bash
cp .env.example .env
export POYO_API_KEY="your-api-key"
```

Run the Node.js example:

```bash
cd node
npm start
```

Keep `POYO_API_KEY` on the server. Do not expose it in browser code, mobile apps, screenshots, or public logs.

## Production Pattern

- Keep `POYO_API_KEY` on the server
- Submit a generation task
- Store `data.task_id`
- Poll status while testing
- Use `callback_url` webhooks in production

## Models

This repo uses `elevenlabs-v3-tts`.

## Examples

| Path | What it covers |
| --- | --- |
| [`curl/generate.md`](curl/generate.md) | Copy-paste API request. |
| [`node/`](node/) | Native Node.js backend example. |
| [`docs/prompt-examples.md`](docs/prompt-examples.md) | Practical prompts for product workflows and creative tests. |
| [`docs/production-notes.md`](docs/production-notes.md) | Security and reliability notes before launch. |
| [`webhooks/express-webhook/`](webhooks/express-webhook/) | Minimal Express receiver for PoYo callbacks. |

## Run Checks

```bash
make check
```

On Windows:

```powershell
./scripts/check.ps1
```

## License

MIT
