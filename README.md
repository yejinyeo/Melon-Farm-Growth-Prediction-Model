# Melon Farm Growth Prediction Model
**Tags**: ML / Time Series Analysis

## Introduction
 스마트팜 시스템에서 수집된 참외 농장의 데이터를 활용하여 참외의 생육 상태와 생산량을 예측하는 모델을 개발한 프로젝트입니다. 머신러닝 모델을 활용하여 다양한 환경 조건에서 참외의 생육 상태와 생산량을 예측할 수 있도록 설계되었습니다.

주요 특징:
- **세 가지 예측 모델**을 개발하여 환경 변화에 따른 참외의 생육 및 생산량을 예측함
- **월, 일, 시간** 등의 추가 피처를 활용해 시계열 데이터를 처리하여 RNN 기반 모델보다 우수한 성능을 달성함
- **80% 이상의 결측 데이터**를 다양한 보간법으로 처리하여 데이터 신뢰성 향상시킴


## File Descriptions
- **전처리된 데이터셋**:
  - `env_to_growth.xlsx`: 내부 환경 변수와 생육 상태 변수로 구성된 데이터 (Environment-to-Growth Model에 사용)
  - `env_to_prod.xlsx`: 내부 환경 변수와 생산량 데이터로 구성된 데이터 (Environment-to-Production Model에 사용)
  - `growth_to_yield.xlsx`: 생육 상태 변수와 생산량 데이터로 구성된 데이터 (Growth-to-Yield Model에 사용)

- **모델 코드**:
  - `Growth_Prediction_Model.ipynb`: 내부 환경 데이터를 기반으로 생육 상태를 예측하는 모델 코드
  - `Production_Prediction_Model.ipynb`: 내부 환경 데이터를 기반으로 생산량을 예측하는 모델 코드
  - `Yield_Prediction_Model.ipynb`: 생육 상태 데이터를 기반으로 생산량을 예측하는 모델 코드
 

## Project Structure
1. **Data Collection and Preprocessing**  
   - 불필요한 행과 열을 제거하고, 데이터를 전처리했습니다.
   - 데이터 샘플의 부족한 부분을 보완하기 위해 다른 데이터셋을 활용하여 추가 데이터를 통합하였습니다.

2. **Handling Missing Data**  
   - 약 **80%의 결측치**를 해결하기 위해 다음과 같은 보간 기법을 사용했습니다:
     - 긴 결측 구간은 **전후 값 보간법**으로 채움
     - 짧은 결측 구간은 **스플라인 보간법**을 적용함

3. **Model Development**  
   - **Environment-to-Growth Model**: 내부 환경 데이터를 기반으로 생육 상태를 예측
   - **Growth-to-Yield Model**: 생육 상태 데이터를 기반으로 생산량을 예측
   - **Environment-to-Production Model**: 내부 환경 데이터를 기반으로 생산량을 직접 예측

4. **Evaluation**  
   - 모델 성능은 **평균 제곱 오차 (MSE)**와 **결정 계수 (R² Score)**를 사용하여 평가하였으며, 높은 정확도를 달성하였습니다.
