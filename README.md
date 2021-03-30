# Seoul Data Total EDA

&nbsp;

### 👉구성원 및 담당 소주제

| 구성원 이름          | 입지 분석 관련 EDA 소주제 |
| :-----------------------: | :------------------------------------------------------------: |
|       `김소현`        | `문화시설` & `상업시설` & `유흥시설` |
|       `윤혜인`        | `대중교통 접근성` & `보행안전` & `주차시설` |
|       `이기쁨`        | `공원 및 녹지` & `교육환경` & `청결도` |
|       `정아영`        | `소음` & `의료시설` & `치안 및 방범`  |

&nbsp;

### 1. 문화·상업·유흥시설

- 문화시설 : 영화관 수, 민간·공공 공연장, 자치구별 인구수 → 자치구별 인구 대비 문화시설 수 최종 칼럼 도출
- 상업시설 : 교육 서비스업, 도매 및 소매업, 숙박 및 음식점업, 공공행정 국방 및 사회보장 행정, 자치구별 인구수 → 자치구별 인구 대비 상업시설 수 최종 칼럼 도출
- 유흥시설 : 예술 스포츠 및 여가관련 서비스업, 유흥 관련 시설, 자치구별 인구수 → 자치구별 인구 대비 시설 수 최종 칼럼 도출

 &nbsp;

