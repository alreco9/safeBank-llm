# 🏦 SafeBank-LLM

**AI-powered multi-layer security system for LLM chatbots in regulated industries**

## Overview
SafeBank-LLM is a proof-of-concept security framework designed to protect
LLM-powered chatbots used in regulated industries (banking, healthcare) from
adversarial attacks such as prompt injection, PII/PHI extraction, and social
engineering — in real time.

The system prompt is fully customizable — this repo includes a banking
configuration, and can be adapted to other regulated domains (e.g. healthcare)
by changing the threat taxonomy and compliance rules.

## Problem
General-purpose AI guardrails (e.g., Llama Guard, Azure Content Safety) are
not domain-aware. They fail to detect industry-specific attack patterns like
account takeover attempts, regulatory bypass, or social engineering disguised
as legitimate requests.

## Architecture — 5 Security Layers
1. **Input Sanitization** — Unicode normalization, homoglyph detection,
   real-time bank card (PAN) detection with Luhn algorithm verification
   (runs entirely client-side, before any API call)
2. **Semantic Guardrail** — Context-aware intent classification
3. **Regulatory Compliance** — PCI-DSS, GDPR, FINRA-aligned policy enforcement
4. **Red-Team Testing** — Adversarial prompt taxonomy
5. **Behavioral Anomaly Detection** — Session-level risk scoring

## Results
- **97.4%** mean attack detection rate
- **1.23%** false positive rate
- **44ms** average latency overhead

## Tech Stack
- Vanilla JavaScript (no framework dependencies)
- Claude API (Anthropic) for semantic threat analysis
- Client-side cryptographic validation (Luhn checksum)

## Running the Demo
1. Open `https://alreco9.github.io/safeBank-llm/` in any browser
2. Enter your own Anthropic API key (get one at [platform.claude.com](https://platform.claude.com))
3. Try the pre-built examples or type your own message

> ⚠️ This is an academic/portfolio demo. Not intended for production use with
> real customer or financial data.

## Author
**Rakan Al-Shammari** — Cybersecurity Graduate | SOC & Network Security Focus
Irbid National University · 2025–2026
