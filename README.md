# Non-Identification Project

YoloX모델 사용

## 소개
이 프로젝트는 라벨링 플랫폼을 위한 비식별화 기술을 연구하고 구현하기 위한 프로토타입 모델입니다.<br>
인턴 기간 동안 B2en의 AI Biz팀에서 데이터 품질 관리 업무를 수행하면서 이 사이드 프로젝트를 진행했습니다.<br>

08월 - Deeplearn.ai 강의를 바탕으로 딥러닝을 활용한 컴퓨터 비전 스터디 <br>
10월 - YOLO 모델 논문 리뷰 및 실습 진행 <br>
11월 - 비식별화 모델 고도화 진행하기(Blur, Crop 등)
12월 - 프로젝트 마무리 및 회고 <br>

Custom Class (데이터셋, 모델)
WIDER FACE 데이터셋은 32,203개의 이미지에 393,703개의 얼굴이 라벨링된 데이터셋입니다.

데이터를 변형(Augmentation)
크기 조정(Resize), 수평 반전(Horizontal Flip), 임의 자르기(Random Crop), 색상 변형(Color Jitter), 회전(Rotation), 모자이크(Mosaic Augmentation)

다양한 성능지표(Metric)를 사용해 모델 성능 분석
Classification : Loss, Confusion Matrix, Accuracy, Precision, Recall, F1-score
Segmentation : Loss, IoU, Dice
단순히 ~ 점수가 나왔다는 내용 전달 뿐만 아니라, Metric 사이의 비교, 클래스 사이의 점수 비교 등 구체적인 모델 진단을 하도록 노력해보세요.
ex) F1-score가 80%인데, Precision이 Recall보다 높습니다. Precision이 Recall보다 높은 것은 ~이란 의미고, 데이터의 ~ 한 특성때문에 Precision이 더 높을 것이라고 추정합니다.

실험관리툴(wandb)

** Pytorch의 Image Augmentation 예시입니다. ** 
torch의 transform이 아닌 Albumentations 패키지를 사용했습니다.
변형한 이미지를 저장하고 불러오는 방식이 아닙니다.
train loop에서 데이터를 로딩할 때 40%(augmentation_prob=0.4) 확률로 변형된 이미지를 로드하는 방식입니다.
Epoch을 길게 설정할 수록 모델은 더 다양한 이미지를 입력받습니다.
이 방식의 장점은 로컬 디스크의 용량을 따로 할애하지 않아도 된다는 점입니다.
https://discuss.pytorch.org/t/how-to-increase-number-of-images-with-data-augmentation/45795

## 기간
2022년 8월 10일부터 2022년 12월 10일까지<br>

## 배경
B2en은 데이터 라벨링과 품질 관리를 한 번에 처리할 수 있는 Laflow라는 플랫폼을 출시하였습니다.<br>
비록 인턴 당시에 구현한 비식별화 기술은 실제 플랫폼에 적용되지는 않았으나, 이 활동을 통해 AI 분야에 한걸음 더 다가설 수 있었습니다.<br>
- 관련 기사: [AITimes 기사](https://www.aitimes.com/news/articleView.html?idxno=151928)

## 한계점
- **데이터 수집**: 데이터 수집이 프로젝트에서 가장 큰 문제점 중 하나였습니다.
- 향후 얼굴 뿐만 아니라 다른 개인 정보 관련된 비식별화를 위한 추가적인 데이터를 수집할 수 있다면, 프로젝트의 결과가 더욱 향상될 것으로 예상됩니다.



