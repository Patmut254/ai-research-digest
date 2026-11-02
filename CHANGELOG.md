# Changelog

## v1.0 (2 November 2026)

First working release.

- Webhook receives a research topic and email address as JSON.
- arXiv search requires every keyword in the topic (AND), returning the five newest papers.
- Clean papers node splits the arXiv feed into one item per paper and handles single-paper and single-author results.
- LLM summarises each paper into structured JSON with a relevance score from 1 to 10.
- Switched the LLM from Google Gemini to Groq after hitting Gemini's free daily limit.
- LLM requests are sent one at a time with a 5-second delay to stay within rate limits.
- Parse AI output handles code fences, stray backslashes, missing fields and invalid JSON.
- Google Sheets uses Append or Update matched on the paper URL, so repeated runs do not create duplicates.
- HTML email digest is sorted by relevance score.
