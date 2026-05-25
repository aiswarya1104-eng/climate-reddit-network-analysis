================================================================================
README — COSC2671 / COSC3047 Assignment 2
Group: Postgraduate Group 30
Members: Dhanya Laxminarayan (s4139554)
         Irine Biju Panicker (s4137661)
         Aiswarya Sibi (s4133705)
================================================================================

PROJECT TITLE
-------------
Hubs, Bridges & Climate Discourse:
Analysing User Interaction and Community Structure in Reddit Climate Discussions

RESEARCH QUESTION
-----------------
How do Reddit users interact in climate change discussions, and which users,
topics, and subreddit communities act as hubs or bridges in the climate
discourse network?

--------------------------------------------------------------------------------
REPOSITORY CONTENTS
--------------------------------------------------------------------------------

SUBMISSION FILES:
  Report_s4139554_PG_Group_30.pdf        — Final report (18 pages, 12pt)
  s4139554_PG_group30.ipynb              — Executed analysis notebook
  Worksheet_s4139554_PG_Group_30.pdf     — Team worksheet (timesheets +
                                           project plan + self-reflections)
  Access_s4139554_PG_Group_30.txt        — This repository access file
  reddit_climate_comments_sample_under10mb.csv     — Data sample under 10 MB

CODE:
  s4137661_PG_group30.ipynb              — Main analysis notebook (fully
                                           executed with all outputs)

DATA:
  comment.parquet                        — Full dataset (NOT included in repo
                                           due to 112 MB size — see note below)
  assignment2_final_outputs/             — All CSV result tables output by
                                           the notebook:
    reddit_climate_comments_sample_under10mb.csv
    table_subreddit_summary.csv
    table_sentiment_overall.csv
    table_sentiment_mean_by_subreddit.csv
    table_kruskal_sentiment_test.csv
    table_tfidf_terms_by_subreddit.csv
    table_lda_perplexity_check.csv
    table_lda_topics_labelled.csv
    table_topic_distribution.csv
    table_user_network_edges.csv
    table_user_centrality.csv
    table_user_community_summary.csv
    table_subreddit_similarity_edges.csv
    table_subreddit_similarity_centrality.csv
    reddit_climate_cleaned_with_sentiment_topics.csv

--------------------------------------------------------------------------------
DATASET
--------------------------------------------------------------------------------
Source:   cathw/reddit_climate_comment
Host:     HuggingFace (https://huggingface.co/datasets/cathw/reddit_climate_comment)
Licence:  MIT
Collected: 21-22 February 2024 via PRAW / Reddit API
Size:     6,550 posts → 96,328 interactions after flattening and cleaning

The full dataset (comment.parquet, ~112 MB) is NOT included in this repository
because it exceeds the 10 MB Canvas submission limit. It can be downloaded
directly from HuggingFace using the link above. A representative stratified
sample (10,620 rows, 8.83 MB) is included as:
  reddit_climate_comments_sample_under10mb.csv

--------------------------------------------------------------------------------
HOW TO RUN THE NOTEBOOK
--------------------------------------------------------------------------------
1. Install required packages:
   pip install pandas numpy matplotlib seaborn nltk scikit-learn scipy networkx

2. Download NLTK data (run once):
   import nltk
   nltk.download('vader_lexicon')
   nltk.download('stopwords')
   nltk.download('wordnet')
   nltk.download('omw-1.4')

3. Place comment.parquet in the same folder as the notebook.
   (Download from HuggingFace — link above)

4. Open s4137661_PG_group30.ipynb in Jupyter or VS Code.

5. Run all cells top to bottom:
   Kernel → Restart & Run All

   Expected runtime: 10-20 minutes (LDA perplexity sweep is the slowest step).

6. All output CSVs and plots will be saved to assignment2_final_outputs/

NOTE: LDA topic ordering may vary slightly between environments even with a
fixed random seed. If running fresh, re-verify topic labels against the top
words printed in Cell 22 before interpreting results.

--------------------------------------------------------------------------------
PACKAGES AND VERSIONS (tested)
--------------------------------------------------------------------------------
Python        3.10+
pandas        1.5+
numpy         1.23+
matplotlib    3.6+
seaborn       0.12+
nltk          3.7+
scikit-learn  1.1+
scipy         1.9+
networkx      2.8+
pyarrow       10.0+   (for reading .parquet)

--------------------------------------------------------------------------------
OUTPUT FILES
--------------------------------------------------------------------------------
The notebook saves all results to assignment2_final_outputs/:
  - CSV tables for all analyses (centrality, communities, topics, sentiment)
  - Plot images (PNG, 150 dpi) embedded in the notebook outputs

No credentials, API keys, tokens, or private data are included anywhere
in this repository.

================================================================================
