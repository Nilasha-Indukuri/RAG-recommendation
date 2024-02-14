# Recommender System and Retrieval Augmented Generation (RAG)

## Introduction
This project consists of two phases aimed at building a recommender system for some items and designing an assistant based on the Retrieval Augmented Generation (RAG) system.

### Phase 1: Recommender System
In this phase, we utilize a JSON file named `revised_data.json`, which contains information about headphone items which we previously crawled from the Amazon website. (The implementation of this can be found in the [repository](link-to-repository).)

#### Data Preparation
The `revised_data.json` file provides details about the headphone items, including their names, descriptions, and other relevant information. To create the recommender system, we employ Elasticsearch to store and retrieve the data efficiently. We merge the 'name' and 'description' tags into a new tag called 'detail' for simplicity, which serves as the basis for similarity calculations.

#### Similarity Calculation
Using Elasticsearch's default scoring function, TF-IDF, we calculate the similarity between items based on their 'detail' tag. The recommender system generates a list of similar items for a given input item.

#### Evaluation Metrics
To evaluate the performance of the recommender system, we define two matrices:
- **Predictions Matrix**: This matrix contains 20 top similar items for each item in the dataset based on the recommender system's output.
- **Ground Truth Matrix**: This matrix is created using cosine similarity as the scoring function to represent the true similarity between items.

##### Evaluation metrics used:

- **Spearman Correlation Coefficient**
  
  ![image](https://github.com/negjafari/recommender-system-and-RAG/assets/59292708/296c3746-6708-410f-b4c4-d27bd8d198a3)



- **Mean Average Precision (MAP)**
  
  ![image](https://github.com/negjafari/recommender-system-and-RAG/assets/59292708/05929483-c928-448d-9b2e-a213069e08c4)



### Additional Approach
In an attempt to enhance performance, we experimented with representing data as vectors using embeddings before storing them in Elasticsearch. This approach involved converting data into chunks and then using embedding techniques to convert these chunks into vectors. However, we observed a decrease in system performance and the quality of results compared to the initial approach.


### Phase 2: Assistant based on RAG Systems
In this phase, we develop an assistant that leverages the Retrieval Augmented Generation (RAG) system.
RAG systems are an easy and popular way to use your own data. You can provide it as part of the prompt with which you query the LLM model. As you would retrieve the relevant data and use it as augmented context for the LLM. Instead of relying solely on knowledge derived from the training data, a RAG workflow pulls relevant information and connects static LLMs with real-time data retrieval.


#### Workflow
1. User inputs a question related to the headphone items (in 'revised_data.json' file).
2. The recommender system retrieves the most similar documents based on the query.
3. User's question and retrieved data serve as context for the Large Language Model (LLM), named "LLaMA".

#### Sample Output
- example 1
  
  ![image](https://github.com/negjafari/recommender-system-and-RAG/assets/59292708/99223d35-eb20-48b8-84aa-02b920b5e5e6)


- example 2
  
  ![image](https://github.com/negjafari/recommender-system-and-RAG/assets/59292708/c4f4463f-8a91-40ea-b8e7-2b317c2b013a)


- example 3
 
  ![image](https://github.com/negjafari/recommender-system-and-RAG/assets/59292708/2498a6bd-df0f-454a-b064-11fb57c2e77b)


## Installation

In order to work with elasticsearch you have to run elastic search and use the API key and Cloud ID inorder to work with elasticsearch in colab.

## usage
in order to work with the `Elastic_Search`, first download the json file `revised_data.json`

## Contact Us
We're excited to hear from you! If you have any questions, suggestions, or need assistance, don't hesitate to reach out.
Feel free to contact us via email at:
- neg.jaafari@gmail.com
- noorbakhsha1@gmail.com
- Mehrnaz271380@gmail.com

We're here to help and would love to hear about your experience using this project.
