# Seoul Data Total EDA

&nbsp;

### 👉구성원 및 담당 소주제

| 구성원 이름          | 입지 분석 관련 EDA 소주제 |
| :-----------------------: | :------------------------------------------------------------: |
|       `김소현`        | `문화시설` & `상업시설` |
|       `윤혜인`        | `대중교통 접근성` & `보행안전` & `주차시설` |
|       `이기쁨`        | `공원 및 녹지` & `교육환경` & `청결도` |
|       `정아영`        | `소음` & `의료시설` & `치안 및 방범`  |

&nbsp;

### 1. 문화·상업시설

- 문화시설 : 영화관 수, 민간·공공 공연장, 자치구별 인구수 → 자치구별 인구 대비 문화시설 수 최종 칼럼 도출
- 상업시설 : 교육 서비스업, 도매 및 소매업, 숙박 및 음식점업, 공공행정 국방 및 사회보장 행정,  예술 스포츠 및 여가관련 서비스업, 자치구별 인구수 → 자치구별 인구 대비 상업시설 수 최종 칼럼 도출

 &nbsp;

### [EDA과정](https://github.com/kim-so-hyeon/Naver-Shopping-Title-Recommendation-Service/blob/develop/NshoppingDBCrawler_hi.py)
- 수집된 데이터의 null값 여부 확인
![image](https://user-images.githubusercontent.com/64175848/111867760-6a482480-89b9-11eb-8e8e-025c70390816.png)
![image](https://user-images.githubusercontent.com/64175848/113703258-88ca5180-9715-11eb-82ab-e4ae321a4072.png)

- 주제&연도별 데이터 현황 파악
![image](https://user-images.githubusercontent.com/64175848/111867603-80a1b080-89b8-11eb-8768-72c5ce8092b0.png)
![image](https://user-images.githubusercontent.com/64175848/113703458-d21aa100-9715-11eb-8fae-e89bb29341f0.png)


→ 근 3년간 시설(문화&상업) 수량의 큰 변화가 없는 것으로 확인되어 합계로 칼럼 단일화 진행

 &nbsp;

- 시설 총 합계 / 인구대비 top6

![image](https://user-images.githubusercontent.com/64175848/113706787-0c863d00-971a-11eb-837d-137c22433dce.png)

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
- 교육환경 :  도서관 수에 대한 데이터 낮은 신뢰성(연도별로 증감의 폭이 너무 큼), 도서관 구분: 대표, 국립, 공공, 작은, 장애인, 전문 도서관(6가지 도서관 종류 중 대표, 국립, 공공도서관의 수만 집계)
- 청결도 :  → 

&nbsp;

### [EDA과정](https://github.com/kim-so-hyeon/Naver-Shopping-Title-Recommendation-Service/blob/develop/NshoppingDBCrawler_hi.py)
- 수집된 데이터의 null값 여부 확인
![image](https://user-images.githubusercontent.com/64175848/113707442-e2814a80-971a-11eb-83b8-2930343e090d.png)
![image](https://user-images.githubusercontent.com/64175848/113708752-946d4680-971c-11eb-9db7-878ea2499ef8.png)


- 주제&연도별 데이터 현황 파악
1) 공원 및 녹지
![image](https://user-images.githubusercontent.com/64175848/113708438-2e80bf00-971c-11eb-828c-ffcf9cabaddc.png)
2) 교육환경
![image](https://user-images.githubusercontent.com/64175848/113709641-b4513a00-971d-11eb-8bff-7ba114f0132d.png)


 &nbsp;

- 시설 총 합계 / 인구대비 top10



 &nbsp;

### 4. 소음·의료시설·치안 및 방범

- 소음 : 데이터 특성상 연도별 변화가 가장 두드러지게 나타났으며, 입지 선정에 있어 마이너스적인 요소로 진행
- 의료시설 : 시설의 경우 변화가 거의 없는 것으로 파악되며 응급실 현황 컬럼 사용
- 치안 및 방범 : 방범용 CCTV & 안전비상벨 컬럼 사용
 
 &nbsp;

### [EDA과정](https://github.com/ayeongjeong/Seoul-Data-EDA/blob/main/seouldataEDA.ipynb)
- 수집된 데이터의 type확인
![image](https://user-images.githubusercontent.com/64175848/112982185-257d7400-9197-11eb-8e78-8c7011bee3d6.png)
![image](https://user-images.githubusercontent.com/64175848/112982416-6d9c9680-9197-11eb-86cf-60541068cbe3.png)


- 주제&연도별 데이터 현황 파악
1) 소음
![image](https://user-images.githubusercontent.com/64175848/112983965-3f1fbb00-9199-11eb-94cd-605e82c45260.png)

   → 소음민원 건수는 연간 증가 추세 / 자치구별 9년간(2010-2018)의 소음민원 합계를 보면 **강남구**가 독보적

![image](https://user-images.githubusercontent.com/64175848/113700848-4ce1bd00-9712-11eb-84e0-021867f9a66f.png)

   → 연도별 소음민원 건수의 변화를 보면, 가장 최신 데이터인 2018년의 빨간 실선을 기준으로 민원이 가장 많은 강남구는 계속해서 민원이 증가해온 것을 볼 수 있고, 은평구와 성북구, 광진구, 관악구 등은 민원 건수가 줄어든 것을 확인할 수 있다.

2) 의료시설
![image](https://user-images.githubusercontent.com/64175848/113701772-8e269c80-9713-11eb-9aa5-53c76a14aef6.png)

3) 치안 및 방범

![image](https://user-images.githubusercontent.com/64175848/113704930-bf08d080-9717-11eb-9580-bdfa8e58dd86.png)

 &nbsp;

- 인구대비 데이터 스케일링 

![image](https://user-images.githubusercontent.com/64175848/113707184-7a326900-971a-11eb-85ca-aa7c405c0164.png)


 &nbsp;
