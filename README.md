# Melanoma Diagnosis
## EDA
1) 클래스 분포 분석
2) 이미지 크기 및 해상도 분석
3) 채널별 색상 분포 분석
4) 병변 위치 및 행태 분석
5) 데이터 다양성 및 Augmantation 필요성 평가

## Preprocessing
1) resized (300x300 -> 244x244)
2) Augmentation(실험을 통해 가장 성능이 좋은 Augmentation 조합 선정)

## Model
1) Resnet
2) EfficientNet
3) VGG
4) DenseNet
5) ViT
6) ConvNeXt
6가지 모델 중 가장 성능이 좋은 모델 선정

## Model Train strategy
다양한 기법을 사용하여 Overfitting 최소화 전략을 실험한 결과, Warm-up Scheduler(Epochs=10) 전략이 가장 성능이 좋았음
최종적으로 선정된 최적 성능 조합을 pth 파일로 만들어 웹앱으로 전달함

## Web&App
flask를 활용하여 웹&앱을 제작
### 주요 기능
1) 사용자가 업로드 한 이미지 기반으로 진단
2) AI 모델 추론 및 병변 특징 추출
   - 병변 위치 감지
   - 병변 박스 시각화(빨간 박스 생성)
   - 병변 특징 추출(ABCD Rule Skin)
3) 결과 시각화 및 저장 기능
