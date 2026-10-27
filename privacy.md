# Talent Matcher privacy and data handling

Updated: 27 October 2026. This policy describes Talent Matcher version 1.3.0.

## What the extension processes

Talent Matcher reads candidate fields displayed on supported SEEK Talent Search and LinkedIn Recruiter pages to provide recruiter-requested match scores. It also stores the position description you enter and, on SEEK, tracks repeat viewport sightings of stable profile IDs.

There is no developer-operated collection service, advertising SDK or analytics backend in this extension. That does not mean data never leaves your device: requested ranking sends the job description and scraped candidate fields to your selected AI provider.

## Local storage

- Provider settings and Gemini/GLM keys are stored in extension-local browser storage, not newly written to Chrome Sync. Older synced configuration is migrated locally and verified before the synced source is removed.
- Settings for different providers remain separate. Account/provider switching does not transfer one provider's key to another.
- The saved position description remains in local extension storage until replaced, cleared, or extension data is removed.
- Seen history persists stable SEEK profile IDs, counts and last-seen timestamps. Profile IDs can still identify people within SEEK and should be treated as personal data. Names, search/service tokens and full profiles are not written to that history store.
- Scraped candidate fields and displayed match results are processed in memory. They are not intentionally persisted as full candidate profiles by the extension.

Browser-local storage is not a separate encrypted vault. Protect the device and browser profile. Code limits direct access to trusted extension contexts and public configuration responses report key presence instead of keys, but these controls are not a guarantee against a compromised device or browser.

## AI providers

Gemini and GLM ranking transmit the saved position description and relevant candidate fields directly to the configured provider over HTTPS when you request ranking. Batch requests include the profile ID, name, title, location and available summary. Single-profile requests can include name, title, previous title, summary, current role/company, location, salary information, skills, work-history role/company/descriptions and certifications where available. These are personal data, even when already visible to your recruiting account.

Your API key is sent to the selected provider for authentication, including model discovery, connection tests and ranking. Model refresh requests the provider's model catalogue, not candidate analysis. A connection test sends a small test prompt and may consume provider usage. Saving a position description stores its original text locally; it does not itself request an AI summary. The extension does not automatically fall back to a different provider.

Provider policies and retention are outside this extension's control:

- Google Gemini: https://policies.google.com/privacy and https://ai.google.dev/
- GLM/Zhipu/z.ai: consult the current privacy and account terms at https://open.bigmodel.cn and https://api.z.ai/

Review your organisation's recruitment/privacy obligations before transmitting candidate information. AI scores can be wrong or reflect incomplete profile information; do not treat them as automatic hiring decisions.

## Optional ChatGPT account helper

ChatGPT linking uses the official local Codex app-server through a separately installed Native Messaging helper. Sign-in occurs on OpenAI's official authorization page. Credentials are stored in Talent Matcher's private helper directory, not extension storage, and are not imported from Hermes, another Codex app or ChatGPT browser cookies.

The current helper supports account linking and official model-catalog discovery. ChatGPT scoring is intentionally disabled because the installed Codex integration cannot verify a tools-disabled inference session. It does not start a ChatGPT ranking thread.

Subscription sign-in and API-key billing are separate. OpenAI's policies and workspace rules apply to account access: https://openai.com/policies/privacy-policy/.

## Seen badges are not eye tracking

A badge measures a qualified card appearance in a focused, visible viewport. It cannot know whether you looked at or read the profile. Repeated IDs are flagged visually; profiles are not automatically hidden or rejected.

## Removing data

Clear or replace the saved position description through the popup. Disconnect ChatGPT through Settings to sign out of Talent Matcher's owned helper account. Removing the extension/browser extension data removes its local settings and seen history. Removing a Chrome extension does not by itself remove the separately installed native helper or its local directory; see native/README.md for its owned registration removal instructions.

Do not upload real candidate HTML captures, credentials or callback URLs to public issues. Development captures in a source checkout are separate files, not part of the extension's runtime storage, and are excluded by the release build.

## Purpose, retention and support

Data is used to provide the candidate-comparison and repeat-profile features described here, not for advertising, sale, unrelated profiling or credit/lending eligibility. The extension does not provide the developer with routine access to candidate data. A user-triggered copy action writes selected candidate names to the system clipboard; clipboard history or other applications may retain them.

Local settings, the saved position description and seen history have no automatic expiry in the current implementation. They remain until changed or the applicable extension data is removed. Provider-side retention, training use and deletion rights depend on the provider, account tier and terms; this extension cannot delete provider-held request records. Do not assume API submission is excluded from training or immediately deleted.

For privacy questions or support, open an issue at the public publisher support page: https://github.com/Jackson-G2/candidate-ranker-privacy/issues. Do not include candidate information, API keys, account credentials or authorization URLs in support requests.
