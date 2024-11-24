# Ultimate Judgement

I chose the customised fine-tuned model over the augmented one as it gave a good accuracy while having a decent loss that's not as low as the augmented one. The hyperparameter-tuned ResNet50 model is the best choice for real-world activity classification and number of person detection tasks.

It achieves about 74% accuracy for activity classification and 82.22% accuracy for person detection on the holdout dataset, showcasing strong generalisation. The model's architecture leverages pre-trained ResNet50 features, with the last 10 layers trainable, enabling the model to adapt better to the respective task while preserving powerful image representations. Techniques like L2 regularisation (0.02) and dropout (0.5) helped reduce overfitting, while callbacks such as early stopping and learning rate scheduling ensured optimal training efficiency.

## Ethical Challenges in Emotion Recognition Technology:

1. Breach of privacy
Constant monitoring of emotions could infringe on individuals&#39;
privacy which could eventually lead to potential for using emotional
data to manipulate consumer behavior and exploitation of vulnerable
individuals through emotional profiling (Elisabeth Hodl, 2022)

2. Manipulation of data:
Misinterpretation or incorrect recognition of emotions can lead
to biased outcomes in employment, law enforcement, or
healthcare.
3. Psychological Impact:
Risk of creating stereotypes or biased emotional profiles of certain
groups or individuals resulting in continuous monitoring of
emotions might increase anxiety or affect mental well-being
(Gremsl, 2022)

4. Sampling Bias:
Unbalanced datasets that do not represent the population
adequately, causing skewed recognition patterns, and limited
emotional expression types in the dataset might lead to overly
simplified or inaccurate recognition of complex emotions.

## Limitations & Potential Extensions

The model shows some difficulty in distinguishing visually similar activities, like "rowing_a_boat" and "riding_a_bike." This highlights a limitation in handling classes with overlapping features.

Due to the large size of the dataset, performing hyperparameter tuning over multiple parameters could be computationally exhausting. This is another limitation.

Despite these limitations, the model’s strong holdout performance, efficient regularisation, and generalisation make it well-suited for real-world application if some further minor tweaks are applied.

Further enhancements could focus on addressing class imbalances and improving the differentiation of similar activities. This could be done using techniques like SMOTE.

### References:

- Gremsl, Thomas and Hödl, Elisabeth. ‘Emotional AI: Legal and Ethical Challenges 1’. 1 Jan. 2022 : 163 – 174.
MLA
- Katirai, A. Ethical considerations in emotion recognition technologies: a review of the literature. AI Ethics (2023). https://doi.org/10.1007/s43681-023-00307-3