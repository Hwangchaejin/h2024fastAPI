# EPL 팀 - 트위터 감정 데이터세트 프로젝트
![ddfs](https://github.com/Hwangchaejin/h2024fastAPI/assets/79899665/4734a631-49ab-4147-a7cc-d1baa0261d8b)
![images](https://github.com/Hwangchaejin/h2024fastAPI/assets/79899665/6d105cfa-022b-4610-89a2-74377b005f46)
## 잉글랜드 프리미어 리그 - 트위터 감정 데이터세트

## 1. 개요
### 1.1 EPL 정의
EPL은 영국 프리미어리그(English Premier League)의 줄임말을 뜻한다.
이 리그에는 맨체스터 유나이티드, 리버풀, 첼시, 아스널 등과 같은 유명한 축구 팀들이 속해 있다.\
EPL(English Premier League) 클럽들의 시장가치는 여러 요소에 따라 결정된다.\
일반적으로, 시장가치는 클럽의 경제적 안정성, 스폰서 계약, 방송 권리, 스타 선수들의 가치, 그리고 클럽의 역사와 팬들의 충성도 등 여러 요소에 의해 영향을 받는다.

가장 큰 클럽들은 국제적으로 매우 큰 영향력을 가지며, 그들의 시장가치는 수억 달러에 이를 수 있다.\
특히, EPL에서 매우 성과 좋은 클럽들은 고도로 상업적이고, 투자자들이 흥미를 가지는 대상이다.\
클럽이 차지하는 위치와 그들의 글로벌 브랜딩 또한 중요한 요소이다.\
![cooc](https://github.com/Hwangchaejin/h2024fastAPI/assets/79899665/17e22207-d305-4736-98f5-f46f00b233e4)
### 1.2 EPL 감정/열정 영향력
EPL의 서포터 열정은 상당히 높다. 영국 프리미어리그는 세계적으로 가장 인기 있는 축구 리그 중 하나로,\
각 팀의 팬들은 그들이 사랑하는 팀을 열정적으로 응원한다. 
경기장은 항상 활기차고 무대 인근의 팬들은 팀을 위해 모든 것을 다할 준비가 되어 있다. 
경기 전후에는 다양한 소셜 미디어 플랫폼에서 토론이 벌어지고, 승리나 패배에 대한 열정적인 의견이 공유된다.
전 세계적으로 EPL을 지지하는 팬들은 그들의 팀에 대한 애정과 열정을 넘어서서 종종 경기장에까지 여행하고 있다.\
![스크린샷 2024-05-14 103907](https://github.com/Hwangchaejin/h2024fastAPI/assets/79899665/678f2ec3-dcbb-4c36-a5d2-de11d63c55b1)
## 2. 원시 데이터
 
[EPL 팀 데이터셋](https://www.kaggle.com/datasets/wjia26/epl-teams-twitter-sentiment-dataset?select=2020-09-20+till+2020-10-13.csv "EPL 팀 데이터셋")<br>
[EPL 홈페이지](https://www.premierleague.com "EPL 홈페이지")

### 2.1 데이터 구성
+ 데이터 열 이름
  
|created_at|file_name|followers|group_name|location|text|username|
|----------|---------|---------|----------|--------|----|--------|
|최초 생성 |파일 이름|팀 팔로워 수|팀명 이름|지역|작성|선수 이름|
+ 데이터 구조 예시

|created_at|file_name|followers|group_name|location|text|username|
|----------|---------|---------|----------|--------|----|--------|
|1|206461|Valsartan|Left Ventricular Dysfunction|"It has no side effect, I take it in combinati...|9|20-May-12|27|
|2|95260|Guanfacine|ADHD|	"My son is halfway through his fourth week of ...|8|27-Apr-10|192|
|3|92703|Lybrel|Birth Control|"I used to take another oral contraceptive, wh...|5|14-Dec-09|17|
|..|...|...|.....|.....|...|...|..|
|53764|130945|Levonorgestrel|Birth Control|"I'm married, 34 years old and I have no kids. Taking..."|8|15-Nov-10|7|
|53765|47656|Tapentadol|Pain|"I was prescribed Nucynta for severe neck/shoulder pain..."|1|28-Nov-11|20|
|53766|113712|Arthrotec|Sciatica|"It works!!!"|9|13-Sep-09|46|

![image](https://github.com/Hwangchaejin/h2024fastAPI/assets/79899665/42b8cbe9-73b2-4b9a-98a1-f15dae5d2938)
데이터 전체 리뷰 수는 211,342건이 나왔다
![스크린샷 2024-05-14 105222](https://github.com/Hwangchaejin/h2024fastAPI/assets/79899665/ad851b84-e69a-4d81-92ea-62f4744d872f)


### 2-2 트위터 내 EPL 팬의 서포터즈 리뷰 수
중립을 제거한 데이터 리뷰 수는 76,735건으로 확인된다\
![image](https://github.com/Hwangchaejin/h2024fastAPI/assets/79899665/998f3cc7-360d-4e31-a01e-ceb6634ca0f4)

### 맨체스터 유나이티드 1위, 리버풀 2위, 아스날 3위로 집계되고 있다.
<hr>

## 2-3 데이터 추출
중립을 제거한 데이터의 수는 76,735건을 알 수 있다.
![image](https://github.com/Hwangchaejin/h2024fastAPI/assets/79899665/4224e619-30e9-4806-ae04-31b33f88e499)

그 중 긍정은 62,052건과 부정은 14,683건이 나왔다.
+ 긍,부정 분류\
나는 이 프로젝트에서 긍정값과 부정값을 더하여 긍정값으로 나누는 값과 
부정값과 긍정값을 더하여 부정값으로 나누는 값을 3000으로 곱해보았다.
#### 그 결과 2426이 긍정, 574가 부정으로 나왔다.
![image](https://github.com/Hwangchaejin/h2024fastAPI/assets/79899665/a853d9f5-e452-4890-ad68-c4fb68024f23)

+ 88.1퍼센트가 긍정, 11.9퍼센트가 부정으로 분석을 확인할 수 있다.



### 2.2 추출한 데이터 (반응)
대량의 데이터에서 잉글랜드 프리미어 리그의 열정 영역을 추출해볼것이다
EPL 팀 - 트위터 감정 데이터세트

### 2.3 추출한 데이터에 대한 탐색적 데이터 분석
1~5점 척도인 경우에는 분포
리뷰 문장의 길이
연도별, 장소별 등등 데이터의 부가정보를 바탕으로 데이터를 탐색하는 (pandas, matplotlib)
# 여기까지가 중간 과제 점검


## 3. 학습 데이터 구축
