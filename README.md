# climate-nlp-esg-news-analysis
This project explores natural language processing techniques to identify, classify, and analyze climate-related discussions in company news articles.

The goal is to understand how organizations are represented in relation to climate issues, including sentiment, specificity, and thematic focus.

Climate discussions are often embedded within broader ESG reporting and can vary widely in tone, clarity, and detail. This project develops a structured NLP pipeline to extract meaningful climate-related insights from large collections of news articles.

## Project Workflow

The project consists of several stages:

- Text preprocessing and cleaning
- Climate relevance classification using domain-specific embeddings
- Climate specificity analysis
- Aspect-based sentiment analysis
- Data visualization and dashboard generation

Each stage addresses key challenges in extracting reliable climate-related insights from ESG news data.

## Dataset

The dataset consists of ESG-labeled company news articles containing:

- article text
- company name
- ESG category labels

Only articles labeled Environmental (E) were retained for climate analysis, as climate issues are typically categorized within the environmental dimension of ESG reporting.

## Text Preprocessing

Preprocessing steps included:

- lowercasing
- punctuation removal
- stopword removal
- number filtering
- tokenization

## Climate Relevance Classification

To determine whether articles discuss climate issues, we used ClimateBERT, a domain-specific transformer model trained on climate-related texts.

Embeddings from ClimateBERT were used as features to train two classifiers:

- Logistic Regression
- Random Forest

Results showed that Logistic Regression achieved better generalization performance, and it was selected as the final model for climate relevance detection.

## Climate Specificity Analysis

Climate discussions vary significantly in specificity.

Some articles contain vague references to sustainability, while others include detailed discussion of emissions, policy, or technology.

To quantify this, a pretrained ClimateBERT specificity model was used to classify texts as:

- Specific climate discussion
- Non-specific climate reference

This helps distinguish meaningful reporting from general ESG statements.

## Aspect-Based Sentiment Analysis

Initial experiments with pretrained climate sentiment models produced inconsistent results.

To obtain more interpretable sentiment insights, we implemented aspect-based sentiment analysis.

### Climate Aspect Detection

A manually curated climate aspects dictionary was created with different categories such as:

- Emissions
- Renewable Energy
- Climate Policy, etc.

Articles were tagged based on keyword matching for each aspect.

## Sentiment Analysis

For each detected aspect, sentiment was calculated using VADER sentiment analysis, producing sentiment scores for specific climate topics rather than the entire article.

This approach enables more granular insights, for example:

 -positive sentiment toward renewable energy initiatives
- negative sentiment toward carbon emissions or regulation costs

## Visualization and Dashboard

Processed results were compiled into a dashboard allowing users to:

- filter by company
- analyze sentiment across climate aspects
- explore trends in climate-related reporting

see (HTML)
