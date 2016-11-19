# Data x Design, Workshop D 3기
==========

### 1. 설치
    - plot.ly: https://plot.ly/python/getting-started/
    - konlpy: http://konlpy.org/en/v0.4.4/
    - selenium: pip install selenium==2.53.6

### 2. 단계에 대한 설명
        1 원자료 수집
          - www.google.com/trends 에서 2014-04-16 부터 2016-10-31 까지 '세월호' 로 검색한 수를 받아오자.
          - 각 점의 값을 직접 입력하긴 했는데 분명히 더 나은 방법이 있을 것임.
        
        2 그래프에 나타내기
          - 사용한 라이브러리
                - pandas
                - matplotlib
                - plotly
          - pandas로 데이터를 불러오자.
          - x축은 날짜(월, 년)로, y축은 검색 건수, 그리고 점 위에 마우스를 올리면 보다 정확한 날짜와 그 날의 검색 건수가 나타나게 만들자.
        
        3 트위터 수집하기
          - 요구 사항
            - 파이어 폭스 47.0
            - Python Selenium 2.53.6
          - 사용한 파이썬 라이브러리:
                - Selenium: webdriver를 통해 파이어 폭스를 이용하기 위해 사용
                - datetime: 트윗 날짜를 저장하고, 저장하는 파일 이름을 당일 날짜로 하기 위해 사용
                - pandas: 엑셀 파일에 결과를 저장하기 위해 사용
          - 트위터의 고급 검색 기능을 이용해서 '세월호'에 대해 검색한 결과를 긁어 오자.
          - 세월호와 관련하여 구글 검색 빈도가 높아진 6일에 대해 전후 일주일에 대한 트위터 데이터만 수집하기로 하자.
                - 2014-04-16: 사건이 일어난 당일
                - 2014-10-27: 선장과 선원들이 사건에 대해 구형 받은 날
                - 2014-11-10: 정부에서 물밑 수색 작업 종료를 선언한 날
                - 2015-04-16: 청해진 해운 세월호 침몰 사고 1주기
                - 2016-01-10: 단원고 졸업식 날
                - 2016-04-16: 청해진 해운 세월호 침몰 사고 2주기
        
        4 트위터 데이터 전처리 및 워드 클라우드 그리기
          - 사용한 라이브러리
                - scipy: 워드 클라우드를 그리기 위한 이미지를 불러오기 위해 사용
                - matplotlib: 워드 클라우드를 보여주기 위해 사용
                - wordcloud: 워드 클라우드를 그리기 위해 사용
                - os: 이미지와 트위터 데이터의 경로를 지정해서 코드를 간단하게 만들기 위해 사용
                - konlpy: 한글 자연어 처리 라이브러리로 Twitter 라는 모듈을 이용해서 전처리 
          - read_data functions: 트위터 데이터를 데이터 프레임 형태로 불러오는 함수
          - get_twts functions: 불러온 트위터 데이터를 전처리해서 워드 클라우드에 사용할 수 있는 문자열 형태로 바꿔주는 함수
          - draw_wc functions: 위의 두 함수를 사용해 워드 클라우드를 그리고 그 결과를 .png 파일로 저장하는 함수

### 1. Installation
    - plot.ly: https://plot.ly/python/getting-started/
    - konlpy: http://konlpy.org/en/v0.4.4/
    - selenium: pip install selenium==2.53.6
    
### 2. Explaination about procedures
        1 Getting raw data
          - Go to www.google.com/trends and search for 'Sewol(in Korean)' from 2014-04-09 until 2016-10-30
          - I manually entered all dates and according values, but there must be some easier way to do so.
                  
        2 Plotting on a graph
          - Libraries ued
                - pandas: getting the data from a raw file(spreadsheet)
                - matplotlib: import dates module from matplotlib library(import matplotlib.dates as mdates)
                - plotly: import plotly, graph_objs from plotly library to draw an interactive graph which shows you 
                    the number of search frequency on a specific day. 
          - Read the data in using pandas
          - X_axis will be represented as Month Year, Y_aixs is the number of search result on Google,
            and you will see the exact day and the value when you hover over the graph.
          
        3 Getting tweets
          - Requirements:
                - Firefox 47.0
                - Selenium 2.53.0
          - Libraries used:
                - Selenium: to run webdriver
                - datetime: to change the format of dates and make file name
                - pandas: to write gethered result on Excel files
          - Crawl the tweets about 'Sewol Ferry' using advanced search result on Twitter.
          - We picked a few particular days and looked up some tweets before and after 7 days around the specific dates.
                - 2014-04-16: The day that the accident happened.
                - 2014-10-27: Procecutors accused the captain and vessel crews for the accident.
                - 2014-11-10: The government announced to cease under water search.
                - 2015-04-16: The first anniversary of Sewol Ferry accident.
                - 2016-01-10: The graduation day at Danwon Highschool.
                - 2016-04-16: The second anniversary of Sewol Ferry accident.
        
        4 Processing Tweets
          - Libraries used
                - scipy: to read images for word clouds
                - matplotlib: to show word clouds
                - wordcloud: to make word clouds
                - os: to make a loop to run through all files as a loop
                - konlpy: a library for Korean Natural Language Proocess, Twitter() is used as a parser
                - random: to generate grey colors for the words in word clouds
          - read_data functions: read tweets into data frames
          - get_twts functions: get tweets from data frames and process them so they can be used for word clouds
          - draw_wc functions: draw word clouds and save them as .png file

### 3. What are those Jupyter Notebook files for?

       1 Changes on Google Trends about Sewol Ferry using Plotly.ipynb
         - For a graph on Google Trends
       2  Tweet Crawler.ipynb
         - To gether tweets from twitter
       3 Word Cloud 
         - All the work pretty much happen here from reading data to drawing word clouds.
 
