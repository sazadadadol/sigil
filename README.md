# Sigil

A local-first, terminal-based pentest assistant — built for zero-exfil operation during active hunts.

Sigil runs entirely on your machine: a Textual TUI backed by a local LLM (via Ollama), so nothing about your live engagement ever leaves the box. No cloud calls, no logging to a third party, no risk of client data touching an external API mid-hunt.


## Features

- **Local inference, zero exfil** — runs on Ollama with Mistral 7B (or WhiteRabbitNeo) for all in-engagement reasoning. No network calls leave the machine during an active hunt.
- **Pentest checklist** — structured tracking through an engagement so nothing gets skipped under time pressure.
- **Duck mentor** — a rubber-duck-style prompting feature for talking through findings and dead ends.
- **Automation / loadout module** — scripts and configs for standing up your lab environment quickly per engagement.
- **SQLite-backed** — engagement data, findings, and checklist state persist locally.
- **Separate intel-scraping path** — scheduled, non-engagement intel gathering can use the Claude API, kept entirely separate from active-hunt inference to preserve the zero-exfil guarantee.



## Requirements

- Python 3.x
- [Ollama](https://ollama.ai) running locally
- A local model pulled (Mistral 7B or WhiteRabbitNeo recommended)
- SQLite (bundled with Python)



## Architecture

- **TUI layer** — [Textual](https://textual.textualize.io/)
- **Inference** — local Ollama instance (Mistral 7B / WhiteRabbitNeo), no external calls during engagements
- **Storage** — SQLite
- **Intel scraping** — separate scheduled path using the Claude API, isolated from the active-hunt inference loop

## Status

Personal project, actively developed. Built and tested primarily on Pop!_OS.

## License

TBD

---

*Sigil: your region map for the hunt.*
