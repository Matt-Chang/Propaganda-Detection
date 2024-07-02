# Propaganda-Detection

This paper is focused on the Propaganda Techniques corpus (Da San Martino et al., 2020) for the propaganda classification. The
process has been divided into two subtasks: Span Identification (SI) and Technique Classification (TC). SI is a binary sequence
tagging task to identify propaganda. TC is the task of classifying the type of propaganda technique used within the snippet. Bag
of words (BoW) classifier with various experimentation is conducted. Pre-trained large language models, BERT is later used to
compare the model performance. Dynamic padding technique is applied in the BERT training process. Each method
incorporates various hyper-parameter tuning strategies and experimentation. The models' performance is evaluated by assessing
metrics such as F1 score, precision, recall, accuracy, and macro average. Our findings demonstrate that the BERT with dynamic
padding technique achieves comparable results.
