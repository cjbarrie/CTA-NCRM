---
title: "Exercises"
subtitle: "NCRM, 2021"
author:
  name: Christopher Barrie
  affiliation: University of Edinburgh | [NCRM](https://github.com/cjbarrie/CTA-NCRM)
output: 
  html_document:
    theme: flatly
    highlight: haddock
    # code_folding: show
    toc: yes
    toc_depth: 4
    toc_float: yes
    keep_md: true
---



# Text as data exercises

We have learned a bit about four main applications of text as data techniques: word frequency analysis; sentiment analysis; topic modeling; and word embedding. Each of the four exercises focuses on one of these techniques. For some of the exercises there a several options. Don't try to do all of them!

## Word frequency

1. Take a large corpus from one of the sources listed [here](https://www.english-corpora.org/). Preprocess the text appropriately. Calculate word frequencies over time or across documents. Visualize the results.

2. Take a book or selection of books from Project Gutenberg. The R package detailed [here](https://cran.r-project.org/web/packages/gutenbergr/vignettes/intro.html) will be helpful with this. Calculate word frequencies across chapters of the same book or across entire books. You may wish to consult the "Social Science Bookshelf" as a first port of call [here](https://www.gutenberg.org/ebooks/bookshelves/search/?query=Anarchism%20%7C%20Crime%20Nonfiction%20.%20%7C%20Racism%20%7C%20Slavery%20%7C%20sociology%20.%20%7C%20Suffrage%20%7C%20Transportation).

Ideas: Variation is what we're often interested in as social scientists. So: 1) think about language use over time: what might change in language use tell us about cultural phenomena?; 2) think about sentence length (or complexity) over time; what does this tell us about differences over time or across different groups or across different texts?

## Sentiment analysis

1. Take tweets data from a labelled dataset of tweets listed [https://data.world/crowdflower/sentiment-analysis-in-text](https://data.world/crowdflower/sentiment-analysis-in-text) and which I've made downloadable via:


```r
twts_sent_data <- read.csv("https://raw.githubusercontent.com/cjbarrie/sicss_21/main/02_text_as_data/exercises_data/text_emotion.csv")
```

Use a sentiment analysis technique to label each tweet. You will need to group the labels in the original data into broader categories comparable to the type of sentiment labels you are going to produce (e.g., positive versus negative). Compare the labels you produce to those in the original data. 

2. Take parliamentary speech data from Hansard using the hansard package [here](https://cran.r-project.org/web/packages/hansard/index.html). Analyze sentiment in parliamentary contributions over time. Visualize the results.

## Topic modeling

1. Consult the vignette material for the topicmodels package in R [here](https://cran.r-project.org/web/packages/topicmodels/vignettes/topicmodels.pdf). Using the JSS papers data, vary the number of topics to search for. How sensitive are results to varying these parameters, when compared to the five topics example in the vignette? Visualize the results.

2. Consult [this](https://academic.oup.com/isq/article/61/3/489/4609692#106939098) article by Rochelle Terman. It looks at portrayals of Muslim women in US media over time. It uses structural topic models as part of the analysis. Replicate the analysis using the replication materials [here](https://github.com/rochelleterman/worlds-women). Provide an alternative visualization of Figure 3. Change the model parameters. What happens?

3. Take parliamentary speech data from Hansard using the hansard package [here](https://cran.r-project.org/web/packages/hansard/index.html). Analyze topics discussed in the House of Commons over a set time period. Visualize the results. Bonus: repeat but split by party Labour/Conservative.

## Word embedding

1. Use the GloVe embedding of MP tweets produced in the tutorial, and hosted on my Github with:


```r
url <- "https://github.com/cjbarrie/sicss_21/blob/main/02_text_as_data/04-word-embed/data/local_glove.rds?raw=true"
glove_embedding <- readRDS(url(url, method="libcurl"))
```

Implement a UMAP reprojection of these data. Explore one region of the data and visualize. Harder: upload the data and project in three dimensions using the tensorflow projector [here](http://projector.tensorflow.org/).

2. Take parliamentary speech data from Hansard using the hansard package [here](https://cran.r-project.org/web/packages/hansard/index.html). Following the steps outlined in the word embedding tutorial, train your own GloVe embedding using text over a period of time you specify. Inspect and visualize the results.

3. Consult [this](https://www.sciencedirect.com/science/article/pii/S0304422X21000504#sec0023) paper by Stoltz and Taylor. It investigates how we can map culture using word embeddings. The replication repo is [here](https://github.com/dustinstoltz/cartography_poetics) and ungated version of the article is [here](https://osf.io/preprints/socarxiv/5djcn/). Reproduce Figures 1 and 2. 
