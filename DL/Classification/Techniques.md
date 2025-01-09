## Comparison

|                                     | **Fine Tuning** | **Incremental Fine Tuning** | Embedding Space Representation | **Prompt Engineering**        | **Clustering on Embedding**        |
| ----------------------------------- | --------------- | --------------------------- | ------------------------------ | ----------------------------- | ---------------------------------- |
| **Training Needed?**                | Yes             | Yes                         | No                             | No                            | No                                 |
| **Handles new categories?**         | No              | Yes                         | Yes                            | Yes                           | Yes                                |
| **Initial Computation**:            | High            | Moderate-High (Periodic)    | Low (Only descriptions)        | - (Use of  pre-trained  LLMs) | Moderate (Embedding training data) |
| **Inference Computation**:          | Moderate        | Moderate                    | Low                            | Moderate (Its on vendor)      | Low                                |
| **Data requirement**:               | High            | Moderate-High               | Low                            | Low                           | Moderate                           |
| **Performance (Known categories)**: | High            | High                        | Moderate                       | Moderate                      | Moderate                           |
| **Performance (New Categories)**:   | -               | High                        | Moderate                       | Moderate                      | Moderate                           |
| **Scalability (new categories)**:   | -               | Moderate                    | High                           | Moderate                      | High                               |

----
## Fine Tuning
> **Fine-Tuning**: Training of models (e.g, BERT) on a labelled dataset for defined categories.


----
## Incremental Fine Tuning
>**Incremental Fine Tuning**: Gradually fine-tune pre-trained models for new categories using techniques like EWC (Elastic Weight Consolidation) to avoid catastrophic forgetting.


----
## Embedding Space Representation
>**Embedding Space Representation (Zero Shot)**: Using of pre-trained models (e.g., GPT-3, BART) to classify text based on semantic similarity between the text and description of categories.

Steps:
Initial:
1. Create text description for each category.
2. Get the embeddings of the description of each category.
Inference:
1. Get the embedding of the input text.
2. Find similarity of the embedding of the input text with the embeddings of the category descriptions.
3. Based upon similarity score, predict the category.
Fine tuning performance:
1. Improve the category descriptions.
2. Use better embedding models.

Demo Experiments:
- https://github.com/Deepam-Rai/AI_Exps/blob/main/classification/Embedding_Space_Representation.ipynb
- 


----
## Clustering on Embeddings
>**Clustering on Embeddings**: Generate embeddings using language models (e.g., BART) and classify text based upon its distance to category cluster centroids.


----
## Prompt Engineering
>**Few-Shot Learning with Prompt Engineering**: Use already trained LLM (e.g., GPT) to classify text based on small number of examples given in prompt.


----