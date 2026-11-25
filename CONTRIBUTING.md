# Contribution Guidelines

Please note that this project is released with a [Contributor Code of Conduct](CODE_OF_CONDUCT.md). By participating in this project you agree to abide by its terms.

## Scope

This repository catalogs **ready-to-use, open-weight Turkish TTS and STT (ASR) models**, along with essential inference runtimes and Turkish speech benchmarks.

- **Included:** Pre-trained or fine-tuned models with publicly downloadable weights (Hugging Face, GitHub, etc.) that support Turkish.
- **Excluded:** Raw standalone datasets, closed-source paid-only APIs, abandoned repositories without weights, and generic text-only LLMs.

## Pull Request Checklist

- Search previous suggestions and the current list before making a new one, as yours may be a duplicate.
- Make an individual Pull Request for each model suggestion.
- Keep descriptions short, objective, and hype-free (avoid words like "best" or "revolutionary").
- Follow the exact Markdown entry format:
  ```markdown
  - [Model Name](https://link-to-model) - Concise description starting with a capital letter and ending with a period.
  ```
- Insert entries in **alphabetical order** within the appropriate section.
- Include parameter count, architecture, hardware tier, or verified WER/CER metrics when available.
- Avoid trailing slashes in URLs and do not duplicate URLs across sections (to keep `awesome-lint` passing).
- Optionally add notable SOTA or ultra-lightweight models to the Quick Comparison tables (using bold text without duplicating the URL).

Thank you for your suggestions!
