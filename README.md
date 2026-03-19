# Prompt Privacy Shield

Prompt Privacy Shield is a browser extension that helps detect and mask sensitive information in text before it is sent to AI tools.
The extension runs locally in the browser, does not use AI, and does not collect user data. Its goal is to reduce the risk of accidentally sending sensitive information such as email addresses, phone numbers, IBANs, card-related data, API keys, crypto wallet addresses, and similar patterns while sharing prompts.

## What it does
- Helps detect common types of sensitive data in prompts
- Masks detected content to produce safer output
- Adds a Clean Prompt button on supported AI sites to sanitize prompts directly before sending
- Can also protect custom sensitive words defined by the user
- Uses a modular architecture with a shared detection engine for consistent results across all features

## What it can detect
- Email addresses
- Phone numbers (TR, DE, GB, FR, NL, US and international formats)
- IBANs and payment-related patterns (60+ countries)
- API keys and tokens (OpenAI, GitHub, AWS, Google, JWT and more)
- Bank card numbers (with Luhn validation)
- Crypto wallet addresses (BTC, ETH, LTC, TRX, SOL)
- SSN and ABA routing numbers (US)
- VAT numbers (EU — DE, FR, GB, NL, ES, IT, PL, SE, BE, AT)
- Custom sensitive words and phrases defined by the user

## How to use
Prompt Privacy Shield can be used in three ways:
1. **Extension popup** — Open the extension, paste text, click Scan & Clean, then copy the result
2. **Clean Prompt button** — On supported AI sites, use the floating button at the bottom right to sanitize your prompt directly before sending
3. **Right-click menu** — Select text on any web page and use "Sanitize & Copy" from the right-click menu

### Supported AI sites
- ChatGPT (chatgpt.com)
- Claude (claude.ai)
- Google Gemini (gemini.google.com)
- DeepSeek (chat.deepseek.com)
- Mistral (chat.mistral.ai)
- Grok (grok.com)

The extension also includes smart textarea detection that may work on other AI sites not listed above.

## How it works
The extension processes user-provided text locally inside the browser.
Its workflow is simple:
1. The user pastes text into the popup, uses the Clean Prompt button on a supported AI site, or selects text on a web page
2. The extension scans the text locally using its shared detection engine
3. It looks for potentially sensitive patterns using rule-based matching and validation checks (Luhn algorithm for credit cards, MOD-97 for IBANs, checksum for ABA routing numbers, etc.)
4. Context scoring helps distinguish real sensitive data from false positives by analyzing surrounding text
5. Detected matches are replaced according to the selected masking style (full or partial)
6. The sanitized result can then be reviewed by the user before sharing

## Architecture
The extension uses a modular design:
- **core.js** — Shared detection engine containing all validation, regex patterns, normalization, and sanitization logic
- **content.js** — Injects the Clean Prompt button on supported AI sites, uses the shared engine for sanitization
- **background.js** — Handles the right-click context menu, injects the shared engine for sanitization
- **popup.js** — Popup UI logic, uses the shared engine for Scan & Clean functionality

## Privacy approach
Prompt Privacy Shield is designed as a privacy-focused tool.
- All processing happens locally in the browser
- No AI model or cloud processing is used
- No user data is collected
- Scanned text is not sent to remote servers
- No data is used for advertising, tracking, or profiling
- Settings are stored only in local browser storage

## Limitations
Prompt Privacy Shield uses a rule-based detection approach. It provides a practical and lightweight privacy layer, but it is not perfect.
- It does not use AI or semantic context analysis
- It may not catch every sensitive pattern
- It may sometimes produce false positives or false negatives
- Sanitized output should always be reviewed before sending sensitive content

## Permissions
The extension requests only the minimum permissions needed for its core features:
- **activeTab** — to work with text from the active tab after direct user interaction
- **scripting** — to run local sanitization logic in the page context when needed
- **storage** — to save user preferences and custom protected words locally
- **contextMenus** — to provide the Sanitize & Copy right-click action
- **Host access on supported AI sites** — to show the Clean Prompt button and sanitize prompts in place

## Changelog

### v1.2.0
- Refactored to modular architecture with shared `core.js` engine
- Fixed text formatting issues on ChatGPT (ProseMirror paragraph handling)
- Fixed "Sanitize & Copy" preserving line breaks correctly
- Improved textarea detection with smart fallback for unknown AI sites
- Tightened Solana wallet regex to reduce false positives
- Made DeepSeek selector more robust against UI updates
- Added error handling for restricted pages in context menu
- Expanded IBAN country support to 60+ countries

### v1.1.0
- Initial public release
- Support for 7 data types and 6 AI sites
- Popup, Clean Prompt button, and right-click menu

## Feedback
Examples of missed detections, incorrect masking, or unexpected behavior are especially valuable.
Useful feedback includes:
- false positive examples
- false negative examples
- edge-case data formats
- different language and country-specific formats

If you want to report missed detections, incorrect masking, or unexpected behavior, you can use this form:
[Submit feedback](https://forms.gle/N4KEvpqEVu2En1xp6)

## Privacy Policy
Privacy Policy: [https://batuhanberk06.github.io/prompt-privacy-shield-privacy/](https://batuhanberk06.github.io/prompt-privacy-shield-privacy/)
