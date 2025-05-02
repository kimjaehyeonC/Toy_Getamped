# Intro & Goal📌

프로젝트의 목표는 겟앰프드 데이터를 활용해 자유롭게 원하는 분석을 수행하며 기간은 정해져 있지 않음

지금 까지 했던 작업 목록
1. 겟앰프드 유저 수 증가 원인 파악
2. 겟앰프드 유저의 선호 액세서리 유형 분석
3. 액세서리 추천 로직 작성
4. 로그 데이터 활용 분석 및 인사이트 도출  

# Data Collection📌
  
데이터는 직접 인 게임에서 대전도감 데이터를 수집하였고 겟앰프드 홈페이지의 액세서리 배너에 있는 데이터를 스크래핑하여 활용  
  
[데이터 스크래핑 코드](https://github.com/kimjaehyeonC/Getamped/blob/main/getamped_scraping.ipynb)
  
# Data Preprocessing & Analysis📌
  
[전처리 및 시각화 분석 코드](https://github.com/kimjaehyeonC/Getamped/blob/main/getamped_anlysis.ipynb)
  
< Preprocessing >  
  
- 계급을 숫자로 labeling하였고 계급별로 유저를 select할 수 있도록 함수를 작성
- 액세서리 평점 데이터를 수집한 유저 데이터와 Join하여 data set을 구성
  
< Analysis >  
  
- 유저별 사용 액세서리들의 평균 평점을 Radar chart로 시각화하여 각 계급군별 성향도를 파악
- 그 외 계급군별로 주로 사용한 액세서리의 빈도를 Bar chart로 시각화하여 선호 액세서리를 파악
  
# Recommendation Logic📌
  
[추천 시스템 로직 작성 코드](https://github.com/kimjaehyeonC/Getamped/blob/main/getampled_recommendation.ipynb)
  
- Content-based Filtering idea를 활용하여 유저가 사용한 액세서리와 유사한 평점을 갖는 액세서리를 추천하는 로직을 작성
- User-based Collaborative Filtering idea를 활용하여 추천받을 유저와 유사한 평점 성향을 갖는 유저를 추려내어 그들이 사용했던 액세서리를 추천하는 로직을 작성
- 두 모델을 비교하기 위해 선택, 적용할 수 있도록 함수를 작성했습니다. 이때, 유저가 이미 사용했던 액세서리를 추천하지 않도록 추가 로직을 작성
- 평가 Metric으로 MSE를 선정하여 sample user data를 통해 평가를 진행했습니다. 수치상의 결과는 Content-based Filtering이 더 좋음
- 기타 실험으로 Apriori 알고리즘을 활용하여 어떤 액세서리를 활용했을 때 같이 자주 사용하는 액세서리 도출을 시도
  
# Making Log data & Analysis📌

- 가상의 로그 데이터를 생성 및 활용하여 유저의 액세서리 선택 성향이 어떤지 파악
- 이를 통해 액세서리 기획시 고려해야 할 인사이트를 도출
