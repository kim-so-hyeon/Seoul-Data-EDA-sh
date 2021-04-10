# Seoul Data Total EDA

### 🙋 구성원 및 담당 소주제

 이름 | 입지 분석 관련 EDA 소주제 | 활용 데이터 
 :---: | :---: | ---| 
`김소현`  | `문화시설` <br> `상업시설` | 1) 서울시 문화공간 <br> 2) 
`윤혜인`  | `대중교통 접근성` <br> `보행안전` <br> `주차시설` | 1) <br> 2) <br> 3) 
`이기쁨`  | `공원` <br> `교육환경` <br> `청결도` | 1) 서울시 주요 공원 현황 <br> 2) <br> 3) 
`정아영`  | `소음` <br> `의료시설` <br> `치안 및 방범`  | 1) 서울시 소음진동민원 현황 통계(2010~2018)<br> 2) 서울시 의료기관 (구별) 통계(2019), 서울특별시 응급실 위치 정보(2020)<br> 3) 서울시 자치구 목적별 cctv 설치 현황(2018), 서울시 시내주요기관(경찰·소방관서) 통계(2019)

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

&nbsp;

### 2-2. 대중교통 접근성·보행안전·주차시설

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

### 2-3. 공원 및 녹지·교육환경·청결도

- 공원 및 녹지 :  공원수, 1인당 공원면적 모두 매년 증가하는 추세로 
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

- 시설 총 합계 / 인구대비 top10



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
<a name="conclusion"> <a/>

## 3. 결론
