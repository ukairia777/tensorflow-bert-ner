# tensorflow-bert-ner
Named Entity Recognition with BERT using TensorFlow 2.0+

Named Entity Recognition (NER) attempts to find a label for each entity in a sentence, such as a person, location, or organization. In this example, learn how to fine-tune a model on the 한국해양대학교 자연언어처리 연구실 데이터셋 (https://github.com/kmounlp/NER) to detect new entities.

## Note
- Only labeling the first token of a given word. Assign -100 to the other subtokens from the same word. so the loss function ignores them.
- If you want to apply it to other dataset, Just Change pre-trained tokenizer, pre-trained language model, dataset.

## NER Sample (Test data)
```
input : '오리온스는 리그 최정상급 포인트가드 김동훈을 앞세우는 빠른 공수전환이 돋보이는 팀이다'
result : [('오리온스', 'B-ORG'), ('는', 'O'), ('리그', 'O'), ('최', 'O'), ('정상급', 'O'), ('포인트', 'O'),
('가드', 'O'), ('김동훈', 'B-PER'), ('을', 'O'), ('앞세우', 'O'), ('는', 'O'), ('빠른', 'O'), ('공수', 'O'),
('전환', 'O'), ('이', 'O'), ('돋보이', 'O'), ('는', 'O'), ('팀', 'O'), ('이', 'O'), ('다', 'O')],
```
