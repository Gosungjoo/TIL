# 웹 스크래핑(크롤링)
## 요청/응답(HTTP)
* 요청(클라이언트)
    * 정보를 원하는 사람 (url)

* 응답(서버)
    * 정보를 주는 사람 (json,data)



## Request 파이썬 라이브러리

```
# pip 실행

pip install requests


```
# Requests 공식 문서

[https://docs.python-requests.org](https://docs.python-requests.org/en/latest/user/quickstart/#make-a-request)


# url로 요청하기

```
import requests


# 1. 주소
URL = 'https://finance.naver.com/sise/'


# 2. 요청
response_text = requests.get(URL).text
response_code = requests.get(URL)

# 3. 출력
print(response_text,response_code)

```

# 얻은 str을 beautiful Soup lib
[https://www.crummy.com/software/BeautifulSoup/bs4/doc/](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)

```
pip install beautifulsoup4
```


# api (application Programming interface)

* 컴퓨터나 컴퓨터 프로그램 사이의 연결
* 일종의 소프트웨어 인터페이스 다른 종류의 소프트웨어에 서비스 제공
* 사용하는 방법을 기술하는 문서나 표준은 api 사양/명세

## api 명세
* 정보가 있는 URL을 확인한다
* URL로 요청한다.

