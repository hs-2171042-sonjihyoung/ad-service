### 3.6 TensorFlow Extended



#### 3.6.1 License 

Apache 2.0 License


#### 3.6.2 설명

TensorFlow 기반 Google 프로덕션 규모의 ML(머신러닝) 플랫폼이다. 기계 학습 시스템의 정의, 실행 및 모니터링하는 데 필요한 공통 구성 요소를 통합하기 위한 구성 프레임워크 및 공유 라이브러리를 제공한다.

TFX를 사용하면 프로덕션 소프트웨어 배포와 모범 사례에 대한 요구사항 중 다수를 포함하는 프로덕션 ML 파이프라인을 만들 수 있다. 이는 데이터를 내부 데이터화하는 단계부터 시작해 데이터 유효성 검사, 특징 추출, 훈련, 평가, 서빙의 순서로 흘러간다.


#### 3.6.3 기능

TFX는 아래 세가지를 제공한다.

- ml pipeline과 build를 위한 toolkit
  - tfx pipeline 쓰면 airflow, apach beam, kubeflow 등에서 ml 워크플로우 조정 가능
- 표준 구성 요소
  - 파이프라인의 일부 혹은 모델 학습 스크립트에 일부로 사용될 수 있는 표준 구성요소의 집합
- TFX 라이브러리
  - TensorFlow Data Validation(TFDV) : 머신러닝 데이터를 분석하고 검증하기 위한 라이브러리 확장성이 뛰어나고 TensorFlow 및 TFX와 원활하게 연동되도록 설계됐다.
  - TensorFlow Transform(TFT) : TensorFlow를 사용하여 데이터를 전처리하기 위한 라이브러리
  - TensorFlow : TFX를 통한 모델 학습에 사용된다. 학습 데이터 및 모델링 코드를 수집하며 SavedModel 결과를 생성. 또한 입력 데이터 사전 처리를 위해 TensorFlow Transform에서 생성한 특성 추출 파이프라인을 통합한다.
  - TensorFlow Model Analysis(TFMA) : 모델을 평가하기 위한 라이브러리. TensorFlow와 함께 사용되어 EvalSavedModel을 생성하며, EvalSavedModel은 분석의 기초가 된다. TFMA를 통해 사용자는 트레이너에 정의된 것과 동일한 측정항목을 사용하여 분산된 방식으로 대량의 데이터에서 모델을 평가한다. 이러한 측정항목은 다양한 데이터 슬라이스에 걸쳐 계산되어 Jupyter 메모장에서 시각화될 수 있다.
  - TensorFlow Metadata(TFMD) : TensorFlow를 사용하여 머신러닝 모델을 학습시킬 때 유용한 메타데이터의 표준 표현을 제공한다. 메타데이터는 입력 데이터 분석 중에 수동으로 또는 자동으로 생성될 수 있으며, 데이터 유효성 검사, 탐색 분석 및 변환에 사용된다. 메타데이터 직렬화 형식에는 아래 두가지가 포함된다.
  - ML Metadata(MLMD) : ML 개발자 및 데이터 과학자 워크플로와 관련된 메타데이터를 기록하고 검색하기 위한 라이브러리. 대체로 메타데이터는 위에서 말한 TFMD 표현을 사용한다. MLMD는 SQL-Lite, MySQL 및 기타 유사한 데이터 저장소를 사용하여 지속성을 관리한다.


#### 3.6.4 작동 과정

TensorFlow 환경에서 학습된 딥러닝 모델을 사용자에게 서빙하는 여러 가지 방법 중 TensorFlow Serving REST API를 인퍼런스 결과를 반환하는 방법을 사용한다. 이 방법은 웹 프레임워크를 이용하는 경우와 비교하여 일반적으로 처리 속도가 빠르다는 장점이 있다. 
