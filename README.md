# Seoul Data Total EDA

### 🙋 구성원 및 담당 소주제

 이름 | 입지 분석 관련 EDA 소주제 | 활용 데이터 
 :---: | :---: | ---| 
`김소현`  | `문화시설` <br> `상업시설` | 1) 서울시 문화공간(2019) <br> 2) 서울시 지자체 사업체현황 (2019)
`윤혜인`  | `대중교통 접근성` <br> `보행안전` <br> `주차시설` | 1) 서울특별시 버스정류소 위치정보 (2020), 공공자전거 대여소 정보 (2020), 서울교통공사 역주소현황(행정동기준) (2020) <br> 2) 서울시 주차장 확보율 통계 (2020) <br> 3) 서울시 보행환경 만족도 통계 (2019) <br>
`이기쁨`  | `공원` <br> `교육환경` <br> `청결도` | 1) 서울시 공원 (1인당 공원면적) 통계 (2019) <br> 2) 서울시 평생교육기관 (유형별구별) 통계 (2018), 서울시 신고·등록 체육시설 통계 (2019), 도서관의 수 (2021) : 대표(중구) + 국립(강남,서초,영등포구) + 공공도서관(그 외) <br> 3) 서울시 생활안전도 통계 (2018) 
`정아영`  | `소음` <br> `의료시설` <br> `치안 및 방범`  | 1) 서울시 소음진동민원 현황 통계(2010~2018)<br> 2) 서울시 의료기관 (구별) 통계(2019), 서울특별시 응급실 위치 정보(2020)<br> 3) 서울시 자치구 목적별 cctv 설치 현황(2018), 서울시 시내주요기관(경찰·소방관서) 통계(2019)

