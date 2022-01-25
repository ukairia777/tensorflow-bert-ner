# tensorflow-bert-ner
Named Entity Recognition with BERT using TensorFlow 2.0+

Named Entity Recognition (NER) attempts to find a label for each entity in a sentence, such as a person, location, or organization. In this example, learn how to fine-tune a model on the 한국해양대학교 자연언어처리 연구실 dataset (https://github.com/kmounlp/NER) to detect new entities.

## Note(English)
- If you want to apply it to other (language) dataset, Just Change pre-trained tokenizer, pre-trained language model, dataset.
- Only labeling the first token of a given word. Assign -100 to the other subtokens from the same word. so the loss function ignores them.

## Note(Korean)
- 만약 다른 데이터셋에 대해서 실험하고 싶다면 사전 훈련된 언어 모델과 토크나이저만 변경하면 됩니다.  
- 하나의 단어가 서브워드로 분할되면, 첫번째 토큰에 대해서만 예측하고 그 뒤의 토큰들에 대해서는 정수가 -100으로 부여되어 손실을 계산하지 않습니다.  

## Model Performance (Test data)
Epoch: 3 (without callbacks)

Epoch | f1-score
-|-
1 | 84.55
2 | 87.25
3 | 88.20

## NER Sample (Test data)
```
input : '오리온스는 리그 최정상급 포인트가드 김동훈을 앞세우는 빠른 공수전환이 돋보이는 팀이다'
result : [('오리온스', 'B-ORG'), ('는', 'O'), ('리그', 'O'), ('최', 'O'), ('정상급', 'O'), ('포인트', 'O'),
('가드', 'O'), ('김동훈', 'B-PER'), ('을', 'O'), ('앞세우', 'O'), ('는', 'O'), ('빠른', 'O'), ('공수', 'O'),
('전환', 'O'), ('이', 'O'), ('돋보이', 'O'), ('는', 'O'), ('팀', 'O'), ('이', 'O'), ('다', 'O')],
```
```
input : '하이신사에 속한 섬들도 위로 솟아 있는데 타인은 살고 있어요'
result : [('하이', 'B-LOC'), ('신사', 'I-LOC'), ('에', 'O'), ('속한', 'O'), ('섬', 'O'), ('들', 'O'),
('도', 'O'), ('위', 'O'), ('로', 'O'), ('솟', 'O'), ('아', 'O'), ('있', 'O'), ('는데', 'O'), ('타인', 'O'),
('은', 'O'), ('살', 'O'), ('고', 'O'), ('있', 'O'), ('어요', 'O')],
```
```
input : '유원준 연구원은 심심해서 탐앤탐스에서 커피를 마시면서 BERT 기반의 개체명 인식기를 만들었다.'
result : [('유원준', 'B-PER'), ('연구원', 'O'), ('은', 'O'), ('심심', 'O'), ('해서', 'O'), ('탐', 'B-ORG'),
('앤', 'I-ORG'), ('탐스', 'I-ORG'), ('에서', 'O'), ('커피', 'O'), ('를', 'O'), ('마시', 'O'), ('면서', 'O'),
('BERT', 'O'), ('기반', 'O'), ('의', 'O'), ('개체', 'O'), ('명', 'O'), ('인식', 'O'), ('기', 'O'), ('를', 'O'),
('만들', 'O'), ('었', 'O'), ('다', 'O'), ('.', 'O')]
```
