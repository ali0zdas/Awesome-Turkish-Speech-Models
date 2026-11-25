# Contributing Guidelines

Thank you for helping grow **Awesome Turkish Speech Models**! Please follow these guidelines to keep the list clean, accurate, and compliant with [Awesome List standards](https://github.com/sindresorhus/awesome/blob/main/pull_request_template.md).

## Scope

This repository catalogs **ready-to-use, open-weight Turkish TTS and STT (ASR) models** and essential inference runtimes.

- **Included:** Pre-trained or fine-tuned models with publicly downloadable weights (Hugging Face, GitHub, etc.) that support Turkish.
- **Excluded:** Raw datasets, closed-source paid-only APIs, abandoned repos without weights, and generic NLP/LLM models without speech capabilities.

## Pull Request Checklist

1. **Search first:** Ensure the model is not already listed.
2. **One model per PR:** Submit individual Pull Requests for separate model additions so each can be reviewed cleanly.
3. **Formatting:** Follow the exact Markdown pattern:
   ```markdown
   - [Model Name](https://link-to-model) - Concise, objective description starting with a capital letter and ending with a period.
   ```
4. **No hype:** Avoid promotional adjectives (e.g., "best", "revolutionary"). Stick to architecture, parameter count, hardware needs, license, and benchmark metrics (WER/CER/RTF) when available.
5. **Update Quick Comparison (Optional):** If the model is a notable SOTA or ultra-lightweight option, add a corresponding row to the summary table.
6. **Check spelling and links:** Verify all links resolve cleanly with no trailing slashes or broken anchors.
