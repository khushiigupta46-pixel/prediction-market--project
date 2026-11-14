# prediction-market--project
Data Science II Mini Project

Important Files:
- data_scraping.qmd 
  - File for scraping and wrangling Polymarket dataset
  - Process:
    1. Used PolymarketR search_events() to get relevant, closed election events
    2. Used event slugs from 1 in get_event_markets() to pull market data for all events
      - filter out 0 volume markets
      - conversions to avoid columns being loaded in as different types
    3. Used event slugs from 1 in get_event_price_history() to get historical prices
      - change fidelity to daily
      - conversions to avoid columns being loaded in as different types
    4. Join datasets
    5. "Pivot" data - instead of having long data, created closest_to_date() to pull prices 1 week, 2 weeks, and 1 month prior to closing
    6. Final wrangling and data renaming
- polymarket_data_final.csv
  - final data file
  - each row represents a single market
  - description in data_scraping.qmd 