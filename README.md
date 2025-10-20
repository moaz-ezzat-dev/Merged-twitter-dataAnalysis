# Insights and Analysis from WeRateDogs Twitter Data

## Project Overview
This project analyzes the WeRateDogs Twitter dataset, a collection of tweets from the popular Twitter account that humorously rates dogs.  
By cleaning, merging, and analyzing the dataset, the project uncovers trends in tweet engagement, dog stage distribution, and breed popularity.

The goal is to:
- Identify which dog stages (like “doggo” or “pupper”) appear most frequently.  
- Analyze which stages receive the highest engagement (retweets and favorites).  
- Determine the most popular dog breeds based on mentions in the tweets.

---

## Objectives
1. Clean and merge multiple data sources (tweets, image predictions, and additional data).  
2. Explore relationships between dog stage and engagement metrics.  
3. Visualize patterns in dog breed frequency and engagement.  
4. Present actionable insights for social media and content strategies.

---

## Dataset Description
The analysis is based on the WeRateDogs Twitter Archive, which includes:
- Tweet text and metadata (date, likes, retweets, etc.)
- Predicted dog breeds from image classification
- Extracted dog “stages” (pupper, puppo, doggo, floofer)

Data Sources:
- `twitter-archive-enhanced.csv`
- `image-predictions.tsv`
- `tweet-json.txt` (API-collected additional metrics)

---

## Data Wrangling
The data required extensive cleaning and integration:

- Quality issues fixed:
  - Removed retweets and duplicates.
  - Converted timestamps to datetime format.
  - Standardized dog stage labels (pupper, puppo, doggo, floofer).
  - Merged additional tweet metrics (retweets, favorites) from API data.
- Tidiness issues fixed:
  - Combined all sources into a single master DataFrame.
  - Extracted relevant columns for analysis.

---

## Key Insights

### 1. Distribution of Dog Stages
“Pupper” and “Doggo” are the most common stages.  
“Puppo” and “Floofer” appear less frequently, indicating lower representation.

### 2. Average Retweet Count by Dog Stage
Tweets with the “Doggo” stage show the highest average retweet count, making them the most engaging.

### 3. Most Common Dog Breeds
Golden Retriever appears as the most frequently mentioned breed, reflecting its strong popularity among followers.

---

## Visualizations

### 1. Distribution of Dog Stages
Displays the count of each dog stage in the dataset.

```python
sns.countplot(data=df, x='dog_stage', order=df['dog_stage'].value_counts().index)
plt.title('Distribution of Dog Stages')
plt.xlabel('Dog Stage')
plt.ylabel('Count')
plt.show()
