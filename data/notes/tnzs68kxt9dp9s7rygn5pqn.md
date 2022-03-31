
User has information need and expresses it as query.

In the boolean model we are very limited.

create representations  with binary term document incident matrix
## Boolean model
- documents can not be ranked
- does not return documents containing variants of the query words
- users must understand the operators

![Relationships](/assets/images/2022-03-17-09-26-58.png)

## Goal to have ranks / full-text queries
Should also provide partial matching

![](/assets/images/2022-03-17-09-29-08.png)

Functional words in the sentiment analysis are words like "not good" - these are important in sentiment analysis.

term-document matrix is a matrix counting the words appearing in a document. -**we have a lots of zeros and want to fix it :smile:**

We represents document in the vector space.


![How to constrcut a word-document matrix](/assets/images/2022-03-17-09-46-41.png)

Adaptions in term frequency - adapt with a function - 50 times occurance does not mean 50 times as important than occuring once
![math functions tf](/assets/images/2022-03-17-09-53-22.png)
inverse document frequency - try to smooth it with operations
![math operations on idf](/assets/images/2022-03-17-09-53-41.png)

!(Calculations TF-IDF)[https://web.stanford.edu/~jurafsky/slp3/]

Document length normalization - penalities for long documents


## Cosine similarty 
$$\frac{\sum_{i=1}^N v_i \times w_i}{\sqrt{\sum_{i = 1}^N v^{2}_i}\sqrt{\sum_{i = 1}^N w^{2}_i}}$$


![Okapi BM 25 formula](/assets/images/2022-03-17-10-27-51.png)
$$\text{score}(q,d) = \sum_{r \in q}\frac{tf \cdot idf (t,d)}{|d|}$$
**Do an tf-idf for each word in the query**





# Machine Learning models for ranked retrieval
- Fast
- robustness

## Learning to rank (LTR)

- **pointwise approach (learn scores)**
  - traditional ML approaches, e.g., One-Class SVM, P-rank
- **pairwise approaches (also learn scores, but with different loss functions)**
  - consider pairwise training data, i.e. positive examples: ym > yn for a pair of documents and a given query, use pairwise loss to learn a classification/regression model
- **listwise approaches (consider the ranked list in its entirety)**
  - consider the ranked list in its entirety

# Takeaways
- We need data
- We need people who annotate data
- we need people who can understand the data

![Metrics for Ranking](/assets/images/2022-03-17-10-52-09.png)
 
Discounted cumulative gain (DCG) - gives high ranks a higher score but also takes low ranks into account

**thereotically-grounded model**