출처 : [서울 ](https://data.seoul.go.kr/), [서울도서관 | 도서관 찾기](https://lib.seoul.go.kr/slibsrch/main)

&nbsp;

## 📋 Contents
1. [서론](#intro)   
    * 서울시 1인가구현황 분석 
2. [주제별 EDA](#eda)    
    * [문화·상업시설](#facilities)    
    * [대중교통·보행안전·주차시설](#)    
    * [공원·교육환경·청결도](#)    
    * [소음·의료시설·치안및방범](#)    
3. [결론](#conclusion)    

&nbsp;

<a name="intro"> <a/>
 
## 1. 서론
서울의 1인가구는 계속해서 증가하고 있다. 국가통계포털(KOSIS)의 ‘서울시 1인가구 통계’ 데이터를 활용하여 **2015~2019년의 연령별 1인가구 추이**를 분석해본 결과는 아래와 같다.

![image](https://user-images.githubusercontent.com/64175895/114260943-c8918180-9a12-11eb-9e72-f069033e1e92.png)

20세 미만 1인가구를 제외하고는 매년 지속적으로 증가하고 있음을 알 수 있다.
전체 1인가구에서 청년 1인가구가 차지하는 비중이 가장 높지만, 2021년 1월 한겨레 기사(*청년 1인가구 65%는 월세로 산다…공공임대 입주는 1%대*) 에 따르면 청년 1인가구 10명 중 3명은 주거비로 월 소득의 30%이상을 지출하는 주거비 과부담 가구이다. 월 소득 대비 임대료 비율을 나타내는 PIR이 30%를 초과하면 주거비 과부담 가구로 보는데, 이 비중이 청년 1인 가구는 31.4%로 일반가구(26.7%)나 1인가구 평균(30.8%)보다 높았다. 이는 초기 자산이 없어 보증금이 낮고 월세가 높은 형태로 거주하기 때문인 것으로 분석되어, 청년 1인가구의 주거비 과부담 비율이 높은 이유가 공공임대 공급 물량 부족과 관련된 것으로 분석되었다.

![image](https://user-images.githubusercontent.com/64175895/114261423-6dad5980-9a15-11eb-9342-c89e7568de7e.png)
![image](https://user-images.githubusercontent.com/64175895/114261207-53bf4700-9a14-11eb-9199-b2b0ea2c95e1.png)

국토교통부 주거실태조사 자료에 따르면 1인가구가 전체가구에 비해 자가비율이 낮은 것을 알 수 있고, 따라서 증가하는 1인가구를 위한 공공임대 공급을 늘릴 필요가 있다고 생각된다.

올해 매입임대주택 공급 계획은 전국 4만5천호로 역대 최대규모의 공급물량이다. 그 중에서도 청년을 위한 공급물량이 신혼부부나 다자녀 유형에 비해 1만 4500호로 가장 많은 공급계획을 보여주고 있다. (*올해 매입임대주택 4만5천호 공급...역대 최대 규모*) 청년 유형 공급계획은 1인가구를 위한 공급계획이라고 볼 수 있기 때문에, 최근 대두되고 있는 서울 주거문제와 늘어나는 1인가구를 위하여 ‘서울시 1인가구를 위한 공공임대 최적입지 선정 프로젝트’를 진행하였다.    
최적입지 선정을 위한 점수는 국토교통부의 1인가구 주거환경 만족도 조사 항목을 참고하여 선정하였다. `1)상업시설 접근용이성`, `2)의료시설 접근용이성`, `3)문화시설 접근용이성`, `4)도시공원 접근용이성`, `5)대중교통 접근용이성`, `6)주차시설 이용편리성`, `7)보행안전`, `8)교육환경`, `9)치안 및 방범`, `10)소음`, `11)청결도`와 같이 11가지 항목을 바탕으로 최적입지를 선정하였다. 각 항목들을 위한 데이터는 서울열린데이터광장과 서울도서관의 데이터를 활용하였다.

주제별 분석에 들어가기 전 서울시 자치구별 1인가구와 임대주택 현황을 분석해본 결과는 아래와 같다. (서울시 1인가구 데이터 및 임대주택 현황 공공데이터 활용)

![image](https://user-images.githubusercontent.com/64175895/114261359-160eee00-9a15-11eb-8c43-1331a5342d14.png)    
![image](https://user-images.githubusercontent.com/64175895/114261391-42c30580-9a15-11eb-96dc-171f5b161e35.png)

&nbsp;

<a name="eda"> <a/>
## 2. 주제별 EDA


<a name="facilities"> <a/>
 
### 2-1. 문화·상업시설

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

→ 기존 시설 합계 순위와 인구대비 합계 순위 사이에는 차이가 존재하고, 인구 대비로 변경한 데이터를 최종 데이터로 선정하고 스케일링 

&nbsp;

### 2-2. 대중교통 접근성·보행안전·주차시설

- 대중교통 접근성 :  공공자전거(따릉이), 서울시내버스, 지하철 데이터 이용
- 보행안전 :  횡단보도 데이터, 교통사고 데이터, 보행안전 통계 데이터 이용 
- 주차시설 :  주차시설 데이터 이용

 &nbsp;

### [EDA과정](https://github.com/kim-so-hyeon/Naver-Shopping-Title-Recommendation-Service/blob/develop/NshoppingDBCrawler_hi.py)
- 수집된 데이터의 null값 여부 확인
1) 대중교통 접근성
![image](https://user-images.githubusercontent.com/64175848/114267328-cb519e00-9a35-11eb-82f1-e81a7085ce57.png)
![image](https://user-images.githubusercontent.com/64175848/114267346-ecb28a00-9a35-11eb-8f2d-a42248cb002a.png)
![image](https://user-images.githubusercontent.com/64175848/114267357-048a0e00-9a36-11eb-8faa-b0c75670b201.png)

2) 보행안전
![image](https://user-images.githubusercontent.com/64175848/116807790-0f851980-ab70-11eb-92d4-1a983b8e1a12.png)
![image](https://user-images.githubusercontent.com/64175848/116807809-2deb1500-ab70-11eb-8dc3-7ae7d4d425d8.png)
![image](https://user-images.githubusercontent.com/64175848/116807816-3fccb800-ab70-11eb-9ddb-c613decf68c5.png)

3) 주차시설
![image](https://user-images.githubusercontent.com/64175848/116807848-828e9000-ab70-11eb-9b50-c241491e5c80.png)

- 주제&연도별 데이터 현황 파악
1) 대중교통 접근성
![image](https://user-images.githubusercontent.com/64175848/114268476-461db780-9a3c-11eb-92d9-c6f7e97ec80f.png)
![image](https://user-images.githubusercontent.com/64175848/114268504-651c4980-9a3c-11eb-94ed-828f57b59cf2.png)
![image](https://user-images.githubusercontent.com/64175848/114268466-369e6e80-9a3c-11eb-9a33-4fc2b6233187.png)

→ 버스·지하철의 경우는 큰 변화가 있지 않은 데이터로 보이고, 공공자전거의 경우 매년 전체적으로 수가 늘어나고 있는 것으로 확인되어짐

2) 보행안전
![image](https://user-images.githubusercontent.com/64175848/116807897-a7830300-ab70-11eb-887a-d55275e607fe.png)
![image](https://user-images.githubusercontent.com/64175848/116807932-f335ac80-ab70-11eb-9818-a42e086fbb31.png)
![image](https://user-images.githubusercontent.com/64175848/116807944-05174f80-ab71-11eb-852c-53df1f619bdb.png)
→ 연도별로 횡단보도 수는 꾸준히 증가하고 있으며, 자치구별 순위에 큰 변동이 없는 것으로 확인되었다. 신호등 유무로 나눠 살펴볼 때, 강남구를 제외하고는 순위에 큰 차이는 없는 것으로 보임

![image](https://user-images.githubusercontent.com/64175848/116808191-70155600-ab72-11eb-927f-175a247339e4.png)
→ 연도별 교통사고 사망자수는 전체적으로는 줄어들고 있는 것으로 보여지는데, 인구 10만명당 사망자수는 강남에 비해 강북에 위치한 자치구에서 좀 더 높게 나타남 

![image](https://user-images.githubusercontent.com/64175848/116808280-ec0f9e00-ab72-11eb-97c3-b6b8f0e6a8fe.png)

3) 주차시설

![image](https://user-images.githubusercontent.com/64175848/116808323-21b48700-ab73-11eb-9ef1-fca86d528905.png)
→ 자치구별 주차장확보율 추이를 나타냄

&nbsp;

### 2-3. 공원 및 녹지·교육환경·청결도

- 공원 및 녹지 :  공원수, 1인당 공원면적 모두 매년 증가하는 추세로 파악됨
- 교육환경 :  도서관 수에 대한 데이터 낮은 신뢰성(연도별로 증감의 폭이 너무 큼), 도서관 구분: 대표, 국립, 공공, 작은, 장애인, 전문 도서관(6가지 도서관 종류 중 대표, 국립, 공공도서관의 수만 집계)
- 청결도 : 급변하는 부분도 있고 자치구들의 공통적인 특징도 찾기 어려움 / 최근 2년 평균치로 진행

&nbsp;

### [EDA과정](https://github.com/kim-so-hyeon/Naver-Shopping-Title-Recommendation-Service/blob/develop/NshoppingDBCrawler_hi.py)
- 수집된 데이터의 null값 여부 확인
![image](https://user-images.githubusercontent.com/64175848/113707442-e2814a80-971a-11eb-83b8-2930343e090d.png)
![image](https://user-images.githubusercontent.com/64175848/113708752-946d4680-971c-11eb-9db7-878ea2499ef8.png)
![image](https://user-images.githubusercontent.com/64175848/113710094-3fcacb00-971e-11eb-9607-4f342ed7ce9e.png)


- 주제&연도별 데이터 현황 파악
1) 공원 및 녹지
![image](https://user-images.githubusercontent.com/64175848/113708438-2e80bf00-971c-11eb-828c-ffcf9cabaddc.png)
2) 교육환경
![image](https://user-images.githubusercontent.com/64175848/113709777-df3b8e00-971d-11eb-9ebf-14fbd875e0fd.png)
3) 청결도
![image](https://user-images.githubusercontent.com/64175848/113710875-368e2e00-971f-11eb-9db3-05faad07cf39.png)

 &nbsp;

### 2-4. 소음·의료시설·치안 및 방범

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

### EDA 결론
입지 분석 관련 데이터의 특성은 시설과 관련된 정보가 주를 이뤘고, 시설 관련 데이터들은 연도별 큰 차이가 나타나지 않는 것으로 확인되었다. 소음과 

 &nbsp;

<a name="conclusion"> <a/>

## 3. 결론

## 4. Scaled_Dataset EDA

1) 스케일링 방식
- MinMaxScaler(최대값과 최소값이 각각 1, 0이 되도록 스케일링)
- 각 컬럼에 대한 만족도를 점수화하여 평가하는 방식을 채택했기 때문에 모든 값들이 양수로 존재할 수 있는 MinMax로 스케일링을 진행하였다.
- 원래 청결심각수준과 소음민원은 점수가 높을수록 심각하고 안좋은 데이터라서 스케일링하기 전에 미리 음수(-)로 변환하여 스케일링 하였다. 

2) 1인당
- 사용한 데이터의 기간에 맞게 해당 자치구의 년도에 맞는 인구수를 나눠서 각 컬럼의 1인당 데이터를 스케일링하여 사용하였다.

3) 스케일링된 데이터셋에 대한 분석

![heatmap](https://user-images.githubusercontent.com/64175151/116783713-4fde8c00-aacb-11eb-9dd4-143865cbd96d.png)
- 공원면적 : 문화시설수, 대중교통, 주차시설, 보행안전, 상업시설수와 양의 상관관계를 가졌으며 특히 문화시설수와의 관계성이 더 크다. 이는 1인당 공원면적이 넓을수록 1인당 문화시설수가 더 많은 경향을 보인다는 것이다. 또한 공원면적이 넓을수록 청결도가 더 안좋아지는 모습을 보인다.
- 교육 : 의료기관과 상업시설수에 더 큰 양의 상관관계를 보이며 평생교육학습관, 도서관, 체육시설 등의 교육 관련 시설이 많을수록 소음이 더 심각해진다.
- 청결심각수준 : 대중교통, 주차시설, 보행안전, 상업시설수, 문화시설수 등에서 좋은 점수를 얻을수록 청결도는 훨씬 심각해진다(강한 음의 상관관계).
- 소음민원 : 비슷한 성격의 청결심각수준을 제외한 모든 컬럼에 대해 음의 상관관계를 갖는다.
- 의료기관 : 치안방법과 강한 양의 상관관계를 가지고 교육, 청결심각수준을 제외하고는 모두 음의 상관관계를 갖는다.
- 문화시설수, 상업시설수, 보행안전, 주차시설, 대중교통 : 청결심각수준, 소음민원, 의료기관, 치안방범과는 음의 상관관계를 갖고 나머지 변수와는 양의 상관관계를 갖는다. 특히 문화시설수, 상업시설수, 보행안전, 주차시설, 대중교통이 서로 관계가 큰 것 같다.

![heatmap2](https://user-images.githubusercontent.com/64175151/116803734-3f72f380-ab55-11eb-8468-5df9644698bf.png)
-

![boxplot](https://user-images.githubusercontent.com/64175151/116783754-80bec100-aacb-11eb-9331-a29114bbea51.png)
-
