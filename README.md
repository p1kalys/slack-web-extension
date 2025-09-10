# Slack Enchanter ✨

**Slack Enchanter** is a Chrome Extension script that enhances the Slack message input experience by adding two AI-powered buttons:

- ✅ **Correct** – Automatically corrects spelling, grammar, and punctuation.
- 🎯 **Professional** – Reformats casual messages to be more formal and professional.

## Problem / Motive

Many professionals use Slack to communicate concise but polished technical and business messages. Copy-pasting into external tools (Grammarly, ChatGPT, translators) is slow and context-breaking. The motive behind Slack Enchanter:

* Eliminate context switching: keep message refinement inside Slack.
* Make messages professional and clear with minimal user effort.
* Provide translations and tone control for global teams.
* Enable single-click post of the refined message back to Slack, preserving workflow.
In short: speed up sending clear, correct, context-appropriate messages without leaving Slack.

## Features

* Inline message editing UI inside Slack: grammar fixes, concise rewriting, tone adjustment and translation.
* One-click replace / send: insert the AI-improved text back into the Slack message input or post directly.
* Configurable tone options (e.g., professional, friendly, terse) and language selection for translation.
* Lightweight UI (popover / contextual button) that attaches to Slack’s message box or message actions.
* Minimal permissions: content script + background script for API calls (if used).

## Implementation Overview

### High-level flow

* Content script runs on Slack web pages. It injects UI (button/toolbar) near the message input or message actions.
* User writes or selects text and triggers the extension (e.g., click “Enchance”).
* The extension captures the message text and metadata (channel, thread context if needed).
* The extension sends the text + requested transformation (e.g., rewrite:professional) to a backend or directly to an AI API (OpenAI / other LLM).
* If Post is chosen, the extension inserts the new text into Slack’s message input and triggers the native send action (or uses the Slack Web API if authorized).

The extension handles errors, rate limits, and shows progress / loading state.
