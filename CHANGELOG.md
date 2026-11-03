# Changelog

Bulgarian: [CHANGELOG_BG.md](CHANGELOG_BG.md)

## 0.2.0-beta.1 — 2026-11-03 (TEST BUILD, pre-release)
- Universal AI Pool: access-route catalog per model (OpenRouter, Hugging Face, Ollama, direct vendors); labels free / limited quota / subscription / paid / local / unknown / not available; "Unknown" instead of invented prices.
- Catalog refresh only via the Refresh buttons; time of the last successful check shown; stale data clearly marked when a catalog is unreachable.
- Route picker per participant ("Route…"); paid or unknown-cost routes need confirmation; never an automatic switch to a paid route.
- The participant setup (provider, model, chosen route) is saved locally and restored after closing and reopening the program (no keys are stored there).
- Hugging Face monthly credits are no longer hardcoded: shown as "Unknown" with a link to your HF billing page (HF removed included credits for free users on 2026-10-07).
- Exact provider / model / route recorded for every message (additive DB migration; old history kept and shown as "Unknown"); shown in the discussion view and export.
- Hugging Face Inference Providers (router.huggingface.co/v1) as a provider — EXPERIMENTAL (tested with fake servers only). Labels: free credits / paid usage / own provider key / unknown.
- OpenRouter "Check limits" (GET /api/v1/key) — key credit limit, remaining, free-model daily requests; clear 402/429 messages; missing values shown as "Unknown".
- Gemini Free: explicit one-time consent to Google's data use, stored locally, revocable.
- Sign in with ChatGPT: shown as "Not available yet" (awaiting OpenAI confirmation); no authentication is active.
- Voluntary "Does this route work?" report: opens a prefilled GitHub issue or e-mail only on click; contains only the fields you see and edit.
- Version shown in the title bar and main window; "What's New" shown once after an update; bilingual changelog; version consistency check.
- Mode B / Consensus Engine v0.4: still not implemented.

## 0.1.1-beta — 2026-11-02 (Public Beta, pre-release)
- Privacy by design: no telemetry or tracking; automatic update check at startup is off by default; no request identifier sent to cloud providers; stronger log redaction; privacy note in About. See PRIVACY_EN.md / PRIVACY_BG.md.
- Licence: War of Machines Freeware License v1.0 (LICENSE).
- Поверителност по замисъл: без телеметрия и проследяване; автоматичната проверка за обновления е изключена по подразбиране; бележка за поверителност в „За проекта“. Лиценз: War of Machines Freeware License v1.0.

- New official project page with a clean history (this repository).
- About window shows the build type, version and Git commit.
- English/Bulgarian interface; separate AI discussion language.
- Providers: OpenAI, xAI, Anthropic, Google Gemini, Mistral, DeepSeek, OpenRouter, optional local Ollama; dynamic model catalog.
- Voluntary support: the "Support via PayPal" button in About opens the PayPal.Me page (https://paypal.me/Hristov375) in your browser; nothing is copied to the clipboard.
- Mode A (AI Team) available. Mode B / Consensus Engine v0.4 not implemented.
- Planned licence: War of Machines Freeware License (final text pending owner approval).

BG: 0.1.1-beta — неиздадена (подготвена, не е публикувана). Нова официална страница с чиста история; „За проекта“ показва тип компилация, версия и commit; BG/EN интерфейс и отделен език на дискусията; бутонът „Подкрепи чрез PayPal“ отваря страницата PayPal.Me (https://paypal.me/Hristov375) в браузъра; режим A е наличен, режим B не е реализиран; планиран лиценз War of Machines Freeware License (очаква одобрение).
