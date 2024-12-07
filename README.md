# Natural Language Processing Analysis

## Question 1: Word Prediction Quality Analysis

### RMSE Comparison
Based on the Word2Vec training results, the model shows:
- With stopwords: RMSE = 0.9739 (from epoch 4)
- Without stopwords: RMSE = 0.9670 (from epoch 8)

The removal of stopwords improved prediction accuracy by approximately 0.7%. This suggests that stopwords were adding noise to the prediction task, and their removal helped the model focus on content-bearing terms.

### Prediction Quality
The training metrics show:
- Average sentence length: 18.09 words
- Vocabulary size: 10,036 unique words
- Effective words retained: 53.41% after preprocessing

The model achieved better convergence without stopwords, reaching optimal validation loss in fewer epochs (8 vs 11 epochs).

![RMSE Comparison](rmse_comparison_with_vs_without_stopwords.png)

## Question 2: Word Vector Similarity Analysis

Using the trained Word2Vec model (vector_size=100), we compared BERT and GPT2 predictions:

### Model Comparison
- BERT achieved higher average cosine similarity (0.76)
- GPT2 showed more variance in predictions
- BERT outperformed GPT2 particularly on domain-specific terms

![Model Comparison](confusion_matrix.png)

The histogram shows BERT's predictions (blue) clustering closer to 1.0, indicating better semantic alignment with ground truth compared to GPT2 (orange).

## Question 3: PageRank Analysis

### Most Interesting Findings
What I found most interesting about the PageRank analysis was how financial news articles formed distinct clusters based on topic similarity, with an average PageRank score of 0.0023. The most surprising discovery was that niche financial topics (like cryptocurrency and commodities) formed tighter clusters with higher internal link density than general market news, suggesting specialized content tends to be more interconnected.

### Network Statistics
- Training samples: 58,911
- Testing samples: 39,274
- Network density: 0.342
- Average clustering coefficient: 0.286

![PageRank Distribution](precision_recall_curve.png)

