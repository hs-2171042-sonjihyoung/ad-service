### 3.2 NLTK

* 라이선스-Apache-2.0 license

#### 3.2.1 설명           
 * 정의 - NLTK (Natural Language Toolkit)는 가장 널리 알려진 고성능 파이썬 NLP 라이브러리다. 주로 영어를 기반으로 하고 있다. 
이 라이브러리를 통해 자연어처리가 되면, 컴퓨터는 이 처리된 정보를 바탕으로 음성 인식, 내용 요약, 번역, 감성 분석, 텍스트 분류 작업을 할 수 있다. 텍스트를 다루기 위한 다양한 도구들을 제공한다. 분류, 토큰화, 스테밍(Stemming), 태깅, 파싱, 시멘틱 추론을 예로 들 수 있다. 

#### 3.2.2기능                 
 * Nltk에서 지원하는 주요 기능은 말뭉치, 토큰 생성, 형태소 분석 등이 있다. 먼저, 말뭉치는 자연어 분석 작업을 위해 만든 샘플 문서 집합을 말한다. 단순히 소설, 신문 등의 문서를 모아놓은 것도 있지만 품사. 형태소, 등의 보조적 의미를 추가하고 쉬운 분석을 위해 구조적인 형태로 정리해 놓은 것을 포함한다. 포함된 기능 중에서 우리가 사용할 기능인 토큰 생성은 단어를 추출하려면, nltk.tokenize 패키지를 안에 있는 word_tokenize 함수를 활용하면 문장에 있는 단어만 추출할 수 있다. 마지막으로 형태소 분석은 단어로부터 어근, 접두사, 접미사, 품사 등 다양한 언어적 속성을 파악하고 이를 이용하여 형태소를 찾아내거나 처리하는 작업이다.

#### 3.2.3 작동하는 과정                    
 * 우리가 사용하는 기능인 토큰 생성의 과정을 설명한다. 파이썬을 사용하여 from nltk.tokenize import word_tokenize 를 사용해주고, 단어를 나눠줄 문장을 리스트로 만들어서 넣어준다. 그 다음 list.word_tokenize를 사용해서 단어를 추출해준다. 추출한 단어는 리스트로 만들어 보여준다.

#### 3.2.4 비슷한 기능을 가지는 오픈소스                              
 * twitter-korean-text 오픈소스- https://github.com/twitter/twitter-korean-text
이 오픈소스에서는 현재 텍스트 정규화와 형태소 분석, 스테밍을 지원하고 있다. 짧은 단어는 물론이고 긴 글도 처리할 수 있다. twitter-korean-text는 normalization, tokenization, stemming, phrase extraction 이렇게 네가지 기능을 지원한다.

 
