### 3.3 Product-categories-classification

* 라이선스-Apache-2.0 license

#### 설명
   * Product-categories-classification은 카카오 아레나- 쇼핑몰 상품 카테고리 분류 대회에 참여해 1등의 성적을 거둔 라임로봇팀의 오픈 소스코드이다.       
   상품 카테고리 분류기로 상품의 타이틀(product 컬럼)과 이미지 특징(img_feat 컬럼)을 입력으로 활용하여 대/중/소/세 카테고리를 예측한다.     
   모델 구조의 심플함에 비해 우수한 카테고리 분류 정확도를 가진다.      

#### 기능
   + 상품의 타이틀(product 컬럼)과 이미지 특징(img_feat 컬럼)만 입력으로 활용   
   + Byte Pair Encoding(BPE) 기반의 word 분절 방법 사용   
   + sub-words로 분절된 word를 LSTM으로 encoding   
   + class imbalance problem을 완화하기 위해 대/중/소/세에 개별 classifier 할당   
   + 클래스 예측 정교화- 4개 classifier의 예측된 distribution에서 가장 높은 확률값을 가지는 대/중.소 세 조합을 탐색   

#### 작동하는 과정(단계)
   - Getting Stared    
      - Step 1: 데이터 다운로드      
      - Step 2: 데이터 준비 및 Vocabulary 생성      
      - Step 3: 학습하기   
      - Step 4: 추론하기   
  
1) 광고 데이터베이스에서 받아온 데이터 다운로드하기 
2) Vocabulary 다운로드- vocab.zip 파일을 다운로드 받아 data/ 디렉터리에서 압축을 해제한다.   
3) dev.h5, text.h5 생성- python preprocess.py make_db dev, python preprocess.py make_db test   
4) pre-trained modes 다운로드- 6개 모델 묶음을 다운로드하여 output/ 디렉터리에 압축을 풀어준다.   
5) 결과파일(dev.tsv, test.tsv)생성 – python inference.py -j 12 -b 2048 –model_dir output/ --div dev, python inference.py -j 12 -b 2048 –model_Dir output/ --div test   
6) 결과파일로 BERT 언어 표현을 사전 학습시키기   

