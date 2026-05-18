# The Rise of Generative AI in Online Discourse

A Reddit-based social media mining project that analyzes how online communities discuss, evaluate, and normalize generative AI tools such as ChatGPT, GPT-4, Midjourney, Stable Diffusion, DALL·E, and other large language model/image-generation systems.

This project combines Reddit data collection, text preprocessing, exploratory data analysis, sentiment analysis, and BERTopic topic modeling to study how public discourse around generative AI differs across communities and interaction contexts.

---

## Project Overview

Generative AI has moved from a research-focused technology into a daily-use digital tool for writing, coding, image generation, education, troubleshooting, and decision support. As these systems become part of everyday workflows, public perception plays an important role in shaping trust, adoption, criticism, and future regulation.

This project investigates generative AI discourse on Reddit by asking:

- How do different Reddit communities discuss generative AI?
- Are posts and comments emotionally different in tone?
- Which topics dominate everyday conversations about generative AI?
- How does discussion volume and topic focus change over time?
- Do technical, creative, and general-interest communities frame AI differently?

The analysis treats generative AI not only as a technical artifact, but also as a social phenomenon shaped by online communities.

---

## Repository Contents

```text
.
├── smothuk_capstone.ipynb          # Main Jupyter notebook with full data collection and analysis pipeline
├── smothuk-assignment3.pdf         # Final written report
├── data/
│   ├── raw_posts.csv               # Raw Reddit post-level data
│   ├── raw_comments.csv            # Raw Reddit comment-level data
│   ├── clean_posts.csv             # Cleaned post-level dataset
│   └── clean_comments.csv          # Cleaned comment-level dataset
├── figures/                        # Generated visualizations
└── README.md                       # Project documentation
```

Note: Some large CSV files are be excluded from GitHub depending on repository size limits or privacy/data-sharing constraints.

---

## Dataset

The dataset was self-collected from publicly available Reddit JSON endpoints.

### Target Communities

The project focuses on AI-related and technology-oriented subreddits, including:

- `r/ChatGPT`
- `r/Midjourney`
- `r/StableDiffusion`
- `r/OpenAI`
- `r/ArtificialIntelligence`
- `r/artificial`
- `r/MachineLearning`
- `r/technology`
- `r/Futurology`

These communities were selected to compare different types of discourse:

- Creative communities focused on image generation and artistic workflows
- Technical communities focused on models, training, reasoning, and performance
- General-interest communities focused on technology news, social impact, and public debate

### Collection Method

The project uses Reddit's public JSON endpoints rather than authenticated API access. The notebook collects:

1. Reddit posts from subreddit feeds and search endpoints
2. Metadata such as post ID, subreddit, title, body text, score, number of comments, timestamp, and URL
3. Comment threads by appending `.json` to Reddit post URLs
4. Nested comments using a recursive flattening procedure
5. Comment metadata such as comment ID, parent ID, post ID, subreddit, author, score, timestamp, and body text

The collection process includes conservative request delays and a descriptive user-agent string.

---

## Installation

Clone the repository:

```bash
git clone https://github.com/<your-username>/<your-repository-name>.git
cd <your-repository-name>
```

Install required Python packages:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn nltk requests tqdm bertopic sentence-transformers
```

If using Jupyter:

```bash
pip install notebook
jupyter notebook
```

---

## How to Run

1. Open the notebook:

```bash
jupyter notebook smothuk_capstone.ipynb
```

2. Run the setup/import cells.

3. Run the data collection cells only if you want to recollect Reddit data.

4. If CSV files already exist, skip directly to the cleaning, EDA, sentiment analysis, and topic modeling sections.

5. Review generated charts and outputs in the notebook.

---

## Ethical and Data Considerations

This project uses publicly available Reddit content from public JSON endpoints. The collection process uses conservative request intervals and a descriptive user-agent string.

The analysis is conducted at the aggregate community level. The goal is to understand broad discourse patterns rather than identify or profile individual users.

---

## Project Context

This project was completed as part of a Social Media Mining course at Indiana University Bloomington. It demonstrates an end-to-end computational social science workflow using real-world social media data, natural language processing, and topic modeling.

