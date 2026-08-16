# Free API - OpenAI & Anthropic Compatible API

[中文](README.md) | [English](README_EN.md)

Free API is a public, no-cost API service compatible with both OpenAI API and Anthropic Messages API formats.

## Quick Links

| Item | Link |
|------|------|
| Web Chat | [Online Demo](https://rp.good.hidns.vip) |


## API Information

| Item | Value |
|------|-------|
| Base URL | `https://openai.good.hidns.vip/v1` |
| API Key | `https://github.com/smanx/free-api` |

> This API key is publicly shared. Do not rely on it for production workloads or other critical use cases.


## Supported Models ([Status Page](https://status.good.hidns.vip))

![Model Status](https://s.wordpress.com/mshots/v1/https://status.good.hidns.vip?w=1280&h=660)

## Supported Endpoints

- `/v1/models` - Model list
- `/v1/chat/completions` - Chat completions
- `/v1/images/generations` - Image generation
- `/v1/messages` - Anthropic Messages API (Claude SDK compatible)

## Minimal Example

Copy and run the following command in your terminal:

```bash
curl https://openai.good.hidns.vip/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer https://github.com/smanx/free-api" \
  -d '{
    "model": "gpt-5.2",
    "messages": [
      {
        "role": "user",
        "content": "Hello, please briefly introduce yourself."
      }
    ]
  }'
```

### Image generation (/v1/images/generations)

> ⚠️ **Grok image generation is deprecated**. For image generation, please use Qwen or refer to: [https://github.com/smanx/qwen2api](https://github.com/smanx/qwen2api)

~~> Currently, image generation requires model: `grok-imagine-1.0`~~

Currently only `response_format: "b64_json"` is supported (returns base64).

Allowed `size` values:
- `1024x1024`
- `1024x1792`
- `1792x1024`
- `1280x720`
- `720x1280`

#### Return base64 (minimal example)

```bash
curl https://openai.good.hidns.vip/v1/images/generations \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer https://github.com/smanx/free-api" \
  -d '{
    "model": "grok-imagine-1.0",
    "prompt": "A minimal flat icon of a rocket, white background",
    "n": 1,
    "size": "1024x1024",
    "response_format": "b64_json"
  }'
```

> For Qwen image generation and video recognition, please refer to: [https://github.com/smanx/qwen2api](https://github.com/smanx/qwen2api)

## Notes

- This service is provided free of charge for personal use. Please use it responsibly.
- Rate limit: each IP can make up to 5 requests within 10 seconds. Exceeding this limit will trigger a 10-second restriction. This policy may change in the future.
- Do not submit sensitive information, personal data, or important business content.
- This project does not collect user information. If you still have concerns, please do not use the service.
- Future changes will be announced in this repository.
