# NC-Pilot — Privacy Policy

_Last updated: 2026-06-02_

NC-Pilot is a browser extension that lets you chat with an AI model which can read and act on
web pages on your behalf. This policy explains what data the extension handles and where it goes.

## Summary

- NC-Pilot does **not** have its own servers and does **not** collect, store, or transmit your
  data to the developer or any third party other than the AI model provider **you** configure.
- Your API keys and settings are stored **only** in your browser's local extension storage
  (`chrome.storage.local`). They never leave your device except to authenticate with the
  provider you select.
- Page content and your messages are sent **only** to the model backend you choose
  (local Ollama, OpenAI, or Anthropic) so it can respond.

## What data is processed

When you use NC-Pilot, the following may be sent to your chosen AI provider as part of a request:

- The text of your chat messages.
- Content NC-Pilot reads from the active tab when you ask it to act: visible page text
  (`read_page`), a list of interactive elements (`get_dom`), form/modal fields and their
  validation state (`get_forms`, `get_modal_html`), the active tab's URL/title, and —
  only if you explicitly request it — a screenshot of the visible tab.
- Browser history results, only when you ask NC-Pilot to search your history.
- The optional **"Your info / context"** text you save in Options (e.g. name, email, phone,
  resume summary, screening answers). You write it; it is sent with each task so the agent can
  fill forms from your data. Leave it empty if you don't want this.

This data is included in the model request solely to fulfill your instruction. NC-Pilot does
not log it, retain it, or send it anywhere else.

## Where data goes (depends on your chosen backend)

- **Ollama (local):** requests go to the Ollama server running on your own machine
  (e.g. `http://localhost:11434`). Nothing leaves your device.
- **OpenAI:** requests go to `https://api.openai.com` using your API key. Subject to
  OpenAI's privacy policy.
- **Anthropic:** requests go to `https://api.anthropic.com` using your API key. Subject to
  Anthropic's privacy policy.

You choose the backend. NC-Pilot sends data to that provider only.

## What NC-Pilot does NOT do

- Does not send any data to the extension developer.
- Does not use analytics, tracking, or advertising.
- Does not sell or share data with third parties.
- Does not store page content or chat history on any remote server.

## Storage on your device

- **API keys, model selection, and preferences:** stored in `chrome.storage.local` on your
  device. Removed when you uninstall the extension or clear them in Options.
- **Chat history:** kept in memory during a session for conversation context; not persisted to
  any remote server. If you enable the optional, off-by-default **debug server** (a developer
  tool you run yourself on `localhost`), runs and chat history are recorded by that local
  process on your own machine only.

## Permissions and why they are needed

- `tabs`, `activeTab`, `scripting`, host access (`<all_urls>`): to read and act on the page you
  ask NC-Pilot to work with.
- `sidePanel`, `storage`: for the chat UI and to save your settings/keys locally.
- `tabGroups`: to group the tabs a task opens so you can see what belongs to it.
- `history`: only used when you ask NC-Pilot to search your browser history.
- `downloads`: only used when you ask NC-Pilot to download a file.
- `notifications`: shows a local desktop notification when an agent action is waiting for
  your approval, so you don't miss it. Nothing is sent anywhere.
- `debugger` (optional, off by default): only requested if you enable **Enhanced input** in
  Options. Used solely to dispatch trusted clicks/keystrokes on the tab the agent works on;
  detached when each run ends. Chrome shows its own banner while active.

## Your control

- Keep **Ask Permission** mode on to approve each page-changing action.
- Remove your API keys at any time in Options.
- Uninstalling the extension removes all locally stored data.

## Contact

Questions about this policy: nilesh.c.060895@gmail.com
