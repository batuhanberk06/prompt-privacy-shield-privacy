# Prompt Privacy Shield

Prompt Privacy Shield is a browser extension that helps detect and mask sensitive information in text before it is sent to AI tools.

The extension **runs locally in the browser**, **does not use AI**, and **does not collect user data**. Its goal is to reduce the risk of accidentally sending sensitive information such as email addresses, phone numbers, IBANs, card-related data, API keys, crypto wallet addresses, and similar patterns while sharing prompts.

## What it does

- Helps detect common types of sensitive data in prompts
- Masks detected content to produce safer output
- Adds a **Clean Prompt** button on supported AI sites to sanitize prompts directly before sending
- Can also protect custom sensitive words defined by the user

## What it can detect

- Email addresses
- Phone numbers
- IBANs and payment-related patterns
- API keys and tokens
- Bank card numbers
- Crypto wallet addresses (BTC, ETH, LTC, TRX, SOL)
- SSN and ABA routing numbers (US)
- VAT numbers (EU)
- Custom sensitive words and phrases defined by the user

## How to use

Prompt Privacy Shield can be used in three ways:

1. Open the extension popup and paste text into it
2. On supported AI sites, use the **Clean Prompt** button to sanitize your prompt directly before sending
3. Select text on a web page and use the **Sanitize & Copy** option from the right-click menu

## How it works

The extension processes user-provided text **locally inside the browser**.

Its workflow is simple:

1. The user pastes text into the popup, uses the **Clean Prompt** button on a supported AI site, or selects text on a web page
2. The extension scans the text locally
3. It looks for potentially sensitive patterns using rule-based matching and validation checks
4. Detected matches are replaced according to the selected masking style
5. The sanitized result can then be reviewed by the user before sharing

## Privacy approach

Prompt Privacy Shield is designed as a privacy-focused tool.

- All processing happens locally in the browser
- No AI model or cloud processing is used
- No user data is collected
- Scanned text is not sent to remote servers
- No data is used for advertising, tracking, or profiling
- Settings are stored only in local browser storage

## Limitations

Prompt Privacy Shield uses a **rule-based** detection approach.  
It provides a practical and lightweight privacy layer, but it is not perfect.

- It does not use AI or semantic context analysis
- It may not catch every sensitive pattern
- It may sometimes produce false positives or false negatives
- Sanitized output should always be reviewed before sending sensitive content

## Permissions

The extension requests only the minimum permissions needed for its core features:

- **activeTab** — to work with text from the active tab after direct user interaction
- **scripting** — to run local sanitization logic in the page context when needed
- **storage** — to save user preferences and custom protected words locally
- **contextMenus** — to provide the **Sanitize & Copy** right-click action
- **Host access on supported AI sites** — to show the **Clean Prompt** button and sanitize prompts in place

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

Privacy Policy:  
https://batuhanberk06.github.io/prompt-privacy-shield-privacy/
