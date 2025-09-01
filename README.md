📰 Newspulse

An interactive Streamlit app to fetch, explore, and analyze live news in real time.

🚀 Overview

Fetch category-based headlines (entertainment, finance, business, technology) from GNews.

Search news dynamically using keywords (latest 10 articles).

Perform per-article analysis: sentiment, tokens, bigrams, named entities.

Get overall insights: sentiment distribution, word frequencies, entity insights across fetched articles.

✨ Features

Live news fetching → Current headlines by category.

Keyword search → 10 most recent articles with title, source, and URL.

Article cards → Image, title, description, metadata.

One-click analysis → Sentiment, tokens, bigrams, entities per article.

Overall insights → Distribution plots + frequency tables.

Session state → Retains fetched data & selections.

Error handling → API keys missing, rate limits, no results, or network issues.

🛠 Tech Stack

Frontend → Streamlit

APIs / HTTP → requests, GNews API (GNEWS_API_KEY), optional: NewsAPI.org (newsapi_fetch.py)

NLP → spaCy, NLTK, transformers, torch

Data / Plots → pandas, matplotlib, seaborn, plotly

Utils → tqdm, orjson, feedparser

Auth & Storage (scaffolded) → bcrypt, pymongo[srv], python-dotenv

📂 Project Structure
newspulse2/
  newspulse/
    newspulse/
      app.py                    # Streamlit entry point
      newsapi_fetch.py          # CLI script for NewsAPI.org keyword search
      requirements.txt
      newspulse_pkg/
        __init__.py
        auth.py                 # Auth helpers
        config.py               # Config/env helpers
        ingestion.py            # Data ingestion utilities
        ner.py                  # Entity extraction (spaCy)
        news_api.py             # GNews integration (category + keyword search)
        news_ui.py              # Streamlit UI components (news & search UI)
        preprocessing.py        # Text cleaning, tokenization, n-grams
        sentiment.py            # Sentiment prediction
        utils.py                # Misc helpers
        viz.py                  # Plotting utilities (plotly/matplotlib)

⚙️ Getting Started
1️⃣ Clone the repository
git clone https://github.com/Dharshh245/newpulse.git
cd newpulse/newspulse2/newspulse/newspulse

2️⃣ Create a virtual environment (recommended)
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python -m venv venv
source venv/bin/activate

3️⃣ Install dependencies
pip install -r requirements.txt

4️⃣ Set up environment variables

Create a .env file in the root directory with:

GNEWS_API_KEY=your_api_key_here


(Optional: Add keys for NewsAPI, MongoDB, etc.)

5️⃣ Run the Streamlit app
streamlit run app.py


The app will start locally in your browser. 🎉
