# Data & Code Repository for MA Thesis 
The University of Chicago

Masters of Arts in Computational Social Science

Analysis of Moral Language in Self-Improvement Discourse through Natural Language Processing

By: Natasha Carpio Castellanos 

## Data

* Raw data can be downloaded from [Academic Torrents](https://academictorrents.com/details/56aa49f9653ba545f48df2e33679f014d2829c10). Click [here](https://academictorrents.com/docs/downloading.html) for download instructions.

* Files were downloaded in .zst format and converted into CSV files using this [python script](https://github.com/Watchful1/PushshiftDumps/blob/master/scripts/to_csv.py) provided by u/Watchful1 (user from Reddit)

- [**selfimpr_liwc.csv**](data/selfimpr_liwc.csv), [**homeowners_liwc.csv**](data/homeowners_liwc.csv), [**investing_liwc.csv**](data/investing_liwc.csv): These files contain the results for each subreddit after LIWC software and MFD analyses.

- [**engineered_morality.csv**](data/engineered_morality.csv): This file contains the LIWC and MFD engineered scores for all subreddits. Engineered scores consist of calculation of vice+virtue scores per foundation.

- [**moralBERT-results folder**](data/moralBERT-results): This folder contains the individual scores for moralBERT in each subreddit + the [**engineered_moralBERTresults.csv**](data/moralBERT-results/engineered_moralBERTresults.csv) file which combines the three subreddits and obtains virtue+vice scores per foundation.

- [**selfimpr_topics.csv**](data/selfimpr_topics.csv): This file contains the topic designation for each document in r/selfimprovement.

- [**selfimpr_pronounsdata.csv**](data/selfimpr_pronounsdata.csv): This file contains pronouns LIWC scores for each document in r/selfimprovement.

- [**selfimpr_finaldata.csv**](data/selfimpr_finaldata.csv): This file contains the r/selfimprovement data with LIWC scores, MFD engineered scores, topic designations, and pronoun scores.

## Code 

- [**01-cleaning-notebook.ipynb**](01-cleaning-notebook.ipynb): This notebook does standard preprocessing. It can be used for the three subreddits by changing the name of the source files. 

- [**02-LIWC.ipynb**](02-LIWC.ipynb): This notebook takes the LIWC and MFD scores from the three subreddits, does feature engineering by combining virtue+vice scores per foundation and creates a single file with all three subreddits' data

- [**03-topicmodeling.ipynb**](03-topicmodeling.ipynb): This notebook uses Gensim's LDA topic modeling

- [**04-pronouns.ipynb**](04-pronouns.ipynb): This notebook explores the LIWC's pronouns scores and tries different thresholds for defining what's considered a first-person document and what's not.

- [**05-plots.Rmd**](05-plots.Rmd): This notebook does some plots in ggplot for showcasing results. (Figures that aren't here were done in Tableau)