### [EDA과정](https://github.com/kim-so-hyeon/Naver-Shopping-Title-Recommendation-Service/blob/develop/NshoppingDBCrawler_hi.py)
- 수집된 데이터의 null값 여부 확인
![image](https://user-images.githubusercontent.com/64175848/111867760-6a482480-89b9-11eb-8e8e-025c70390816.png)
![image](https://user-images.githubusercontent.com/64175848/112956498-7f704080-917b-11eb-9338-770fd199053f.png)
![image](https://user-images.githubusercontent.com/64175848/112954885-ceb57180-9179-11eb-9a5a-b56319496eb2.png)

- 주제&연도별 데이터 현황 파악
![image](https://user-images.githubusercontent.com/64175848/111867603-80a1b080-89b8-11eb-8768-72c5ce8092b0.png)
![image](https://user-images.githubusercontent.com/64175848/112855372-b269f400-90e9-11eb-9abd-2727ad67c846.png)


근 3년간 시설(문화&상업) 수량의 큰 변화가 없는 것으로 확인되어 합계로 칼럼 단일화 진행 / 유흥시설의 경우 다년간의 시설 수 확인이 어려워 최신 수량으로 진행

 &nbsp;

- 시설 총 합계 / 인구대비 top10

![image](https://user-images.githubusercontent.com/64175848/112977404-f82dc780-9190-11eb-8da4-4ea7aaa496d9.png)![image](https://user-images.githubusercontent.com/64175848/112980044-54461b00-9194-11eb-86a3-b84468335210.png)

&nbsp;

### 2. 대중교통 접근성·보행안전·주차시설

- 문화시설 : 영화관 수, 민간·공공 공연장, 자치구별 인구수 → 자치구별 인구 대비 문화시설 수 최종 칼럼 도출
- 상업시설 : 교육 서비스업, 도매 및 소매업, 숙박 및 음식점업, 공공행정 국방 및 사회보장 행정, 자치구별 인구수 → 자치구별 인구 대비 상업시설 수 최종 칼럼 도출
- 유흥시설 : 예술 스포츠 및 여가관련 서비스업, 유흥 관련 시설, 자치구별 인구수 → 자치구별 인구 대비 상업시설 수 최종 칼럼 도출

 &nbsp;

### [EDA과정](https://github.com/kim-so-hyeon/Naver-Shopping-Title-Recommendation-Service/blob/develop/NshoppingDBCrawler_hi.py)
- 수집된 데이터의 null값 여부 확인
![image](https://user-images.githubusercontent.com/64175848/111867760-6a482480-89b9-11eb-8e8e-025c70390816.png)
![image](https://user-images.githubusercontent.com/64175848/112956498-7f704080-917b-11eb-9338-770fd199053f.png)
![image](https://user-images.githubusercontent.com/64175848/112954885-ceb57180-9179-11eb-9a5a-b56319496eb2.png)

- 주제&연도별 데이터 현황 파악
![image](https://user-images.githubusercontent.com/64175848/111867603-80a1b080-89b8-11eb-8768-72c5ce8092b0.png)
![image](https://user-images.githubusercontent.com/64175848/112855372-b269f400-90e9-11eb-9abd-2727ad67c846.png)


근 3년간 시설(문화&상업) 수량의 큰 변화가 없는 것으로 확인되어 합계로 칼럼 단일화 진행 / 유흥시설의 경우 다년간의 시설 수 확인이 어려워 최신 수량으로 진행

 &nbsp;

- 시설 총 합계 / 인구대비 top10

![image](https://user-images.githubusercontent.com/64175848/112977404-f82dc780-9190-11eb-8da4-4ea7aaa496d9.png)![image](https://user-images.githubusercontent.com/64175848/112980044-54461b00-9194-11eb-86a3-b84468335210.png)

&nbsp;

### 3. 공원 및 녹지·교육환경·청결도

- 공원 및 녹지 :  → 
- 교육환경 :  → 
- 청결도 :  → 
 &nbsp;

### [EDA과정](https://github.com/kim-so-hyeon/Naver-Shopping-Title-Recommendation-Service/blob/develop/NshoppingDBCrawler_hi.py)
- 수집된 데이터의 null값 여부 확인
![image](https://user-images.githubusercontent.com/64175848/111867760-6a482480-89b9-11eb-8e8e-025c70390816.png)
![image](https://user-images.githubusercontent.com/64175848/112956498-7f704080-917b-11eb-9338-770fd199053f.png)
![image](https://user-images.githubusercontent.com/64175848/112954885-ceb57180-9179-11eb-9a5a-b56319496eb2.png)

- 주제&연도별 데이터 현황 파악
![image](https://user-images.githubusercontent.com/64175848/111867603-80a1b080-89b8-11eb-8768-72c5ce8092b0.png)
![image](https://user-images.githubusercontent.com/64175848/112855372-b269f400-90e9-11eb-9abd-2727ad67c846.png)


근 3년간 시설(문화&상업) 수량의 큰 변화가 없는 것으로 확인되어 합계로 칼럼 단일화 진행 / 유흥시설의 경우 다년간의 시설 수 확인이 어려워 최신 수량으로 진행

 &nbsp;

- 시설 총 합계 / 인구대비 top10

![image](https://user-images.githubusercontent.com/64175848/112977404-f82dc780-9190-11eb-8da4-4ea7aaa496d9.png)![image](https://user-images.githubusercontent.com/64175848/112980044-54461b00-9194-11eb-86a3-b84468335210.png)

 &nbsp;

### 4. 소음·의료시설·치안 및 방범

- 소음 :  → 
- 의료시설 :  → 
- 치안 및 방범 :  → 
 
 &nbsp;

### [EDA과정](https://github.com/ayeongjeong/Seoul-Data-EDA/blob/main/seouldataEDA.ipynb)
- 수집된 데이터의 null값 여부 확인
![image](https://user-images.githubusercontent.com/64175848/111867760-6a482480-89b9-11eb-8e8e-025c70390816.png)
![image](https://user-images.githubusercontent.com/64175848/112956498-7f704080-917b-11eb-9338-770fd199053f.png)
![image](https://user-images.githubusercontent.com/64175848/112954885-ceb57180-9179-11eb-9a5a-b56319496eb2.png)

- 주제&연도별 데이터 현황 파악
![image](https://user-images.githubusercontent.com/64175848/111867603-80a1b080-89b8-11eb-8768-72c5ce8092b0.png)
![image](https://user-images.githubusercontent.com/64175848/112855372-b269f400-90e9-11eb-9abd-2727ad67c846.png)


근 3년간 시설(문화&상업) 수량의 큰 변화가 없는 것으로 확인되어 합계로 칼럼 단일화 진행 / 유흥시설의 경우 다년간의 시설 수 확인이 어려워 최신 수량으로 진행

 &nbsp;

- 시설 총 합계 / 인구대비 top10

![image](https://user-images.githubusercontent.com/64175848/112977404-f82dc780-9190-11eb-8da4-4ea7aaa496d9.png)![image](https://user-images.githubusercontent.com/64175848/112980044-54461b00-9194-11eb-86a3-b84468335210.png)

 &nbsp;



























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
