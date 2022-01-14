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


## init 설정을 해제하기
삭제시
```
rm -rf .git
```
```
-r 하위 디렉토리
-f 숨김 폴더까지
```
<br><br>

---

# *GIT 사용 흐름 정리*
1. *해당 폴더로 이동한다.*
    ```
    cd //(작업 디렉토리)
    ```
2. *git init을 통해 Local Repo에 등록한다.*

    ```
    git init
    ```
3. *git add . 을 통해 Stage Area에 등록한다*
    ```
    cd //(내가 원하는 디렉토리)
    git init
    git add .
    ```
4. *git commit 을 통해 Stage Area에 있는 파일을 Local Repo에 등록한다.*
    ```
    git commit -m "메모 남길 내용"
    ```

5. *git push 하면 연결된 Remote Repo에 Push한다.*
    ```
    git push
    ```

6. *Remote Repo(@github.com)에서 결과를 확인한다.*
    






# *Git Book 교안*
 https://git-scm.com/book/ko/v2/



 ---
# **Python**

<br><br>

## 1. **문자열 하나 입력 받기**

```
st = input()
print(a)
```
<br><br>


## 2. **문자열을 나누는 법**
*split() 함수는 내부 인자로 ',' 등의 string을 가진다.*<br>
*ex) split(',') 이면 "1, 2" 가 각각 1  2로 나뉘어 저장된다.*
```
st1, st2 = st.split()
```

<br><br>

## 3. **문자열 형변환**
```
문제
 1 5 2 입력
 세 숫자의 합 출력
```
 *split으로 나눈것은 스트링이므로*<br>
 *정수로 바꿔주어야한다.*<br>
 *+) 숫자를 스트링으로 바꾸는법   str(a)* <br>
```
st = input()
a, b, c = input.split()

a= int(a)
b= int(b)
c= int(c)

print(a+b+c)
```

<br><br>

## 4. **공백 제거**
*strip([chars]) : 인자로 전달된 문자를 String의 왼쪽과 오른쪽에서 제거합니다.*
```

st = '             i am a good boy       '
st = st.strip()
```

<br><br>

## 5. **문자열 포맷팅**
### *다양한 방법의 포맷*

```
a = '철수'
b = '영희'

print( a , 'likes' ,b)
# '철수 likes 영희'

st1 = a + ' likes '+b
st2 = '%s likes %s' % (a,b)
st3 = "{} likes {}".format(a,b)
st4 = f"{a} likes {b}"

```
<br><br>

## 6. **스트링의 연산**
*스트링의 배열 스트링의 사칙연산은 적용된다.*<br><br>
*ex) list1 + list 2는 ['고양이' ,'토끼','호랑이','강아지']*
*곱은 이와 똑같은 방향으로 진행된다.*<br><br>
*list1 * 3  ['호랑이','강아지','호랑이','강아지''호랑이','강아지','호랑이','강아지']*

```
list1 = ['고양이' ,'토끼']
list2 = ['호랑이','강아지']

print(list1[0])
pirnt(list1+list2)
print(list1*3)

```
<br><br>

## 7. **list에 원소 추가**
 *list1은 ['고양이','토끼'] 를 가진다.*

```
list1 = ['고양이']
list1.append('토끼')
```


 *실습 문자열 하나 입력받고 list2 에 append*<br><br>
 *append함수는 인자로 list 원소 형태의 데이터 삽입 할 수 있다.*<br><br>
 *[1,2,3,4] 정수형 list -> append(정수)*<br><br>


```
a = input()

list2 = []
list2.append(a)


```
<br><br>

## 8. **리스트 인덱스**
 *list[정수]하면 0,1,2 .. 부터 시작하는 순서에서 2번째의 값을 출력한다.*<br><br>
 *list[음수]이면 오른쪽 끝에서부터 -1 -2 순서로 index한다. <br><br>범위를 넘는 경우 무조건 에러가 나므로 주의*

```
list[1]  # 왼쪽 두번째 값 
list[-1] # 오른쪽에서 첫번째 값

```
<br><br>


## 9. **리스트 슬라이싱**
 *list[::정수]*<br><br>
 *예제는 리스트를 역순으로 정렬*
```
list[::-1]
```


## 10. **String에 공백(서식) 추가/정렬**
<br>
*여러가지 경우가 있다.*<br>
*서식지정자부터 알아보자*<br><br>

### 1. **서식 지정자(우측 정렬)**
```
'%10s' % 'python'
```
*(오른쪽 정렬)결과는 총 10칸을 두고 출력한다.*
```
'    python'
```
<br><br>

### 2. **서식 지정자(좌측 정렬)**
```
'%-10s' % 'python'
```
*(왼쪽 정렬) 결과는 총 10칸이지만 문자열이 왼쪽이다.*
```
'python    '
```

### 3. **format (좌측, 우측 정렬)**
*간단하게 사용 할 수 있다. 가운데에 부등호가 방향을 결정한다.*
```
'{0:<10}'.format('python')
'{0:>10}'.format('python')
```
*결과는?*
```
'python    '
'    python'
```

