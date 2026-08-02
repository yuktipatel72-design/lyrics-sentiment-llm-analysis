# lyrics-sentiment-llm-analysis
Sentiment analysis and LLM-based theme extraction on song lyrics using NLP and Google Gemini API

# Song Lyrics Sentiment & Theme Analysis (NLP + LLM Integration)

A project analyzing song lyrics through a combination of traditional NLP 
sentiment scoring and modern LLM-based theme extraction, uncovering 
emotional patterns and trends across an artist's discography.

## Overview

This project combines two approaches to text analysis:
- **Traditional NLP** (TextBlob) for sentiment polarity scoring
- **LLM-based analysis** (Google Gemini API) for nuanced emotional theme 
  extraction

The goal was to compare what each method captures — and where a modern 
LLM adds interpretive value that simple polarity scoring misses (e.g., 
sarcasm, context, mixed emotions).

## Repository Structure
- `lyrics_analysis.ipynb` — main analysis notebook
- `README.md` — this file

## How to Run
1. Clone this repo
2. Install dependencies: 
   `pip install pandas textblob google-generativeai matplotlib seaborn`
3. Get a free Gemini API key from [aistudio.google.com](https://aistudio.google.com)
4. Replace the placeholder `"YOUR_GEMINI_API_KEY_HERE"` in the notebook 
   with your own key
5. Source the dataset from Kaggle (song lyrics dataset, artist-specific 
   CSV) and place it in the working directory
6. Run cells in order

## Dataset
- 347 songs, columns: Artist, Title, Album, Year, Lyric
- Sourced from a public Kaggle lyrics dataset
- Missing values handled: dropped 1 row with missing lyrics, recovered 
  ~57 missing Year values via Album-based grouping, remaining unrecoverable 
  rows excluded from year-based analysis only

## Methodology
1. Data cleaning and missing value handling
2. Sentiment analysis using TextBlob (polarity scoring: -1 to +1)
3. LLM-based emotional theme extraction using Google Gemini API 
   (with rate-limiting and error-handling for reliable batch processing)
4. Post-processing of LLM outputs (standardizing formatting, removing 
   near-duplicate categories)
5. Visualization: sentiment distribution, sentiment trend by year, theme 
   frequency, sentiment-by-theme comparison

## Key Findings
- 52% of songs classified as positive sentiment, 39% neutral, 9% negative
- Clear sentiment arc across career: strongly positive (2009–2012), a 
  notable dip around 2013–2014, followed by a volatile but generally 
  recovering trend through 2020–2022
- "Devoted Love" emerged as the most frequent LLM-identified theme, with 
  multiple "longing"-related sub-themes recurring across different 
  emotional tones
- LLM-based theme extraction captured nuance (e.g., context and emotional 
  framing) that basic sentiment polarity scoring alone missed

## Limitations
- Single-artist dataset (347 songs) — findings reflect one discography, 
  not generalizable broadly
- ~7% of tracks (short/alternate versions) had insufficient lyrical 
  content for reliable theme classification and were excluded from 
  theme-based analysis
- LLM output depends on API availability and free-tier rate limits

## Tools Used
Python, pandas, TextBlob, Google Gemini API, matplotlib, seaborn

## Note on Copyright
Song lyrics were used only for local, non-commercial analysis and is not redistributed in this repository to avoid copyrighting material — only derived outputs (sentiment scores, themes, metadata) are included.
