# Privacy Policy for Candidate Ranker

*Last updated: March 2026*

## Overview

Candidate Ranker is a browser extension that helps recruiters rank job candidates using AI. This privacy policy explains how the extension handles data.

## Data Collection

**Candidate Ranker does not collect, store, or transmit any personal data to our servers.** We do not have access to your data.

## Data Storage

All data is stored locally on your device:

- **API Keys**: Your AI provider API keys (GLM/Zhipu AI or Google Gemini) are stored locally in your browser's extension storage. These keys never leave your device except when used to authenticate with the respective AI service.
- **Position Descriptions**: Job descriptions you enter are stored locally in your browser.

## Third-Party Services

This extension uses third-party AI services to analyze and rank candidates:

### GLM (Zhipu AI)
- **Website**: https://open.bigmodel.cn
- **Privacy Policy**: https://open.bigmodel.cn/terms
- Candidate profile data is sent to Zhipu AI's servers for analysis when you use the GLM provider.

### Google Gemini
- **Website**: https://ai.google.dev
- **Privacy Policy**: https://policies.google.com/privacy
- Candidate profile data is sent to Google's servers for analysis when you use the Gemini provider.

**Important**: By using this extension, you acknowledge that candidate profile information will be transmitted to your chosen AI provider. You are responsible for ensuring compliance with applicable privacy laws and regulations in your jurisdiction.

## Candidate Data

- Candidate profiles are read from LinkedIn and Seek pages you visit
- This data is temporarily processed in memory and sent to your selected AI provider for ranking
- Candidate data is not stored persistently by this extension
- Candidate data is not shared with any parties other than your selected AI provider

## Your Responsibilities

As a user of this extension, you are responsible for:

1. Obtaining necessary consent before processing candidate information
2. Complying with applicable data protection laws (GDPR, CCPA, etc.)
3. Understanding and accepting the privacy policies of your chosen AI provider
4. Safeguarding your API keys

## Changes to This Policy

We may update this privacy policy from time to time. Changes will be posted on this page with an updated revision date.

## Contact

For questions about this privacy policy, please open an issue on our GitHub repository:
https://github.com/Jackson-G2/Candidate-Ranker-Seek-Linkedin/issues

---

## Chrome Web Store Description Suggestion

Here's a description you can use for the Chrome Web Store:

**Short Description (132 chars max):**
```
AI-powered candidate ranking for recruiters. Rank candidates from Seek and LinkedIn against your job requirements using GLM or Gemini.
```

**Detailed Description:**
```
Candidate Ranker helps recruiters quickly identify the best candidates by using AI to analyze and rank profiles from Seek and LinkedIn.

Features:
- Rank candidates against your job description
- Support for GLM (Zhipu AI) and Google Gemini
- Works on Seek and LinkedIn candidate search pages
- Color-coded match scores (Excellent, Good, Fair, Weak)
- Configurable AI provider and model selection

How it works:
1. Enter your job/position description
2. Browse candidates on Seek or LinkedIn
3. Click "Rank Candidates" to get AI-powered match scores
4. Quickly identify top candidates

Your API key is stored locally and never shared. Candidate data is processed by your chosen AI provider (GLM or Gemini).

Perfect for recruiters, hiring managers, and talent acquisition professionals who want to save time screening candidates.
```
