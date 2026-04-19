# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Purpose

HTML-E-Mail-Signatur für Michael Netzig / MINEC UG mit klickbaren Social-Media-Icons (WhatsApp, LinkedIn, Facebook, Instagram, Newsletter).

## Files

- `signatur.html` — vollständige Signatur als HTML-Datei, im Browser vorschaubar und in E-Mail-Clients einfügbar

## Corporate Design

All visual output (HTML signatures, previews) must use the MINEC CSS variable system defined in the global `~/.claude/CLAUDE.md`. Key values:

- Background: `var(--minec-cream)` (`#f0ece9`)
- Primary color: `var(--minec-navy)` (`#193e47`)
- Accent/links: `var(--minec-teal)` (`#155d6b`)
- Font: Segoe UI (Arial fallback)
- No hardcoded hex codes — use CSS variables exclusively

Reference design: `../Coporate Design Guideline/MINEC_Design_System.json` and the interactive preview at `../Coporate Design Guideline/MINEC_Design_System_Interaktiv.html`.

## Contact Block (use verbatim in signatures)

```
Michael Netzig
MINEC UG
Gartenweg 9, 38551 Ribbesbüttel
Tel: +49 5374 6740088
info@minec.tech | https://minec.tech
```
