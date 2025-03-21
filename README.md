# EDA 프로젝트 5조 : 로봇 취업시장의 미래 (Team Vector)

## Introduction

### 주제
| 주제 | 앞으로 로봇 시장에 취업하기 위해서 어떤 역량이 필요할까? |
|:---|:---|
| 배경 | 로봇공학은 자동화, 인공지능, 스마트 기술의 발달과 함께 주목받는 분야 중 하나입니다. 다양한 산업에서 로봇 기술의 적용이 점차 증가하고 있어, 해당 분야의 취업 시장도 빠르게 성장하고 있습니다. 이러한 시장에서 경쟁력을 갖추기 위해, 필요한 역량을 이해하고 준비하는 것이 중요하기 때문에 로봇 취업 시장에 필요 역량을 조사하고 분석하여 저희와 같은 관련 분야 취업자에게 도움을 주고자 프로젝트를 시작하게 되었습니다. |


### 기술 스택
|분류|기술|
|---|---|
|개발환경|<img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=white"/> <img src="https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=Ubuntu&logoColor=white"/>|
|언어|<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=Python&logoColor=white"/> <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=Pandas&logoColor=white"/>|
|웹스크롤링|<img src="https://img.Shields.io/badge/selenium-43B02A?style=for-the-badge&logo=selenium&logoColor=white"/>|
|데이터베이스|<img src="https://img.shields.io/badge/MYSQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white"/>|
|협업 툴|<img src="https://img.shields.io/badge/confluence-172B4D?style=for-the-badge&logo=confluence&logoColor=white"/> <img src="https://img.shields.io/badge/jira-0052CC?style=for-the-badge&logo=jira&logoColor=white"/> <img src="https://img.shields.io/badge/slack-4A154B?style=for-the-badge&logo=slack&logoColor=white"/> |


# Responsibility
||이름|역할|
|:---:|:---:|---|
|팀장|윤민섭| **데이터 분석**, KOSIS 통계자료 수집 및 시각화, 스펙 입력시 기업 추천 및 시각화, 발표자료 준비 |
|팀원|최희재| **사람인 공고 웹크롤링**, DB 구축, 관리, 및 Query 작성, 기술 키워드 사전 제작 및 키워드 - 공고 간 비교 작업 |
|팀원|김완섭| **KOSIS 통계자료 수집 및 시각화**, 발표자료 서포트  |
|팀원|조성현| **JobKorea 공고 웹크롤링**, 데이터 분석 |


# Data collection

## 1.1 채용 공고 사이트에서 데이터 크롤링
| | Data |
|---|---|
|수집 사이트|사람인, 잡코리아|
|수집 데이터|기업 정보 - 기업명, 기업 형태, 사원수, 설립일, 2021, 2022, 2023년 매출|
|취업 공고 정보|공고명, 공고 내용, 게시일|


