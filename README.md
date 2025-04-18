# SmartRead
Implementation Workflow:
Data Preprocessing:
 The dataset was loaded and cleaned by removing null values and irrelevant columns. Only key features such as title, author, and genre were retained. A new column was created by merging these attributes to represent the book content as a single string.


Feature Vectorization:
 To make the data suitable for comparison, CountVectorizer (or optionally TfidfVectorizer) was applied to convert the text into numeric feature vectors. Each book became a vector in a high-dimensional space, with terms as features.


Similarity Computation:
 Cosine similarity was computed between the vector of the input book and those of all other books in the dataset. This helped identify how closely the other books matched the query book.


Recommendation Logic:
 The system sorts books based on their similarity scores and returns the top 5–10 most similar books to the user’s input. If a book is not found in the dataset, an appropriate message is displayed.


User Interface with Streamlit:
 The frontend was built using Streamlit, which lets users enter a book title. The interface processes the query and displays recommended titles in a visually clean and readable format.


This approach allows users to get fast, relevant book suggestions by leveraging natural language features and mathematical similarity measures.

