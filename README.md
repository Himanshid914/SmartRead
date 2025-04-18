## SmartRead
Implementation Workflow:
Data Preprocessing:
 The dataset was loaded and cleaned by removing null values and irrelevant columns. Only key features such as title, author, and genre were retained. A new column was created by merging these attributes to represent the book content as a single string.


## Feature Vectorization:
 To make the data suitable for comparison, CountVectorizer (or optionally TfidfVectorizer) was applied to convert the text into numeric feature vectors. Each book became a vector in a high-dimensional space, with terms as features.


## Similarity Computation:
 Cosine similarity was computed between the vector of the input book and those of all other books in the dataset. This helped identify how closely the other books matched the query book.


## Recommendation Logic:
 The system sorts books based on their similarity scores and returns the top 5–10 most similar books to the user’s input. If a book is not found in the dataset, an appropriate message is displayed.


## User Interface with Streamlit:
 The frontend was built using Streamlit, which lets users enter a book title. The interface processes the query and displays recommended titles in a visually clean and readable format.


This approach allows users to get fast, relevant book suggestions by leveraging natural language features and mathematical similarity measures.

## System Architecture

The system architecture of the Book Recommender System is designed to be modular and efficient, allowing seamless interaction between the user interface, core logic, and dataset.
User Interface (UI): Built on Streamlit, the UI acts as the communication layer between the user and the system. It collects user input, displays recommendations, and provides an intuitive and engaging experience.
Recommendation Engine: This is the heart of the system and resides in the backend script. It performs data loading, vectorization using CountVectorizer, similarity computation, and recommendation ranking. The simplicity of cosine similarity ensures fast and reliable performance.
Data Storage: The static dataset (goodreads_data.csv) is stored locally and loaded during execution. It holds book titles, authors, genres, and other descriptive information. Efficient preprocessing ensures consistent results.
Integration & Deployment: The entire system is run on Google Colab for development and testing. For deployment, ngrok is used to expose the local server to a public URL, making it accessible without a full-fledged cloud deployment.
This three-tier architecture ensures that the system remains lightweight, responsive, and easy to scale or modify for future enhancements.
