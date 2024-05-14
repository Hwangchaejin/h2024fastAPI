# EPL 팀 - 트위어 감정 데이터세트 프로젝트
## 잉글랜드 프리미어 리그 - 트위터 감정 데이터세트
![ddfs](https://github.com/Hwangchaejin/h2024fastAPI/assets/79899665/4734a631-49ab-4147-a7cc-d1baa0261d8b)
![images](https://github.com/Hwangchaejin/h2024fastAPI/assets/79899665/6d105cfa-022b-4610-89a2-74377b005f46)
## 1. 개요
### 1.1 정의
EPL은 영국 프리미어리그(English Premier League)의 줄임말을 뜻한다.
이 리그에는 맨체스터 유나이티드, 리버풀, 첼시, 아스널 등과 같은 유명한 축구 팀들이 속해 있다.\
![cooc](https://github.com/Hwangchaejin/h2024fastAPI/assets/79899665/17e22207-d305-4736-98f5-f46f00b233e4)
### 1.2 EPL 감정/열정 영향력
EPL의 서포터 열정은 상당히 높다. 영국 프리미어리그는 세계적으로 가장 인기 있는 축구 리그 중 하나로,\
각 팀의 팬들은 그들이 사랑하는 팀을 열정적으로 응원한다. 
경기장은 항상 활기차고 무대 인근의 팬들은 팀을 위해 모든 것을 다할 준비가 되어 있다. 
경기 전후에는 다양한 소셜 미디어 플랫폼에서 토론이 벌어지고, 승리나 패배에 대한 열정적인 의견이 공유된다.
전 세계적으로 EPL을 지지하는 팬들은 그들의 팀에 대한 애정과 열정을 넘어서서 종종 경기장에까지 여행하고 있다.\
![스크린샷 2024-05-14 103907](https://github.com/Hwangchaejin/h2024fastAPI/assets/79899665/678f2ec3-dcbb-4c36-a5d2-de11d63c55b1)
# A4 용지를 한장정도 채울 것 

## 2. 데이터
2020년 7월 12일부터 2020년 9월 19일까지의 데이터를 조사해봤다\


### 2.1 데이터 구성
+ 데이터 열 이름
"created_at","file_name","followers","friends","group_name",\
"location","retweet_count","screenname","search_query","text",\
"twitter_id","username","polarity","partition_0","partition_1"\
## 극성 팬들이 많은 팀 TOP12
![스크린샷 2024-05-14 105222](https://github.com/Hwangchaejin/h2024fastAPI/assets/79899665/ad851b84-e69a-4d81-92ea-62f4744d872f)\
### 맨체스터 유나이티드 1위\
### 리버풀 2위\
### 아스날 3위로 집계되고 있다.

기본적인 정보 : 어떠한 데이터인지, 총 데이터 건 수

### 2.2 추출한 데이터 (반응)
대량의 데이터에서 잉글랜드 프리미어 리그의 열정 영역을 추출해볼것이다
EPL 팀 - 트위터 감정 데이터세트

### 2.3 추출한 데이터에 대한 탐색적 데이터 분석
1~5점 척도인 경우에는 분포
리뷰 문장의 길이
연도별, 장소별 등등 데이터의 부가정보를 바탕으로 데이터를 탐색하는 (pandas, matplotlib)
# 여기까지가 중간 과제 점검


## 3. 학습 데이터 구축
