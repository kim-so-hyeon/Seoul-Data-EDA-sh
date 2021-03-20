# Seoul Data Total EDA

&nbsp;

### 구성원 및 역할 분담

| 구성원 이름          | 입지 분석 관련 EDA 주제                                                         |
| ----------------------- | ------------------------------------------------------------ |
|       `김소현`        | `문화시설` & `상업시설` & `유흥시설`              |
|       `윤혜인`        | `대중교통접근성` & `보행안전` & `주차시설` |
|       `이기쁨`        | `공원 및 녹지` & `교육환경` & `청결도` |
|       `정아영`        | `소음` & `의료시설` & `치안 및 방범`  |

&nbsp;

---
## 전처리 과정

- [입지 분석 관련 주제별 EDA](#김소현-EDA)
- [스케일링 작업](#텍스트-특수기호-클렌징-작업)
- [워드클라우드 함수화](#워드클라우드-함수화)

 &nbsp;

### [김소현 EDA](https://github.com/kim-so-hyeon/Naver-Shopping-Title-Recommendation-Service/blob/develop/NshoppingDBCrawler_hi.py)

![스크린샷, 2020-08-14 15-50-55](https://user-images.githubusercontent.com/64175895/90222165-7b8aea80-de46-11ea-89a0-9286b278c23e.png)
Requests, BeautifulSoup 크롤링 / Background_tasks 스케쥴링 → 모델링 학습 데이터 및 WordCloud

### [텍스트 특수기호 클렌징 작업](https://github.com/kim-so-hyeon/Naver-Shopping-Title-Recommendation-Service/blob/develop/MakeResultVal_hi.ipynb)

![스크린샷, 2020-08-14 16-23-31](https://user-images.githubusercontent.com/64175895/90224385-88a9d880-de4a-11ea-9cc6-7e8501f4b23e.png)

### [워드클라우드 함수화](https://github.com/kim-so-hyeon/Naver-Shopping-Title-Recommendation-Service/blob/develop/Naver%20shopping%20preprocessing.ipynb)

![스크린샷, 2020-08-14 16-25-14](https://user-images.githubusercontent.com/64175895/90224535-c60e6600-de4a-11ea-88d6-332f8e4d0286.png)

&nbsp;

---

## 모델 설계 및 구현

### 모델 선정
1. LSTM
- 네이버 쇼핑에 검색된 상품 제목으로, 등록하려는 상품의 쇼핑검색 상위 노출 여부를 예측할 수 있을 것이다. 일반적으로 네이버 스마트 스토어 / 윈도에 상품을 등록할 때, 네이버 쇼핑검색 상위에 노출되는 상품을 참고하여 등록
2. CNN - Convolution1D
- 네이버 쇼핑에 검색된 상품 제목으로, 등록하려는 상품의 쇼핑검색 상위 노출 여부를 예측할 수 있을 것이다. 일반적으로 네이버 스마트 스토어 / 윈도에 상품을 등록할 때, 네이버 쇼핑검색 상위에 노출되는 상품을 참고하여 등록

&nbsp;

### 모델 평가 

![스크린샷, 2020-08-14 16-32-59](https://user-images.githubusercontent.com/64175895/90225203-e1c63c00-de4b-11ea-9e4b-9f68c92301c1.png)

CNN 모델의 한계점
1. 과적합 : traon 데이터는 loss가 줄어드는 모습을 보이지만, test 데이터는 loss 상승
2. Precision이 낮음

&nbsp;

### 모델을 이용한 서비스 구조

![스크린샷, 2020-08-14 16-36-25](https://user-images.githubusercontent.com/64175895/90225432-54371c00-de4c-11ea-8886-ad480c20a239.png)

&nbsp;
