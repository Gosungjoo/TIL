# TIL

## Git bash 사용법

* 로컬에 정보 저장하기

```
git config --global user.name "내 이름"

git config --global user.email "내 메일"

git config --global --list

```

<br>

* *숨김파일 ( 참고 )*<br>

    *형식*
    ```
    .filename
    ```

    *예제 ( 숨김파일(.test) 만들기 )*
    ``` 
    touch .test 

    ```

    *숨김파일까지 확인하는 명령어*

    ```

    ls -a

    ```



<br><br><br>

* 현재 디렉토리 Local Repo로 만들기
```

git init

```

* 코드 에디터 실행하기
```

code .

```
<br><br>

---

<br><br>
* Local Repo에 commit 하기
    * *작업 repo를 등록하는 두 가지 방법*<br><br>
        *1. work 작업 폴더 만들고 만든 작업 폴더를 등록하기*

        *2. Clone 하면 Local Repo에 작업 폴더가 자동생성*
<br><br><br><br>

---



## **Staging Area에 등록하기 (Add)**

```
git add .
```


* Staging Area 확인하기

```

git status

```

     git status?

    새로 만든 파일일 경우 한 번만 해주면 된다.


## **커밋 하기 (Commit)**
```

git commit -m "메모 남길 내용"

```



## **클론 하기 (Clone)**



   1. *클론 할 주소를 **github** 에서 얻는다.*


   ```
   (클립보드)https://github.com/Gosungjoo/public-7-.git
    
   ```


   2. *작업 디렉토리를 준비하고 이동한다.*
   ```
    
   mkdir work2

   cd work2

   ```


   3. *git Clone 작성*
   ```
   git clone https://github.com/Gosungjoo/public-7-.git

   ```


<br><br>

---

<br><br>
* Remote repo 설정 보기
```
git remote -v
```

<br><br>


## **푸쉬(Push)**

```
git push

```

<br><br>

---


## Git 파일의 상태


* Untracked
    * git이 관리하지 않는 파일.

* Tracked
    * git이 관리하는 파일



* Unmodified
    * 최신 상태

* Modified
    *  수정되었지만 아직 Staging Area에는 반영하지 않은 상태
* Staged
    * Staging Area에 올라간 상태
<br><br>

# Git Book 교안
 https://git-scm.com/book/ko/v2/