## 1.2 크롤링한 데이터 AWS 데이터베이스에 저장
![image](https://github.com/user-attachments/assets/3a212ef9-87ab-4e8d-911b-130b404ab6bc)
* 기업-기술 및 공고문-기술 간의 연관성을 효율적으로 조회할 수 있도록 조인 테이블을 활용해 데이터베이스 설계
* 크롤링한 데이터를 실시간으로 데이터베이스에 저장하도록 구현

## 1.3 기술 키워드 수집
### 사람인에서 제공하는 직무 키워드 목록을 기반으로 기술 테이블의 기본 <br> 구조를 구성
![image](https://github.com/user-attachments/assets/de850e7b-7e87-45e6-a004-c2e8558fa3cf)
### 동의어 정리
![image](https://github.com/user-attachments/assets/fe7282ce-0947-41f6-9bf3-678792b998e0)

# Exploratory Data Analysis (EDA)
* ## 2-1. 전체 공고문에서 가장 많이 언급된 키워드는 <br> 무엇일까?
* ## 2-2. 기업형태별로 어떤 역량을 요구할까?
* ## 2-3. 어느 업종이 유망할까?
* ## 2-4. 내 역량을 많이 언급한 기업을 알아보자.
  ---

## 2-1. 전체 공고문에서 가장 많이 언급된 키워드는 무엇일까?
![image](https://github.com/user-attachments/assets/1d935a19-d780-4446-a234-f98d1d0fc230)

* ###  여기서 잠깐! 'C언어'가 가장 높게 집계된 이유
 대부분의 공고문에서 'C/C++' 'C, C++'처럼 표기해놓기 때문입니다.
![image](https://github.com/user-attachments/assets/2439e063-0ff6-493f-a32b-1c210acf7d9d)

## 2-2. 기업형태별로 어떤 역량을 요구할까?
중소기업, 중견기업, 대기업 별로 무슨 역량이 중요하게 여겨지는지 분석 해보았습니다.  
중소기업은 수가 많은 관계로 그 안에서 연봉으로 세분화 하였습니다.  
* ###  1. 중소기업(~4천만원)
![image](https://github.com/user-attachments/assets/4ca3cec4-2cf6-4c9f-b0fc-eeaf46898ae7)
* ###  2. 중소기업(4~7천만원)
![image](https://github.com/user-attachments/assets/12aa70c4-b1c4-47e3-900a-1b31f4b898b5)
* ###  3. 중소기업(7~9천만원)
![image](https://github.com/user-attachments/assets/989c6d50-f729-4a59-a72b-0943ab10ef5b)
* ###  4. 중견기업
![image](https://github.com/user-attachments/assets/fea96d91-679d-48c9-bb3e-73ab656c284b)
* ###  5. 대기업
![image](https://github.com/user-attachments/assets/eea92178-825a-455a-8416-f9e53d1979ec)

### **분석 결과**
#### 고연봉 대기업에서 파이썬보다 C / C++의 수요가 높습니다.

1. 중소기업 (평균연봉 7천 이하) : C++, C, Python에 대한 평균연봉은 큰 차이가 없습니다.

2. 중견기업, 중소기업 (평균연봉 7~9천이하) : C#, C++, C 언어에 대한 평균연봉이 일정수준 상승함을 
확인할 수 있습니다.
 
3. 대기업 : C++, C 언어에 대한 평균연봉이 Python, SQL에 비해 월등히 높음을 확인할 수 있습니다.

**로봇 현업에 종사하면서 자신의 연봉을 꾸준히 올리고 싶다면 C++, C가 필수입니다.**
  
## 5-3. 어느 업종이 유망할까?
![image](https://github.com/user-attachments/assets/48cb9e8c-ec49-42ea-b546-ebd26cbea9af)
21~23년도 업종별 매출액을 기준으로 '매출액 상승폭'과 '매출액 평균'을 구하여 가장 높은 수치를 기록한 다섯 개의 업종을 조회했습니다.  
'기타 엔지니어링 서비스업'이 '매출액 상승폭'과 '매출액 평균'에서 모두 높은 수치를 기록하였으며,  
이는 최근 수요의 증가, 성장 가능성, 그리고 안정성이 다른 업종에 비해 상대적으로 크다는 것을 의미합니다.  
'기타 엔지니어링 서비스업'에 포함되는 주요 키워드는 '자동화'입니다.  
따라서 '자동화'와 관련된 업종이 유망할 것으로 보입니다.

## 5-4. 내 역량을 많이 언급한 기업을 알아보자.
![image](https://github.com/user-attachments/assets/97c15da2-d078-4b78-a0ee-9f015f77ff8a)

![image](https://github.com/user-attachments/assets/ebbaf156-d155-4b15-863e-d6497735e9a4)
제 역량인 'C, C++, Python, MySQL'을 가장 많이 언급한 회사는 위와 같습니다.


# Project Schedule
![jira_1](https://github.com/user-attachments/assets/893c888b-2bb1-4d3c-a468-eaa27d1755e6)
* Jira를 활용하여 각자 개인이 맡은 작업 일정을 확인하고, 수정 사항 또한 실시간으로 확인하여 유연한 팀프로젝트를 진행하였습니다.

* 프로젝트 스케줄은 크게 "주제 선정", "데이터 조사", "데이터 수집 및 관리", "데이터 분석 및 시각화", "발표 자료 작성"으로 구성하였으며, 앞서 끝나야지만 다음 작업이 가능한 부분까지 스케줄을 점검하여 프로젝트의 속도를 붙이게끔 스케줄을 작성하였습니다.


# Review

| |이름|소감|
|:----:|:----:|---|
|팀장|윤민섭| 팀장으로서 부담이 있었지만 팀원들의 확실한 보조로 끝까지 잘 마무리 <br> 할 수 있었습니다.|
|팀원|최희재| 구체적인 목표 설정, 문서 작성의 중요성을 느꼈습니다. <br> 각자 잘하는 부분에 집중할 수 있다는 점에서 협업의 장점을 <br> 느꼈습니다.|
|팀원|김완섭| 비전공자로써 두려움과 걱정이 앞섰지만, 팀원들과 협업하여 결과물을 <br> 만들어 내니, 협업의 중요함과 성취감을 느꼈습니다. |
|팀원|조성현| 프로젝트 초반에는 협업보다는 각자 개인의 역량이 중요하다고 <br> 생각했지만, 팀원들과 소통하면서 step by step으로 프로젝트를 <br> 진행하면서 어떤 프로젝트도 개인 혼자서 다 만들 수 없다는 것을 팀원간의 협업을 통해 깨달았습니다. |

