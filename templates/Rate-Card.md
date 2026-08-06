# Rate card (local / contract overrides)

Copy to `{PACK_ROOT}/rate-card.md` or `{PROJECTS_DIR}/<slug>/rate-card.md` and edit.  
**List rates below are estimates** until replaced with your contract or API-reported figures.

## Meta

- **Effective date:** YYYY-MM-DD
- **Plan:** API | ChatGPT Business | ChatGPT Enterprise | mixed
- **USD per credit (if known):** e.g. 0.04  
  Leave blank to compute USD only from API token prices.
- **Notes:** volume discounts, overage rate, Scale Tier — document here

## Codex / ChatGPT credits per 1M tokens (example list — verify against current OpenAI rate card)

| Model | Input | Cached input | Output |
|-------|------:|-------------:|-------:|
| (fill from current Codex rate card) | | | |

Formula (credits):

```text
credits ≈ (tok_in/1e6)*rate_in + (tok_cached/1e6)*rate_cached + (tok_out/1e6)*rate_out
```

Fast mode may multiply credit burn (check current OpenAI docs).

## API USD per 1M tokens (example list — verify against platform pricing)

| Model | Input USD | Cached input USD | Output USD |
|-------|----------:|-----------------:|-----------:|
| (fill from platform.openai.com pricing) | | | |

## Conversion policy

1. If `USD per credit` set → `usd_estimate = credits * usd_per_credit`
2. Else if API token rates set → price from tokens
3. Prefer **API Costs endpoint / export** over estimate when available
4. Invoice always wins for “actual spend”

## Mapping pack project → OpenAI project

| Pack slug | OpenAI project_id or API key label |
|-----------|-------------------------------------|
| | |
