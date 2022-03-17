# model

* 단일한 데이터에 대한 정보를 가짐
  * 사용자가 저장하는 데이터들의 필수적인 필드들과 동작들을 포함
* 저장된 데이터베이스의 구조(layout)
* 장고는 모델을 통해서 데이터에 접속하고 관리
* 일반적으로 각각의 모델은 하나의 데이터베이스 테이블에 매핑 됨

# Database

* 데이터베이스
  * 체계화된 데이터의 모임

* 쿼리
  * 데이터를 조회하기 위한 명령어

* 조건에 맞는 데이터를 추출하거나 조작하는 명령어
* "Query를 날린다" DB를 조작한다.

# DB의 기본구조

* 스키마(Schema)
  * 데이터베이스의 기본 구조(단위)

* 테이블
  * 열 : 필드 or 속성
  * 행 : 레코드 or 튜플


* PK(primary Key)
  * 기본키 반드시 설정해야 한다.
  * DB관리시 주요 활용


# ORM
* object-Relational-Mapping
* 객체지향 프로그래밍 언어를 사용하여 호환되지 않는 유형의 시스템 간에(Django - SQL)데이터를 변환하는 프로그래밍 기술

# ORM의 장점

* 장점
  * SQL을 잘 알지 못해도 DB 조작이 가능
  * SQL의 절차적 접근이 아닌 객체 지향적 접근으로 인한 높은 생산성
* 단점
  * ORM 만으로 완전한 서비스를 구현하기 어려운 경우가 있음
* DB를 객체로 조작하기 위해 ORM을 사용한다.



# django 설치 팁

*pip freeze > requirements.txt*
* 설치된 목록 txt 저장


*gitignore.io*
* gitignore 필수 요소 모음



# DB작성

1. articles (app)/models.py에  "class 모델 생성"
ex)
class Article(models.Model):
    title = models.CharField(max_length=10)
    content = models.TextField()
2. python manage.py makemigrations 실행
3. python manage.py showmigrations로 확인
4. python manage.py migrate 설정

# sql migrate
* 버전확인
  * python manage.py  sqlmigrate [app이름] [번호]
* 날짜 확인


# 명령어들 사용한
python manage.py shell_plus
* 콘솔에서 바로 python 명령어 실행
* django-extensions 라이브러리 중 하나

pip install ipython

```
article =Article()
#인스턴스 생성

article.title = '~~'
#인스턴스 변수 변경

article.save()
#인스턴스 저장 호출

# Classname.manager.API 형식



```


# CRUD

* creat, read, update, delete


## READ
```
#DB에 인스턴스 객체를 얻기 위한 쿼리문 날리기

Article.objects.all()

```

## CREAT


```
art = Article()
#클래스 이름으로 받기

art.title = '~~'
#클래스 내부의 속성에 저장

art.content = 'django!'
#클래스 내부의 속성에 저장

art.save()

```


```
art = Article(title="second", content="django")
# 선언과 동시에 값 저장하기

art.save()
# DB에 적용

```


```

Article.objects.create(title='third',content="django!!")
#클래스에서 바로 적용, 저장할 필요가 없음, 다만 DB관리에서 주의가 필요함

```

* 쉽게 읽는 방법

```
# 매직 매서드를 클래스이름.py에 넣어준다.
    def __str__(self):
        return self.title
```

## READ

```

Article.object.all()
# 전부 가져온다.

```


```

Article.object.get(title='first')

# title이 first인 것 '한개'만 가져옴
# 없으면 DoesNotExist 예외 발생시킴
# 2개 이상이여도 multiple ObjectReturned 예외 발생


#사용할려면?

Article.objects.get(id='2')
Article.objects.get(pk='2')

#이런식으로 unique한 value 사용


```


```

Article.objects.filter(title='first')

# title이 first인 모든 것을 가져옴

```


## UPDATE


```

#잘못된 UPDATE의 방법

art = Article.objects.get(title='second')
art.title = "ssafy"
art.save()

# 유일한 값이 맞는치 확인해야함

```
## delete

```

art = Article.objects.get(pk=3)
art.delete()



```









