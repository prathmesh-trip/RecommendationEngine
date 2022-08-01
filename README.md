# Recommendation Engine

#### What is a Recommendation Engine?
Recommendation Engine is a subclass of **information filtering** system that predicts the rating/preference user gives to an item.

Alternatively, can be defined as algorithms that predict "movies to watch", "products to buy" or "text to read".

#### Applications : Recommendation Engine

1. Personalized Content Recommendations
2. Better search experience

#### Types of Recommender Systems

1. Content Based Filtering

- Content based filtering aka Cognitive filtering uses item features to recommend other items similar to what the users liked (based on previous actions/feedback).
- Data/Feedback is collected
  - Explicitly : Asking to fill survey forms
  - Implcityly : Tracking clicks/movements

2. Collaborative Filtering

- Recommends new items to a user based on interests/preferences of other similar users
- Done in two ways : 
  - User-based collaborative filtering : Find similar users
  - Item-based collaborative filtering : Find similar items
 
 #### Evaluation Metrics
 
 1. **Mean average precision at K**
   - Evaluates how relevant a list of recommended items are
   - Proportion of recommended items in top-k set that are relevant
 
 2. **Coverage**
   - % of items in training data that model is able to recommend on test set
   - % of possible recommendations that system can predict
   


 3. **Personlization**
   - Used to asses whether a model recommends many of same items to different users
   - Dissimilarity (l-cosine similarity) between user's lists of recommendations

 4. **Intralist Similarity**
   - Average cosine similarity of all items in a list of recommendations
   - Calculation usese features of recommended items to calculate similarity
 
 __________________________________________________________________________________________________________________________________
 
 
 ## Recommendation Engine : Content Based Filtering

#### Example

James has rated the Netflix content as follows :

| Movie | Rating | Genre |
| --- | ----------- | ----------- |
| Mission Impossible | Good | Action |
| James Bond | Good | Action |
| Toy Story | Bad | Kids |

This means we can use these above ratings to recommend him action movies only. 
We can't rule out the possibility of James liking Staurt Little (another kid's movie) or disliking Batman v/s Superman (an action movie).
Hence, we need more data to make accurate predictions.
Behaviours/Features of users being used for further recommendations. 
