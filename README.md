# **Streaming Content Strategy Insights**

This project analyzes exclusive content offerings and strategic trends across five major streaming platforms — **Netflix, Hulu, Amazon Prime, Disney+, and HBO Max** — using content metadata, thematic tags, and unsupervised clustering to uncover platform-specific priorities, gaps, and success patterns.

---

## **Project Goals**

- Identify **what type of content platforms prioritize** through exclusive catalogs.
- Reveal **content whitespace** — themes or formats missing across or within platforms.
- Determine **what types of shows succeed**, using rating and longevity metrics.
- Provide **data-driven recommendations** to optimize content creation and licensing strategies.

---

## **Notebooks**

| File Name | Description |
|-----------|-------------|
| `01_exploratory_filtering_and_tags.ipynb` | Loads, cleans, and filters TV content data. Maps missing age/rating fields and constructs tag-level metadata. |
| `02_tag_clustering_and_platform_focus.ipynb` | Uses Sentence-BERT + KMeans to cluster thematic tags. Analyzes dominant themes per platform and visualizes exclusive content strategies. |
| `03_content_gaps_and_success_factors.ipynb` | Identifies underrepresented (whitespace) genres and overperforming clusters in successful shows (high-rated, multi-season exclusives). |
| `04_country_and_age_insights.ipynb` | Analyzes age rating distributions and licensing origins. Surfaces platform-specific preferences in content maturity and global sourcing. |

---

## **Methodology**

### Data Cleaning
- Focused exclusively on **TV shows**, as they signal long-term engagement and strategic investment.
- Limited to the **Top 5 streaming platforms** for competitive relevance.
- Mapped noisy or missing age ratings using show descriptions.

### Tag Clustering
- Embedded show tags using **Sentence-BERT (`all-MiniLM-L6-v2`)**.
- Applied **KMeans** to group 90+ tag combinations into ~30 thematic clusters.
- Enabled interpretable, strategy-aligned content classification beyond broad genres.

### Success Definition
A show is considered **successful** if:
- Its **IMDB rating** is in the **top 20th percentile**, and
- It has **≥2 seasons**, indicating long-term viewer engagement.

---

## **Key Insights & Strategic Takeaways**

### Platform Priorities (via Exclusive Clusters)

| Platform      | Overrepresented Clusters                                        |
|---------------|-----------------------------------------------------------------|
| **Disney+**   | Music & Friendship, Youth Feel-Good, Magical Adventures        |
| **Netflix**   | Sci-Fi & Teen Drama, Political Espionage, Supernatural         |
| **HBO Max**   | Historical Conflict, Satire & War, Mature Drama                |
| **Amazon Prime** | Crime, Action & Revenge                                      |
| **Hulu**      | Teen Life, Coming-of-Age, Mixed                                |

> Each streamer is investing in distinct emotional and thematic arcs that define their audience identity.

---

### Genre Gaps (Whitespace Analysis)

- **Absolute Whitespace**: Clusters that appear in <3% of exclusive content across *all* platforms.
- **Platform-Specific Gaps**: Themes that are common on other platforms but missing from one.

> Use these gaps to guide platform-specific acquisitions or differentiation strategies.

---

### Top Performing Clusters

- Clusters with **highest leverage ratios** among successful shows:
  - **Mature Drama & Crime**
  - **Teen Life & Coming-of-Age**
  - **Political Espionage & Revenge**

> These clusters are **2–2.5× more likely** to appear in successful shows than in the full exclusive catalog.

---

### Licensing Trends (Country of Origin)

- **USA's share** dropped from **59.8% in 2016** to **51.3% in 2020**.
- **India** entered the top 5 in 2018 and rose to **7.3% by 2020**.
- **Japan** maintained a steady presence.

> Licensing teams should monitor and expand relationships with regional studios in India and Japan.

---

### Target Demographics (via Age Rating)

| Platform      | Skewed Toward   |
|---------------|-----------------|
| **Disney+**   | TV-G            |
| **HBO Max**   | TV-MA           |
| **Netflix & Hulu** | TV-14 + TV-MA |

> Align content development or licensing based on platform tone and audience maturity.

---

## Tech Stack

- **Python** (Pandas, NumPy, Seaborn, Matplotlib)
- **Colab** for interactive exploration
- **Sentence-BERT** for tag embeddings
- **KMeans**, **t-SNE** for clustering & visualization
- **ReelGood Data** as the primary content source
