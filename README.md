# CLI-development
## 1. 개요

- 목표: Use news counting and portal trends(google,naver,kakao) data to develope new Composite Leading Indicator(경기선행지수) 
뉴스기사수와 포털 트렌드의 주간 데이터들을 수집하여, 월간 경제 지표인 소비자심리지수를 예측하여 새로운 주간 경제 지표를 개발한다. 

- 데이터: 
  - 부정적 경제 상황 키워드를 포함하는 뉴스 기사 수
  : 빅카인즈에서 json 파일 다운로드
  - 포털 트렌드의 '경제' 검색량 비율
    - 구글: 구글 트렌드에서 csv 파일 다운로드
    - 네이버: 네이버 데이터랩 openAPI 활용
    - 카카오: 카카오 트렌드에서 excel 파일 다운로드
  - 소비자심리지수(CCSI), 경기동행지수(CCI) 순환변동치
  : 한국은행 경제통계시스템 API 활용

## 2. 예측 모델 소개

y(주간 데이터 레코드로 CCSI를 예측한 값), yhat(월말에 제공되는 CCSI)
: 해당 월의 주차들 레코드들의 평균값들을 데이터셋으로 활용

- multiple linear regression
- regression decision tree
- random forest

## 3. 개발 환경
1) 개발 환경
- WSL Ubuntu-18.04 ver2.
2) 개발 언어
- Python 
3) 라이브러리
- pandas 1.0.5
- pymysql 0.9.2
- urlib3 1.25.9
- BeautifulSoup 4.9.1
- matplotlib 3.2.2

## 4. 코드 실행 및 결과 재현 방법

1. 데이터셋 준비(save to db table)
```
python get-data.py
```
[get-data.py](https://github.com/2hyes/CLI-development/blob/master/get-data.py)에 네이버데이터랩 API client id, pw / 한국은행 openAPI api key / 저장할 database의 id, pw, db를 입력하면, 필요한 데이터셋이 모두 데이터베이스에 저장된다.

2. 예측
진행중
