# 🧠 MNIST CNN Classification

이 프로젝트는 **MNIST 손글씨 숫자 이미지 데이터셋(28×28 흑백)**을 대상으로  
**합성곱 신경망(CNN, Convolutional Neural Network)** 을 이용하여 **0~9 숫자 분류**를 수행합니다.  

---

## 📂 프로젝트 구조
- `CNN(Mnist).ipynb` : Jupyter Notebook (학습 및 결과 시각화)
- `README.md` : 프로젝트 설명 파일

---

## 🚀 주요 기능

### 🔹 데이터 전처리
- `mnist.load_data()`를 이용해 데이터셋 불러오기
- `(28,28)` → `(28,28,1)` 형태로 reshape (CNN 입력 형태)
- 픽셀값을 `0~1` 범위로 정규화

### 🔹 CNN 모델 구성
- `Conv2D(32, 3x3, relu)` + `Conv2D(64, 3x3, relu)`
- `MaxPooling2D(2x2)`으로 다운샘플링
- `Dropout` 으로 과적합 방지
- `Flatten → Dense(128, relu) → Dropout(0.5)`
- `Dense(10, softmax)` 출력층 (0~9 클래스)

### 🔹 모델 학습
- **Optimizer**: Adam
- **Loss function**: categorical_crossentropy
- **Metrics**: accuracy
- 학습 후 `train accuracy`, `validation accuracy` 그래프 시각화

---

## 📊 학습 결과 (예시)
- 훈련 정확도: 약 **99%**  
- 검증 정확도: 약 **98%**  
