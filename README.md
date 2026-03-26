# SteamGamesDataAnalysis

## **DATABASE DOWNLOADED FROM KAGGLE (https://www.kaggle.com/datasets/waddahali/top-1000-steam-games-20242026/data)**
Credits to: https://www.kaggle.com/waddahali
  


  
# Top 1000 Steam Games (2024–2026)

A comprehensive, analysis-ready dataset of the top 1,000 best-selling and most-played games on Steam, scraped in March 2026. It combines data from the Steam Storefront API, store-page scraping, and the SteamSpy API into a single clean CSV with 12 structured columns.

What's Inside  
1,000 games — the top sellers on Steam, with release dates spanning 2006–2026 (majority from 2024–2026).
Pricing data — current USD price and active discount percentage, including Free-to-Play titles.
Review metrics — positive review percentage and total review count.
Community tags — up to 10 user-defined tags per game (e.g., Open World, Multiplayer, Pixel Graphics).
Steam Deck compatibility — Verified, Playable, Unsupported, or Unknown.
Player estimates — estimated owners via the Boxleiter Method (Total Reviews × 30) and 24-hour peak concurrent players from SteamSpy.


| Column | Type | Description |
|-------|----------|----------|
| AppID | int | Unique Steam application ID |
| Name    | str | Full game title |
| Release_Date  | date | Official release date (YYYY-MM-DD) |

...  
Primary_Genre	str	First genre listed (Action, Indie, RPG, etc.)
All_Tags	str	Up to 10 semicolon-separated community tags
Price_USD	float	Current price in USD (0.00 = Free to Play)
Discount_Pct	int	Active discount % at time of scrape (0–95)
Review_Score_Pct	int	% of positive reviews (0–100)
Total_Reviews	int	Total user reviews
Steam_Deck_Status	str	Deck compatibility (Verified / Playable / Unsupported / Unknown)
Estimated_Owners	int	Estimated owners (Total Reviews × 30)
24h_Peak_Players	int	Peak concurrent players in last 24h (SteamSpy)  

### How It Was Collected
Data was collected via a custom Python scraper using a multi-source pipeline:  

AppID Discovery — Crawled the Steam store "Top Sellers" page to compile ~1,000 unique AppIDs.
Steam API — Queried the Storefront API for official metadata (name, price, genre, reviews).
Store-Page Scraping — Parsed user-defined tags and Steam Deck compatibility from each game's public store page.
SteamSpy API — Retrieved 24-hour peak concurrent player counts.
Cleaning — Dropped rows with missing names, cast types, removed duplicates, calculated estimated owners, and sorted by review count.

### Use Cases  

NLP / tag clustering — Discover latent game groupings via TF-IDF or embeddings on All_Tags.
Genre success analysis — Which genres have the best review-to-ownership ratio?
Hidden gem detection — Surface under-priced, highly-reviewed games.
Steam Deck readiness — Analyse which game types earn "Verified" status.
Time-series exploration — Track how the top-seller landscape shifts year-over-year.

### Acknowledgements   
Valve Corporation—for the Steam platform and public APIs.   
SteamSpy (Sergey Galyonkin) — for the concurrent-player data endpoint.   
Boxleiter Method—industry heuristic estimating owners as Total Reviews × 30.   
