# NUS Sentiment

NUS Sentiment is a sentiment checker which takes in keyword(s) and scrapes [**r/NUS**](https://www.reddit.com/r/nus/) for posts and comments containing the keyword(s). It allows NUS students to learn others' opinions of NUS-related topics, such as modules, professors, and accommodation, easier.

The posts and comments containing specific keyword(s) are run through a Sentiment Analysis Pipeline, which helps gauge people's sentiment toward the keyword(s). These results are collected, and a quick summary is displayed via various data visualization methods. They can also be pushed to a vector database where in the SemanticSearch page of the web app, users can make natural language queries. Top ranked matches by cosine similarity will be returned in a user-friendly format.

This project was done within the 24-hour limit of NUS Hack&Roll 2023 and won **Coreteam's Best Roll**.

## How we built it
- **Model**:  The main model we used to predict the sentiment of post/comment is a pre-trained `cardiffnlp/twitter-roberta-base-sentiment` from **HuggingFace Transformers**. Pre-processing tokens for our **WordCloud** was done with `TextBlob`

- **Data**: All data used is scraped from **r/NUS** using `PRAW`

- **Charts**: Altair, Matplotlib, Plotly Express

- **Database**:  We used **Pinecone**, a **vector database** to power our semantic search engine.**Deta Base**, a key-value store was also used to keep track of the most common keywords searched.

- **Frontend**: Streamlit

## Quick Start

```
git clone git@github.com:nus-sentiment/nus-sentiment.git
cd nus-sentiment
virtualenv venv
source venv/bin/activate
```

```
pip install -r requirements.txt
```

```
streamlit run Search.py
```
