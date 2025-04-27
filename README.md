# RAG-based Movie Recommendation System

## Overview

This project implements a movie recommendation system using Retrieval-Augmented Generation (RAG). It leverages semantic search on movie plot descriptions to find movies related to a user's query. The system uses MongoDB to store movie data, Hugging Face Transformers for generating plot embeddings, and a vector search to find relevant movies.

## Functionality

The system performs the following steps:

1.  **Data Storage:** Stores movie data, including titles and plot descriptions, in a MongoDB Atlas database.
2.  **Embedding Generation:** Uses the `sentence-transformers/all-MiniLM-L6-v2` model from Hugging Face Transformers to generate embeddings for movie plot descriptions. These embeddings capture the semantic meaning of the plots.
3.  **Vector Search:** Implements a vector search using MongoDB's `$vectorSearch` aggregation pipeline to find movies with plot embeddings similar to a user's query.

## Installation

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/git098/Movie_reccomendation.git
    cd Movie_reccomendation
    ```
2.  **Install the dependencies:**

    ```bash
    pip install pymongo[srv] requests
    ```

## Usage

1.  **Set up MongoDB Atlas:**

    *   Create a MongoDB Atlas account and a new cluster.
    *   Load the `sample_mflix` dataset.
    *   Create a vector search index named `PlotSemanticSearch` on the `plot_embedding_hf` field in the `movies` collection.
2.  **Set the Hugging Face API token:**

    *   Obtain a Hugging Face API token from your Hugging Face account.
    *   Set the `hf_token` variable in the notebook to your API token.
3.  **Run the Jupyter Notebook:**

    *   Open `RAG_app_Movie_Recommendation_Project.ipynb` using Jupyter Notebook or JupyterLab.
    *   Run the cells in the notebook to connect to MongoDB, generate plot embeddings (if not already present), and perform vector search.
4.  **Query the system:**

    *   Modify the `querry` variable in the notebook to specify your search query (e.g., `'superhero characters'`).
    *   Run the remaining cells to find movies related to your query.

## Requirements

*   Python 3.6+
*   `pymongo[srv]`
*   `requests`
*   Hugging Face API token

## License

This project is licensed under the MIT License - see the `LICENSE` file for details.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes.
