# War of Machines — Privacy Policy

**Local-first · No telemetry · No tracking · User-controlled data**

This policy covers the War of Machines desktop application, version 0.1.1-beta and later, for all builds. Privacy is a permanent principle of the product: none of the collection described below as absent will be added without a new, explicit decision by the owner. Any such change would be announced in this policy.

## 1. What War of Machines does NOT do
RitualForge Labs does **not** receive or collect any of the following through the application:
- your conversations, tasks or AI answers;
- your API keys or files;
- your usage history;
- telemetry, diagnostics or crash reports.

The application also has:
- no registration or online account;
- no central server and no hidden intermediate servers;
- no analytics or tracking SDKs;
- no advertising;
- no fingerprinting and no device or user identifiers;
- no hidden collection of hardware or OS information.

Nothing is sent automatically: no history, logs, screenshots or databases.

## 2. What is stored locally, on your computer only
| What | Where |
|---|---|
| Local database `wom.sqlite3` | `~/.local/share/war-of-machines/data/` for the compiled Linux package. You can change this with the `WOM_DATA_DIR` environment variable. |
| Local log `wom.log` | Same folder |
| API keys | Your system keyring (Secret Service on Linux), service name `war-of-machines-ai-team`. Alternatively, environment variables that you set yourself. |

**The database** contains:
- your local owner account: user name plus a salted scrypt hash of the password, never the password itself;
- settings;
- your tasks and the AI conversations;
- token counts and cost estimates.

**The log** records technical events only. API keys, tokens and home-directory paths are redacted. Do not assume the log is fully anonymous; review it before you share it with anyone.

## 3. Cloud AI providers
When you start a discussion with cloud models (OpenAI, xAI, Anthropic, Google Gemini, Mistral, DeepSeek, OpenRouter):
- **The application sends your task and the conversation context directly from your computer to the providers you chose.** It uses your own API key for each provider.
- **What you type may contain personal data.** That content is processed by the provider under its own terms and privacy policy. RitualForge Labs is not a party to these requests and does not see them.
- **Paid requests need confirmation.** You confirm before paid requests are sent.

The same direct connection is used when you click "Check" in the provider settings to list the available models.

**Access routes (v0.2, test build).** Public model catalogs (OpenRouter, Hugging Face, local Ollama) are downloaded **only when you click "Refresh"** — never in the background or on a timer. The time of the last successful check is shown; if a catalog cannot be reached, the last saved copy is shown and marked as stale. The catalog cache is a local file in your data folder and contains no keys.
- **Hosts contacted by the route-catalog "Refresh":** only `openrouter.ai` (public model list), `huggingface.co` (public model list) and, for local Ollama, `127.0.0.1:11434`. Conversations go only to the provider/route you selected.
- **OpenRouter "Check limits"** sends one request (GET /api/v1/key) with your OpenRouter key, only when you click it. The result is shown and not stored; it is not a guaranteed balance.
- **Hugging Face Inference Providers** (router.huggingface.co, experimental) is used only if you choose it and enter your own token. Hugging Face and the inference provider process the request under their terms; usage may be billed even with a Hugging Face account.
- **Gemini free tier:** Google may use submitted content to improve its products. War of Machines asks for your explicit consent before the first use, stores only that choice (in your local settings), and lets you revoke it in "Route…". History and files are never sent automatically.
- **Sign in with ChatGPT** is not active; no sign-in or tokens are used. War of Machines never reads, copies or extracts browser or ChatGPT session cookies or tokens.

## 4. Ollama (local models)
- In local mode (the default address is `http://127.0.0.1:11434`), requests go only to the Ollama server on your own computer. Nothing is sent to the cloud.
- If you change the Ollama address yourself, requests go to the address you set.

## 5. Update check: user-controlled
- **Off at startup by default.** There is no automatic update check at startup. A check happens only when you click "Check now", or at startup if you turned on "Check automatically at startup" yourself.
- **What is sent.** The check is one plain, read-only request: `GET https://api.github.com/repos/PhoenixbgOrg/war-of-machines/releases`.
  - It contains no keys, history, files or identifiers.
  - It sends only a generic `User-Agent: WarOfMachines-Updater`, with no version or OS details.
- **Installation.** Nothing is installed automatically.

## 6. Links and voluntary support
- **Links open only when you click them**, in your own browser:
  - the PayPal.Me support page (`https://paypal.me/Hristov375`);
  - the project websites;
  - this privacy policy on GitHub.

  The application itself does not contact these sites.
- **Payments.** Donations are voluntary and are handled entirely by PayPal under PayPal's own terms. The application stores no payment information.

## 7. Optional local API
The optional local HTTP API (start option `--api`) listens only on `127.0.0.1` (port 8765 by default) and requires a login token. It is not reachable from other computers.

## 8. Managing and deleting your data
- **Delete a single API key:** in the Providers dialog, or in your keyring manager.
- **Delete all local data:** close the application and delete the folder `~/.local/share/war-of-machines/data`, or your `WOM_DATA_DIR`.
- **Updating:** the installer moves the old program folder aside and keeps your data and keys.
- **Uninstalling:** `uninstall.sh` removes only the program files. It does **not** delete your history, database, log or keyring entries. You delete those yourself, only if you want to.

## 9. Things you send voluntarily
If you choose to contact us, these services process your personal data under their own terms. This includes at least your e-mail address, your GitHub account and any content you include.
- e-mail to info@ritualforgelabs.com;
- a GitHub Issue;
- the optional "Does this route work?" report: on click it only opens a prefilled GitHub Issue or e-mail in your own browser or mail program. It contains only the fields you see and can edit (provider, route, model id, app version, optional OS family, result) — no conversations, keys or file paths. Nothing is sent unless you submit it yourself;
- a PayPal payment.

Please do not include API keys, private conversations or personal paths in bug reports or screenshots.

## 10. Notes
- **IP addresses.** External services that you connect to (AI providers, GitHub, PayPal, your browser's sites) may receive and process your IP address independently.
- **What this policy does not claim.** It does not claim that no personal data is ever processed anywhere. It describes what the application does. This policy is not a GDPR certification.
- **Platforms.** The policy applies to all builds: Debian and other Linux distributions, Windows 10/11, x86-64, ARM64 and experimental builds.

Contact: info@ritualforgelabs.com
