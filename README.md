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

- [**moralBERT-results folder**](data/moralBERT-results): This folder contains the individual scores for moralBERT in each subreddit + the [moralBERT-binary.csv file](data/moralBERT-results/moralBERT-binary.csv) that has the binary designation (present/not present) for each moral foundation. 

- [**selfimpr_topics.csv**](data/selfimpr_topics.csv): This file contains the topic designation for each document in r/selfimprovement.

- [**selfimpr_by_person_focus.csv**](data/selfimpr_by_person_focus.csv): This file contains posts/comments ids with pronouns designations (e.g. first person vs. not first person focused) .

- [**selfimpr_finaldata.csv**](data/selfimpr_finaldata.csv): This file contains the r/selfimprovement data with LIWC scores, MFD engineered scores, topic designations, and pronoun scores.

## Code 

- [**01.1-selfimprovement-cleaning-notebook.ipynb**](01.1-selfimprovement-cleaning-notebook.ipynb), [**01.2-homeowners-cleaning-notebook.ipynb**](01.2-homeowners-cleaning-notebook.ipynb), [**01.3-investing-cleaning-notebook.ipynb**](01.3-investing-cleaning-notebook.ipynb) : These notebooks do standard preprocessing and cleaning for the three subreddits. They are different since the investing data had to be subsampled. 

- [**02-LIWC.ipynb**](02-LIWC.ipynb): This notebook takes the LIWC and MFD scores from the three subreddits, does feature engineering by combining virtue+vice scores per foundation and creates a single file with all three subreddits' data

- [**03-topicmodeling.ipynb**](03-topicmodeling.ipynb): This notebook uses Gensim's LDA topic modeling

- [**04-pronouns-and-merging.ipynb**](04-pronouns-and-merging.ipynb): This notebook explores the LIWC's pronouns scores and tries different thresholds for defining what's considered a first-person document and what's not. It also combines the LIWC, MFD, topics and pronouns data into a single file. 

- [**05-plots.Rmd**](05-plots.Rmd): This notebook does some plots in ggplot for showcasing results. (Figures that aren't here were done in Tableau)

- [**06-stats-tests.ipynb**](06-stats-tests.ipynb): This notebook does statistical tests to evaluate differences across subreddits and between moralized/not moralized content. 

- [**07-moralBERT.ipynb**](07-moralBERT.ipynb): This notebook was obtained from the [moralBERT's authors repository](https://github.com/vjosapreniqi/MoralBERT/blob/main/MoralBert/Predict_mft_scores_from_the_MoralBERT_weights.ipynb) and minimally changed for using the reddit data.

- [**08-moralBERT-processing.ipynb**](08-moralBERT-processing.ipynb): This notebook takes the results from MoralBERT and calculates binary scores based on probabilities for each foundation. 

- [**09-BERTopic.ipybn**](09-BERTopic.ipynb): This notebook does BERTopic modeling on the selfimprovement data. 
