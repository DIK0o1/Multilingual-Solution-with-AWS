# CMU Movie Summary Corpus - Topic Modeling

This project demonstrates topic modeling on the **CMU Movie Summary Corpus**, a dataset containing movie plot summaries and metadata. The project uses **Amazon SageMaker's Neural Topic Model (NTM)** or **Amazon Comprehend** to extract and analyze topics from the data.

## Dataset

The CMU Movie Summary Corpus consists of:
- **plot_summaries.tsv**: 42,306 movie plot summaries.
- **movie.metadata.tsv**: Metadata for 81,741 movies (release date, revenue, genres, etc.).

For more details on the dataset, refer to the [paper by Bamman et al. (ACL 2013)](http://www.cs.cmu.edu/~dbamman/pubs/pdf/bamman+oconnor+smith.acl13.pdf).

---

## Steps to Run the Project

### 1. Data Preprocessing
- Load and inspect the datasets (`plot_summaries.tsv` and `movie.metadata.tsv`).
- Clean the plot summaries by:
  - Removing stop words and punctuation.
  - Tokenizing and lemmatizing text.

### 2. Feature Extraction
- Use **CountVectorizer** to transform the cleaned plot summaries into a document-term matrix.
- Convert the matrix to a sparse format required by Amazon SageMaker.

### 3. Topic Modeling
- Experiment with the number of topics using either:
  - **Amazon SageMaker's Neural Topic Model (NTM)**.
  - **Amazon Comprehend's topic modeling**.
- Upload the processed data to an S3 bucket for SageMaker or Comprehend.

### 4. Results and Analysis
- Extract and analyze the most relevant topics for the corpus.
- Visualize and interpret the results.

---

## Installation

### Prerequisites
1. Python 3.7+
2. AWS CLI configured with permissions for S3 and SageMaker.

### Required Packages
Install the dependencies:
```bash
pip install boto3 pandas numpy scikit-learn nltk sagemaker matplotlib seaborn
