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

#### Transactional Encoders
- Learns the unique labels in the dataset and then Transforms the dataset into a one-hot encoded NumPy boolean array
```
# Let's split all the genres into transactions
genres = data['genres'].str.split('|')

# Initiating/Defining a transactional encodes
te = TransactionEncoder()

# Transforming the data into Transactions
genres = te.fit_transform(genres)
```

 ## Recommendation Engine : Collaborative Filtering
 
 - Limitation of Content based filtering, requires good amount of information about own features rather than using users own interactions
 - Collaborative filtering uses user interactions instead of content from items used by users
 - Needs user's historical preferences on a set of items
  - Analysis is based on historical data
  - Core assumptions : Users who have agreed in the past also tend to agree in the future
  
## Types of Collaborative Filtering

**Reference** : https://medium.com/recommendation-systems/user-based-vs-item-based-collaborative-filtering-d40bb49c7060

- User Based Collaborative Filtering

  - **Item’s recommendation rating for a user is calculated depending on that items’ ratings by other similar users.**
  - Predicted Ratings based on rating by neighbouring users
  - Neighbourhood defined by similarity among users
  - Methodology : Pearson Correlation

- Item Based Collaborative Filtering

  - **Item’s rating is predicted based on how similar items have been rated by that user.**
  - Predicted Ratings based on rating by user on similar items
  - Neighbourhood defined by similarity among items
  - Methodology : Adjusted Cosine similarity


![image](https://user-images.githubusercontent.com/60221225/187652840-c5c3b2c3-f935-473d-bda4-3179ef8657e7.png)

