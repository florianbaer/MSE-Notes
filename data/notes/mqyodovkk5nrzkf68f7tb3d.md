# Sentiment Analysis


Target is to understand the emotional state of the author of a text, which can be **extremly hard.**

Can be misleading : 
![Missleading example using sentiment analysis](/assets/images/2022-03-10-10-47-08.png)

- The following thing have the be taken into accoutn:
- opinion holder: whose opinion is this?
- target entity: what is this opinion about?
- aspect: specific feature of the target that this opinion is about
- type: most commonly positive, negative, neutral, along with an indication of strength
- time when this opinion was expressed

![Example of entities](/assets/images/2022-03-10-10-49-51.png)

## Dog Example
![Dog Example](/assets/images/2022-03-10-10-51-35.png)

- There are problems with negations
> I didn't like it.
- There are problems with modal words
> Many consider the movie bewildering, boring or slow-moving or annoying
- Not literal language 
> Not exactly a masterpiece

## Simplify the problem 

- Subtlety: Let’s all go to see Miss Hepburn and hear her run the gamut of emotions from A to B! Dorothy Parker (1893-1967), American writer (criticizing the American actress Katharine Hepburn in 1934)

- Sarcasm: The staff went out of their way to make us look forward to
the end of our vacation.

## Approach
1. tokenization (often hard with informal text)
1. feature extraction
1. classification (NB, MaxEnt, SVM)
1. two or three classes: {positive | negative | (neutral)}

In Sentitment-Analysis topic words are not as importat as sentitment words such as splendid (prächtig) and bad.

Turney (2002) startet it using a POS-Tagger (1), then estimate the **semantic orientation** (2) and then **classified on the average semantic orientation**

## PMI
Semantic orientation is computed based on Pointwise Mutual Information (PMI)
![Probability calculation](/assets/images/2022-03-10-11-25-36.png)

![Calculation of the PMI](/assets/images/2022-03-10-11-28-52.png)
Where the second #Academy should be #Award

- Words with high PMI are very likely to occur jointly
- Two words with low PMI are very likely to occur separately
- The PMI of select _bigrams_ with reference words is computed
- excellent for positive reviews and poor for negative reviews is poor

![Phrase - PMI Calculation](/assets/images/2022-03-10-11-32-39.png)