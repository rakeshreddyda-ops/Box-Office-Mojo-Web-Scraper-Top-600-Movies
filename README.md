# 🕷️ Web Scraping — Box Office Mojo (Top 600 Movies)

A Python web scraping project that extracts worldwide box office data of the top 600 movies from [Box Office Mojo](https://www.boxofficemojo.com), cleans it, and exports to CSV. A follow-up analysis script (`gross_analysis_imdb.py`) performs deep EDA and market insights on the scraped data.

---

## 📁 Folder Structure

```
web-scraping/
│
├── scraper/
│   └── Web_Scrapping_Final_data.ipynb   # Main scraping notebook (BeautifulSoup)
│
├── analysis/
│   └── gross_analysis_imdb.py           # EDA & market analysis on scraped data
│
├── data/
│   └── boxoffice_593_movies.csv         # Output: cleaned dataset (593 movies)
│
├── requirements.txt                     # Python dependencies
└── README.md
```

---

## 📌 Project Overview

This project scrapes the **Top 600 highest-grossing movies of all time** from Box Office Mojo across 3 paginated pages and exports the data for analysis.

The companion analysis script (`gross_analysis_imdb.py`) then performs:
- Outlier detection using IQR method
- Log transformation to handle skewed data
- Market concentration (Pareto) analysis
- Domestic vs. Foreign revenue correlation
- Feature engineering (era classification, market categories)
- Temporal trend analysis by year and era

---

## 🛠️ Tech Stack

| Library | Purpose |
|---------|---------|
| Python 3.x | Core language |
| `requests` | HTTP GET requests |
| `BeautifulSoup4` | HTML parsing |
| `pandas` | Data cleaning & CSV export |
| `matplotlib` & `seaborn` | Data visualization |
| `scipy` | Statistical analysis (Pearson, trimmed mean) |
| `numpy` | Numerical operations |

---

## 🌐 Data Source & Fields Scraped

- **Source:** [boxofficemojo.com/chart/ww_top_lifetime_gross](https://www.boxofficemojo.com/chart/ww_top_lifetime_gross/)
- **Pages scraped:** 3 (offsets: 0, 200, 400)

| Column | Description |
|--------|-------------|
| Rank | Global box office rank |
| Name | Movie title |
| Worldwide Gross | Total worldwide revenue |
| Domestic Gross | US/Canada revenue |
| Foreign Gross | International revenue |
| Domestic % | Share of domestic earnings |
| Foreign % | Share of foreign earnings |
| Year | Release year |

**Total records:** 593 movies (after deduplication)

---

## 📊 Key Analysis Findings

- **Top earner:** Avatar ($2.92B worldwide)
- **Market concentration:** ~65% of movies drive 80% of total revenue — a strong Pareto effect
- **Domestic vs Foreign correlation:** Weak — international success doesn't guarantee domestic success
- **Median worldwide gross:** ~$471M (more reliable benchmark than the mean of ~$592M, which is skewed by blockbusters)
- **Trend:** Revenue has grown post-2010, driven mostly by a handful of mega-blockbusters

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/web-scraping.git
   cd web-scraping
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the scraper notebook:
   ```bash
   jupyter notebook scraper/Web_Scrapping_Final_data.ipynb
   ```

4. Run the analysis script:
   ```bash
   python analysis/gross_analysis_imdb.py
   ```

---

## 📦 requirements.txt

```
requests
beautifulsoup4
pandas
numpy
matplotlib
seaborn
scipy
jupyter
```

---

## ⚠️ Disclaimer

This project is for **educational purposes only**. Always check a website's `robots.txt` and Terms of Service before scraping.

---

## 📄 License

This project is for educational and portfolio purposes.
