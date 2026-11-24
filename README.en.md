# GPT-6.2 Does More

**🇧🇷 [Português](README.md) · 🇺🇸 [English](README.en.md) · 🇪🇸 [Español](README.es.md)**

[![GPT-6.2 Does More](guia/assets/banner-en.jpg)](https://linnoff88-dev.github.io/

## What it is

GPT-6.2 Does More is a living collection of tips for getting better results with Astra and Sol, OpenAI’s new models. It’s for people who delegate work to AI and want fewer interruptions and surprises. Each tip explains what to do, what kind of use it’s suited for, and, when it makes sense, includes ready-to-use text you can paste. The collection is based on official OpenAI publications, and new tips are added as they’re verified. Just read and copy.

## 📖 Guide

**https://linnoff88-dev.github.io/

The tips are in [`DICAS.md`](DICAS.md), and the ready-to-use text is in [`prompts/`](prompts/) (both in Portuguese; the English text is in the guide).

## Ask your AI to analyze your situation

```text
Read the tips at https://github.com/linnoff88-dev/gpt62-rende-mais/blob/main/DICAS.md. Then look at how I use AI here, including the instructions already in place, and explain in plain language: 1. Which tips solve a real problem for me? 2. Does any of my instructions get in GPT-6.2’s way? 3. What would you change first? Don’t change anything yet. If you can’t open the link or see my instructions, tell me what to paste here. Show me the plan and wait for me to say yes.
```

## Based on OpenAI publications

- [Using GPT-6.2](https://developers.openai.com/api/docs/guides/latest-model/gpt-6.2-astra): behavior, prompts, reasoning effort, and migration.
- [GPT-6.2 System Card](https://deploymentsafety.openai.com/gpt-6-2-astra-sol): omission of obstacles (22.28% for GPT-6.2 Astra and 11.09% for GPT-6 Astra, on programming tasks designed to provoke the error; this does not necessarily indicate the rate in real-world use) and the effect of the Codex prompt.
- [Rethinking skills and prompts for GPT-6 Astra](https://developers.openai.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra): written for the previous version; included here as a tip to test.

Verified on November 18, 2026. The text in `prompts/` was written by us.

---

## Technical setup

There’s nothing to install: copy the text from `prompts/` into your request, `AGENTS.md`, or system prompt.

When migrating an integration, the official documentation says to check:

| Item | What to do |
|---|---|
| Model | `gpt-6.2-astra` or `gpt-6.2-sol` |
| Reasoning effort | for a new integration, start with `medium`; if you use `none` or `minimal`, switch to `low` |
| Tools | use the Responses API |
| Parameters | remove `temperature`, `top_p`, and `top_logprobs`; in Chat Completions, also remove `logprobs`; in Responses, remove `message.output_text.logprobs` from `include` |
| Reasoning | don’t edit the start of the conversation between responses |
| Cache | when upgrading from GPT-5.5 or earlier, replace `prompt_cache_retention` with `prompt_cache_options.ttl` = `"30m"` |

To repeat the test, from the project directory and with Codex CLI authenticated via your subscription (`3` runs 12 executions; the script only saves the responses, and classification is done by reading each one):

```bash
teste/medir_bloqueio.sh 3 teste/nova-rodada
```

The results from November 18, 2026 are in [`teste/PROVA.md`](teste/PROVA.md) (in Portuguese).

## The process, from start to finish

🧠 = person with agent · ⚙️ = script · 🤖 = AI agent via subscription

| # | Step | Command / what happens | Who |
|---|---|---|---|
| 1 | A tip comes in | GitHub issue | community |
| 2 | Verify | read the official OpenAI publication or run your own test; third-party blogs, videos, and social media aren’t used as sources | 🧠 |
| 3 | Record | add it to `DICAS.md`, with the date and status; add new text to `prompts/` | 🧠 |
| 4 | Test, if appropriate | `teste/medir_bloqueio.sh 3 teste/nova-rodada` or a new test in `teste/` | ⚙️ / 🤖 |
| 5 | Update the guide | edit `guia/index.html` and regenerate `guia/en/` and `guia/es/` | 🧠 / 🤖 |
| 6 | Review | a reviewer who didn’t write the change reads the guide | 🤖 |
| 7 | Publish | commit + push; GitHub Pages publishes automatically | 🧠 |
| 8 | Share, if it’s major news | announce it on the ARCKHÉ AI portal and in the ARCKHÉ.LLMS group | 🧠 |

## License

MIT.
