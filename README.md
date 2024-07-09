### Project Pipeline: Propaganda Detection

#### 1. Introduction
- **Objective:** Classify propaganda techniques using the Propaganda Techniques corpus.
- **Subtasks:**
  - Span Identification (SI): Binary sequence tagging to identify propaganda.
  - Technique Classification (TC): Classify the type of propaganda technique used.

#### 2. Data Collection
- **Dataset:** Propaganda Techniques Corpus (Da San Martino et al., 2020)
  - **Columns:**
    - Label: Indicates propaganda type or "Not propaganda."
    - Tagged Text: Text content with specific tokens marked by `<BOS>` (beginning of span) and `<EOS>` (end of span).

#### 3. Data Preprocessing
- **Challenges:**
  - Categorical imbalance in target variable.
  - Handling special tags (`<BOS>`, `<EOS>`).
  - Addressing potential duplicates and sparsity in the dataset.

- **Steps:**
  - Cleaning and preprocessing (removal of tags, normalization).
  - Tokenization using `nltk.word_tokenize`.
  - Stemming and lemmatization using `WordNetLemmatizer` and `PorterStemmer`.
  - Named Entity Recognition (NER) using `spacy`.

#### 4. Feature Extraction
- **Bag of Words (BoW) Vectorization:**
  - Create vocabulary of unique words.
  - Convert textual data into numerical form.

#### 5. Model Training
- **Models Used:**
  - **Logistic Regression:**
    - Input from BoW vectorizations.
    - Penalty, solver, max_iter, multi_class, and C parameter tuning.
  - **BERT (Bidirectional Encoder Representations from Transformers):**
    - Preprocessing and tokenization using `BertTokenizer`.
    - Fine-tuning with `BertForSequenceClassification`.
    - Dynamic padding to handle variable-length input sequences.

#### 6. Hyper-Parameter Tuning
- **Bag of Words:**
  - Analyzer, n-gram range, and lowercase parameters tuning.
- **Logistic Regression:**
  - Penalty, solver, max_iter, multi_class, and C parameter tuning.
- **BERT:**
  - Tokenization parameters (`batch_encode_plus`, max_length, pad_to_max_length, truncation).
  - Batch sizes, epochs, learning rate, optimizer tuning.

#### 7. Evaluation Metrics
- **Precision:** Measures accuracy of positive predictions.
- **Recall:** Measures coverage of actual positives.
- **F1-Score:** Harmonic mean of precision and recall.
- **Accuracy:** Overall correctness of the model.
- **Macro Average:** Average metrics across all classes, giving equal weight to each class.

#### 8. Results and Analysis
- **Bag of Words:**
  - Experimentation with optimized CountVectorizer, stemming, and NER & lemmatization.
  - Observations on precision, recall, F1-score, and accuracy.
- **BERT:**
  - Experimentation with hyper-parameter settings and dynamic padding.
  - Improved performance over BoW models.

#### 9. Conclusion
- Summary of findings.
- Comparison between BoW and BERT models.
- Effectiveness of dynamic padding.

#### 10. Further Work
- Additional preprocessing stages and feature selection.
- Cross-evaluation with diversified datasets.
- Use of BERT for feature extraction with logistic regression.
- Experimentation with other Transformer family models (e.g., BERT-Large, RoBERTa, GPT).
