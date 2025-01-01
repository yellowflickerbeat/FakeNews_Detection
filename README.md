# FakeNews_Detection
1. Abstract
The objective of this project is to detect fake news using machine learning
techniques. We implemented a solution that uses a combination of VADER
sentiment analysis for headlines, a Random Forest Classifier for article text,
incorporating the various subjects as features for the model and various
linguistic features such as average sentence length, Flesch-Kincaid readability,
and keywords feature.
---
2. Text-Based Features:
○ Average Sentence Length: A measure of sentence complexity.
○ Flesch-Kincaid Readability Score: A metric indicating the
readability of the text.
These features were calculated and added to the dataset as
additional predictors for the model.
---
4. Dataset
The dataset used for training and testing contains news articles labeled as 1
(for real) or 0 (for fake). It consists of 5 columns:<br>
● id: Unique identifier for each article.<br>
● title: The headline of each news article.<br>
● text: Full text of the article<br>
● date: The date of publication.<br>
● label: The true label indicating whether the article is fake or real, using
which our model accuracy will be determined<br>
● subject: The category or domain of the article (e.g., politics, world<br>
news, etc.).<br>
After processing the datasets through the ML model, features such as
sentiment analysis scores, readability metrics, and average sentence length,
are added.
---
6. Model and Approach
We used a Random Forest Classifier to build the classification model for
the articles' text. The Random Forest algorithm was chosen for its ability to
handle high-dimensional data, its ability to implement feature importance and
its robustness in the context of overfitting. We also incorporated the following
features:<br>
● Content sentiment scores from VADER.<br>
● Average sentence length and Flesch-Kincaid readability scores.<br>
● Keywords for fake news detection.<br>
● Subject categories (politics, government, left-news, politics, world,
news, Middle-east, US).<br>
The training and testing data were split using an 80-20 ratio.
---
8. Results
After each feature implementation as shown in sections in the code notebook,
the model accuracy climbed from initial 54% to 100% by the final stage, for
both train and test datasets.<br>
To ensure that the results were not just a fluke, the labels were shuffled and
tested again, the accuracy dropped to 48%, which is expected when the labels
are randomized. This confirmed that the model was not overfitting and there
was no data leakage due to overlapping between test and training data. This
also implied that the accuracy resulted from the model observing patterns
within the data.<br><br>
Key evaluation metrics:<br>
● Accuracy: 100% (on the original dataset before label shuffling).<br>
● Classification Report: Included metrics such as precision, recall, and
F1-score for both "fake" and "real" classes.
---
