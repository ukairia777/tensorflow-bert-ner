# tensorflow-bert-ner
Named Entity Recognition with BERT using TensorFlow 2.0+

* Dataset : The data is provided from 한국해양대학교 자연언어처리 연구실 (https://github.com/kmounlp/NER)

## Note
- Only labeling the first token of a given word. Assign -100 to the other subtokens from the same word. so the loss function ignores them.
- If you want to apply it to other dataset, you don't need to change the model architecture. Just Change pre-trained tokenizer, pre-trained language model, dataset.
