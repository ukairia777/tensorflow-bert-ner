# tensorflow-bert-ner
Named Entity Recognition with BERT using TensorFlow 2.0+

Token classification refers to the task of classifying individual tokens in a sentence. One of the most common token classification tasks is Named Entity Recognition (NER). NER attempts to find a label for each entity in a sentence, such as a person, location, or organization. In this example, learn how to fine-tune a model on the 한국해양대학교 자연언어처리 연구실 데이터셋 (https://github.com/kmounlp/NER) to detect new entities.

## Note
- Only labeling the first token of a given word. Assign -100 to the other subtokens from the same word. so the loss function ignores them.
- If you want to apply it to other dataset, you don't need to change the model architecture. Just Change pre-trained tokenizer, pre-trained language model, dataset.
