# Introduction to Data Science — Projects 1 & 2
**Group 2**

This repository contains the full data science pipeline for two projects built on the Spotify Tracks Dataset, including data preparation, visualization, web scraping, data integration, and hypothesis testing.

---


## Dataset

**Spotify Tracks Dataset** — 114,000+ music tracks across 114 genres, sourced via the Spotify API on Kaggle.

- Source: [Kaggle — Spotify Tracks Dataset](https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset)
- Key features: popularity, danceability, energy, loudness, tempo, valence, acousticness, speechiness, instrumentalness, artist name, track genre, explicit flag

---

## Repository Structure

```
├── README.md
├── Project 1.ipynb        # Data preparation & visualization (Spotify dataset)
└── Project 2.ipynb        # Web scraping, integration & hypothesis testing
```

---

## Project 1 — Spotify Tracks Analysis (`Project 1.ipynb`)

Follows the full data science pipeline on the Spotify dataset.

### Parts
| Part | Description |
|---|---|
| Part 1 | Report |
| Part 2 | Data Preparation — Cleaning, Encoding, Aggregation |
| Part 3 | Data Visualization & Question Answering |

### Questions Answered (Q1–Q12)

| # | Question |
|---|---|
| Q1 | How do energy and danceability influence track popularity across different genres? |
| Q2 | How does loudness relate to popularity, and does this differ between explicit and non-explicit tracks? |
| Q3 | How does valence vary across genres — is happier music more popular? |
| Q4 | How does tempo vary across genres, and does higher tempo correlate with danceability and popularity? |
| Q5 | How does track duration relate to popularity — are shorter or longer songs more successful? |
| Q6 | How does the relationship between acousticness and energy differ across genres? |
| Q7 | Which genres are most and least popular overall? |
| Q8–Q12 | Additional analysis (see `Full Report.docx` for full answers) |

### Libraries Used
```python
pandas, numpy, matplotlib, seaborn
```

---

## Project 2 — Web Scraping & Data Integration (`Project 2.ipynb`)

Extends Project 1 by enriching the Spotify dataset with data scraped from Wikipedia.

> **Note:** Project 2 uses `cleaneddataset.csv` — the cleaned output produced at the end of Project 1.

### Steps

| Step | Description |
|---|---|
| Step 1 | Web Scraping — Wikipedia "List of best-selling music artists" |
| Step 2 | Cleaning the scraped Wikipedia data |
| Step 3 | Data Integration — merging Spotify + Wikipedia datasets on artist name |
| Step 4 | Question Answering on the merged dataset |
| Step 5 | Hypothesis Testing |

### Why Wikipedia?
The Wikipedia dataset adds country of origin, genre, period active, and claimed record sales (in millions), enabling new cross-dataset questions such as:
- Do artists from certain countries score higher in Spotify popularity?
- Does real-world commercial success (sales) relate to Spotify popularity?
- How do audio features differ between long-active and newer artists?

### Libraries Used
```python
pandas, numpy, matplotlib, seaborn, requests, beautifulsoup4
```

---

## Key Findings

- **Energy & Danceability vs. Popularity** — Near-zero correlation; popular songs are spread across all energy/danceability levels.
- **Loudness** — Not a strong predictor of popularity for either explicit or non-explicit tracks.
- **Valence (Musical Positivity)** — No consistent link between happier-sounding music and higher popularity.
- **Tempo** — Mid-tempo genres (100–130 BPM) such as hip-hop and reggaeton are more popular and danceable than very fast genres.
- **Track Duration** — Songs between 2–4 minutes tend to achieve the highest popularity scores.
- **Acousticness vs. Energy** — Strong negative correlation (–0.845); acoustic and high-energy production rarely coexist.

## Running the analysis

1. Clone this repository and create a Python virtual environment.
2. Install Jupyter and the analysis libraries:

   ```sh
   python -m pip install jupyter pandas numpy matplotlib seaborn scipy requests beautifulsoup4 lxml
   ```

3. Download the Spotify Tracks Dataset from the source linked above. Check the CSV loading paths in `Project 1.ipynb` against your local download.
4. Open Jupyter and run `Project 1.ipynb` in order. Confirm that its cleaned data is exported as `cleaneddataset.csv` at the path expected by `Project 2.ipynb`.
5. Run `Project 2.ipynb`. Its Wikipedia scraping steps require internet access.

These are setup guidelines, not a verified dependency lockfile. Local paths or changes to Wikipedia tables may require adjustments.

## Interpretation and limitations

The findings describe associations in this dataset; they do not establish that audio features cause popularity. The Wikipedia integration covers a selected set of commercially successful artists, and artist-name matching may miss or ambiguously match records.

This is group coursework. The notebooks and report describe the combined work; repository ownership should not be interpreted as sole authorship.
