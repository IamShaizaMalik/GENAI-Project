# Legal Textual Entailment Task:

This project addresses the legal entailment task
 using data from the COLIEE competition, focusing on Japanese
 statutory law. Due to the limited availability of high-performing
 legal language models for Japanese and the complexity of
 Japanese legal text, the dataset was translated into English for
 processing. The training data, originally in XML format, was
 parsed and consolidated into a CSV file containing approximately
 1,200 article–hypothesis–label examples. We initially approached
 the task using an embedding-based semantic similarity frame
work by fine-tuning a SentenceTransformer initialized with
 the **nlpaueb/legal-bert-base-uncased model**. Despite implementing Top-K layer fine-tuning and gradual unfreezing to mitigate
 overfitting, the model failed to produce satisfactory results due to
 the dataset’s limited size and the model’s large parameter count.
 Subsequently, we adopted a more lightweight model, legal-bert
small-uncased, and repeated the embedding-based approach.
 However, performance improvements remained marginal. As an
 alternative, we restructured the task as a binary classification
 problem, treating each article-query pair as a natural language
 inference input using standard BERT tokenization and cross
entropy loss. Fine-tuning **legal-bert-small-uncased** under this
 formulation yielded better alignment with entailment labels,
 offering a more robust solution for structured legal reasoning in
 a low-resource setting. Our findings emphasize the importance
 of task formulation and model size when applying transformer
based models to domain-specific entailment problems.
