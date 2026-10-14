# TryAllAPI

**OpenAI-compatible multi-model API gateway** — one base URL, 300+ models (GPT, Claude, Gemini, DeepSeek, Grok, Qwen, Kimi, and more).

| | |
|---|---|
| **Website** | [https://tryallapi.com](https://tryallapi.com/) |
| **OpenAI-compatible Base URL** | `https://tryallapi.com/v1` |
| **Chat Completions** | `https://tryallapi.com/v1/chat/completions` |
| **Pricing** | [https://tryallapi.com/pricing](https://tryallapi.com/pricing) |
| **Docs** | [https://docs.tryallapi.com](https://docs.tryallapi.com/) |
| **API reference (Apifox)** | [https://5oq7d57fbk.apifox.cn](https://5oq7d57fbk.apifox.cn) |
| **Contact** | bgnwd15@gmail.com |

> **Disclaimer:** TryAllAPI is a **third-party API aggregator**. It is **not** affiliated with, endorsed by, or an official product of OpenAI, Anthropic, Google, or any other model vendor. Model availability and prices change; always trust the live console and [pricing page](https://tryallapi.com/pricing).

---

## What it is

TryAllAPI (on-site brand: MomoAPI / momoAPIPro) is a pay-as-you-go AI API aggregation platform:

- **One endpoint for many providers** — switch models by name; keep the same base URL and API key.
- **300+ models** — text, image, video, and music models from major vendors (catalog size changes; check the model plaza).
- **OpenAI-compatible** — drop-in for the official OpenAI SDK and most tools that speak `/v1`.
- **USD pay-as-you-go** — top up from a low minimum; balance does not expire (see site for current terms).

---

## Quick start

1. [Register](https://tryallapi.com/register) and log in.
2. [Top up](https://tryallapi.com/console/topup) if needed.
3. Create an API key in [console → tokens](https://tryallapi.com/console/token).
4. Point your client at `https://tryallapi.com/v1` and use the exact model id from the plaza / pricing page.

### Python

```python
from openai import OpenAI

client = OpenAI(
    api_key="YOUR_API_KEY",  # never commit real keys
    base_url="https://tryallapi.com/v1",
)

completion = client.chat.completions.create(
    model="gpt-4o",  # or any model id from the plaza
    messages=[{"role": "user", "content": "Hello"}],
)
print(completion.choices[0].message.content)
```

### Node.js

```javascript
import OpenAI from "openai";

const client = new OpenAI({
  apiKey: "YOUR_API_KEY", // never commit real keys
  baseURL: "https://tryallapi.com/v1",
});

const completion = await client.chat.completions.create({
  model: "gpt-4o",
  messages: [{ role: "user", content: "Hello" }],
});
console.log(completion.choices[0].message.content);
```

### cURL

```bash
curl https://tryallapi.com/v1/chat/completions \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "gpt-4o",
    "messages": [{"role": "user", "content": "Hello"}]
  }'
```

---

## Pricing

Billing is typically **official list price × group multiplier**, shown in **USD**. See the live list:

- **Pricing / model plaza:** [https://tryallapi.com/pricing](https://tryallapi.com/pricing)
- **Per-model guides:** [https://docs.tryallapi.com](https://docs.tryallapi.com/)

---

## Docs & guides

- Model call guides and price notes: [docs.tryallapi.com](https://docs.tryallapi.com/)
- OpenAPI / Apifox: [5oq7d57fbk.apifox.cn](https://5oq7d57fbk.apifox.cn)
- News / updates: [tryallapi.com/news](https://tryallapi.com/news)

---

## Security

- **Never commit API keys** or paste them into public issues/PRs.
- Prefer environment variables (`OPENAI_API_KEY`) or your secret store.
- Rotate a key immediately if it leaks.

---

## Related (optional integrations)

Client-specific how-tos (e.g. WorkBuddy) live in **separate** repos. This repository is the **standalone product README** for TryAllAPI — not a WorkBuddy (or other product) brand page.

---

## License

Documentation in this repository is provided as-is for public reference. The TryAllAPI service itself is operated at [tryallapi.com](https://tryallapi.com/); terms of use are those of the website.
