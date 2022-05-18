## Hand Gesture Recognition [2022.04.12 ~ 2022.05.14]
## 데이크루 2기, 첫번째 프로젝트 [SITE LINK](https://dacon.io/codeshare/4956?page=1&dtype=recent)
### 멤버 : 전다운(프로젝트 팀장), 강수연, 이태범, 허지혜

1. 한 손 동작을 인식하여 4가지 동작(yes, no, rotate, shake)을 분류하고 화면에 나타내는 프로젝트<br>
-> 한 손으로 인식을 잘 못하고 동작의 시퀀스도 비슷하여 분류를 잘 못하는 문제를 발견<br>
2. 두 손 동작을 인식하여 4가지 동작(yes, no, good, heart)를 분류하고 화면에 나타내는 프로젝트<br>


## 한 손 인식 (examples 폴더 참고)
### Pipeline
- create_dataset
    - mediapipe를 활용하여 웹캠이미지로부터 손동작 좌표를 추출하여 데이터셋을 직접 생성합니다.
- train_hand_gesture
    - tensorflow를 활용하여 LSTM 모델을 학습시킵니다.
    - 학습 metric을 시각화하여 학습 상태를 확인합니다.
    - tensorflow lite 모델로 변환합니다.
- test_hand_gesture
    - keras h5 model을 동작 테스트합니다.
- test_model_tflite
    - tensorflow lite 모델을 테스트합니다.

</br>

### Setting Develop Enviorments
- conda env 생성
```
conda create -n mp python=3.8
```
- conda env activate
```
conda actiavate mp
```
- python lib install(requirements.txt가 있는 디렉토리로 이동)
```
pip install -r requirements.txt
```

</br>

### Examples Execution
1. examples/create_dataset.py : 데이터 촬영 및 생성
2. examples/train_hand_gesture.ipynb : 모델 학습
2. examples/test_hand_gesture.py : LSTM 모델 테스트
2. examples/test_model_tflite.py : LSTM TFlite 모델 테스트
 
</br>

### Directory Structure
```
.
├─dataset(git 미포함)
│      gesture_1.npy
│      gesture_2.npy
│      gesture_3.npy
│      gesture_4.npy
│
├─examples
│      create_dataset.py
│      test_hand_gesture.py
│      test_model_tflite.py
│      train_hand_gesture.ipynb
│
└─models(git 미포함)
        hand_gesture_classifier.h5
        hand_gesture_classifier.tflite
```
