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

- 대중교통 접근성 :  → 
- 보행안전 :  → 
- 주차시설 :  → 

 &nbsp;

### [EDA과정](https://github.com/kim-so-hyeon/Naver-Shopping-Title-Recommendation-Service/blob/develop/NshoppingDBCrawler_hi.py)
- 수집된 데이터의 null값 여부 확인


- 주제&연도별 데이터 현황 파악




 &nbsp;

- 시설 총 합계 / 인구대비 top10


&nbsp;

### 3. 공원 및 녹지·교육환경·청결도

- 공원 및 녹지 :  → 
- 교육환경 :  → 
- 청결도 :  → 
 &nbsp;

### [EDA과정](https://github.com/kim-so-hyeon/Naver-Shopping-Title-Recommendation-Service/blob/develop/NshoppingDBCrawler_hi.py)
- 수집된 데이터의 null값 여부 확인


- 주제&연도별 데이터 현황 파악




 &nbsp;

- 시설 총 합계 / 인구대비 top10



 &nbsp;

### 4. 소음·의료시설·치안 및 방범

- 소음 :  데이터 특성상 → 
- 의료시설 :  → 
- 치안 및 방범 :  → 
 
 &nbsp;

### [EDA과정](https://github.com/ayeongjeong/Seoul-Data-EDA/blob/main/seouldataEDA.ipynb)
- 수집된 데이터의 type확인
![image](https://user-images.githubusercontent.com/64175848/112982185-257d7400-9197-11eb-8e78-8c7011bee3d6.png)
![image](https://user-images.githubusercontent.com/64175848/112982416-6d9c9680-9197-11eb-86cf-60541068cbe3.png)


- 주제&연도별 데이터 현황 파악

![image](https://user-images.githubusercontent.com/64175848/112983368-92ddd480-9198-11eb-8ff7-c1dc5577f4c5.png) ![image](https://user-images.githubusercontent.com/64175848/112983452-ab4def00-9198-11eb-8b96-60d2652429f2.png)




근 3년간 시설(문화&상업) 수량의 큰 변화가 없는 것으로 확인되어 합계로 칼럼 단일화 진행 / 유흥시설의 경우 다년간의 시설 수 확인이 어려워 최신 수량으로 진행

 &nbsp;

- 시설 총 합계 / 인구대비 top10

![image](https://user-images.githubusercontent.com/64175848/112977404-f82dc780-9190-11eb-8da4-4ea7aaa496d9.png)![image](https://user-images.githubusercontent.com/64175848/112980044-54461b00-9194-11eb-86a3-b84468335210.png)

 &nbsp;
