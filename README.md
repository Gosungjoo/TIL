# TIL
##  git 구조 4단계<br>
* RemoteRepo.<br>
* LocalRepo.<br>
* Staging Area (commit 대기실)<br>
* 작업 폴더
<br><br>


##  단계 별 정리
1. 작업파일 변화/생성/수정
2. 변화가 있으면 감지(auto) [추적]
3. 추적된 파일을 Staging Area에 올린다. [add]
4. Commit을 통해 Local 에 올린다.
5. Push를 통해 Remote 에 올린다.
<br><br>

---

## ignore
* ignore 파일 생성 (.gitignore)<br>
<br>

### 해당 파일 양식

<br>
* 해당 폴더의 파일 이름을 확장자까지 작성

> abc.txt


<br><br>
* *을 삽입하게 되면 그 이후 단어는 전부 포함

> abc1.txt abc2.txt ....<br>
> abc*


<br><br>
* 폴더는 /를 통해서 구분
> cache/<br>
> cache/*<br>


<br><br>
---

## 인증 Factor

* Single Factor 인증
    * 1개로 인증한다.

    > Password

<br>

* Two Factor 인증
    * 2개로 인증한다.

    > Password , 휴대폰

<br>

* Multi Factor 인증
    * 2가지 이상의 여러개로 인증한다.
    >  id , 지문, 홍채..<br>

    <br><br>


 이런 Facotr 중 Keyfile은 Git에 올리면 안된다.

---
 ## 리눅스
 *  운영체제 중 하나

SW는 System / App 계열로 나뉜다

System Software 중  유닉스 계열이다. 
>리눅스 / 안드로이드 / 타이젠...<br>

---
<br>
<br>

## 운영체제의 커널
* 운영체제는 소스코드로 만들어진 하나의 프로그램<br>
* 소스코드 중에서 핵심을 **커널 코드**라고 함 

> 메모장 , 그림판은 커널코드가 아니다


> CPU, 모니터 등 장치관리 프로그램은 커널코드이다.

리눅스 배포판
* 리눅스 배포판&nbsp; = "커널" + 쉘 *(다음장에 설명)* + 기타 S/W
> Android / 우분투
---
## 서버

* A, B, C 컴퓨터가 있다고 하자
* A에서 컴퓨터에 팀과제 파일이 있다고 하면
* B, C 에서 접속해서 과제를 수정한다.


> A 의 컴퓨터의 연결이 끊긴다면?

* 해결방법은?
    * 24시간 켜져있는 컴퓨터를 만든다.
    * 그 서버에 파일을 저장해서 작업을 한다.
    * 모두가 언제나 접속 할 수 있다.
    > 24시간 켜져있는 컴퓨터는 서버 이다.


---
## Shell(쉘)

* 쉘 인터페이스
유저들이 운영체제의 기능을 사용하게 해주는 리모컨 같은 것.
    * GUI
        > 화면, 마우스 등을 이용하여 사용
        
        쉽게 사용 할 수 있다.
    * CLI
        > 커맨드 라인만을 이용하여 사용

        왜 쓰죠?

    * CLI를 사용하는 이유
        > 여러개 설치/관리시 불편하다.

            프로그램 10개를 GUI에서 설치한다면?
            
            GUI > 설치 ..클릭 ..설치 클릭....
                  설치 ..클릭 ..설치 클릭....
                  설치 ..클릭 ..설치 클릭....
                  설치 ..클릭 ..설치 클릭....
                  설치 ..클릭 ..설치 클릭....
                  ..
                  ..
                  ..

            CLI > pip install - ...

        > *(중요) 멋있어 보인다* 


---
<br>
<br>

#  Unix CLI 명령어
### *remind*
* git
* github
* github desktop

## Bash
```
 현재 디렉토리 폴더 확인

* ls

```
```
 폴더 이동 

* cd [폴더명]
* cd 경로/경로/경로/[폴더명]

```
```
 상위 폴더 이동

* cd ..

```
```
확장자 만들기

* touch [파일이름.확장자]
* touch 폴더/폴더 .../[파일이름.확장자]
```
```
폴더만들기

* mkdir [폴더이름]
* mkdir 경로/경로.../[폴더이름]
```
```
rm -r[파일 or 디렉토리]

 파일지우기
   -r옵션은 하위 디렉토리를 포함하여 삭제한다.
```

## bash Tip

<br> <br>
```
경로(path) 표시는 윈도우에서는   \(역슬래쉬)   이지만
Unix 기반에서는   /(슬래쉬)   이다.
```
- Unix
> folder/aaa.txt
- Window
> floder\aaa.txt
<br> 

```
화살표 위 키를 누르면 이전에 쓴 명령어가 자동입력된다.
```
1. 명령어 입력한다.
> &nbsp;<br>
> user touch aaa.txt*현재라인*
> &nbsp;<br>
2. 빈 라인이 생긴다
> &nbsp;<br>
> user touch aaa.txt <br>
> *실행결과*<br>
> &nbsp;<br>
> user  *현재라인* <br>
3. 화살표 위키를 누른다.
> &nbsp;<br>
> user touch aaa.txt <br>
> *실행결과*<br>
> &nbsp;<br>
> user touch aaa.txt *현재라인* <br>

<br> <br>

```

Tap 키를 누르면 디렉토리나 폴더 이름 자동완성 된다.

```
> user cd a <br>

탭을 누른다.

> user cd aaa.txt <br>


---
