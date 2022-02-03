# Web


## Django
* 데이터를 조작하는 부분 (back)

## Vue
* 데이터를 보여주는 부분 (front)

## front?
* CSS
* HTML

## HTML
* 현재의 웹 표준
* 참조(하이퍼링크)를 통해 사용자가 한 문서에서 다른 문서로 즉시 접근할 수 있는 텍스트


# HTML
## HTML 기본구조
* HTML 
  * 문서의 최상위 요소


* head
  * 문서의 메타데이터 요소
  * meta?
    * 문서 제목, 인코딩,스타일...
    * 일반적으로 브라우저에 나타나지 않는 내용


* body
  * 문서 본문 요소
  * 실제 화면 구성과 관련된 내용


## HTML 기본 문법
* 속성 
  * 쌍따옴표 사용 권장, = 전후로 공백X
  * 속성명과 값이 하나의 세트
  * 태그와 상관


```
<a href="https://google.com"></a>
```

* 시멘틱 태그

  * 논 시맨틱 요소는 div,span 이 있다.
  * 의미를 가지는 태그를 통해 나눌 수 있다.
* 인라인 요소
  * span , a 같은 인라인 요소는 감쌀 수 있다.
  * 내용물의 크기만큼만 크기를 가져간다.
```

<h1 title="h1태그!!!">나의 첫번째 HTML</h1>
<h1>나의 두번째 HTML</h1>
<p tabindex="1">이것은 본문입니다.</p>
<span>이것은 인라인 요소</span>
<a href="https://www.naver.com">네이버로 이동!!</a>
<p tabindex="2">이것은 본문입니다.2</p>
<a href="https://www.naver.com" tabindex="-1">네이버로 이동!!2</a>


```

* table
  * th 테이블 헤드
  * tr 테이블 로우
  * td 테이블 데이터
  * colspan, rowspan 속성을 이용하여 셀 병합



* form
  * 서버/클라이언트
    * 요청과 응답으로 이루어진 Web 구성요소
  * action
    * form을 처리할 서버의 URL
  * method
    * form을 제출할 때 사용할 HTTP 메서드 (get, post)
```
#예시) 아이유

https://www.google.com/search?q=%EC%95%84%EC%9D%B4%EC%9C%A0&rlz=1C1CHZN_koKR985KR985&oq=%EC%95%84%EC%9D%B4%EC%9C%A0&aqs=chrome.0.0i355i512j46i512j0i512l5j46i512j0i512l2.1162j0j4&sourceid=chrome&ie=UTF-8


# ?뒤에 method 에서 q= 뒤의 값은 아이유이다.
%EC%95%84%EC%9D%B4%EC%9C%A0 = 아이유

# q == get

```

<br><br><br>
* input(tag)
  * 입력을 받음 보통 form과 같이 들어감
  * enter == 요청

* input label
  * label을 클릭하여 input 자체의 초점을 맞추거나 활성화 시킬 수 있음

## - 여러가지 html을 해보자..
<br><br><br>

# CSS (Cascading Style Sheets)
 *계단식 스타일 시트*

## 내부참조 / 인라인 / 외부참조

* 인라인
    * 해당 태그에 직접 style 속성을 활용

```

<h1 style="color: blue; font-size: 100px;">Hello</h1>

```

* 내부 참조
    * head 태그 내에 style
    에 지정


```

<head>
.
.
.
  <style>
    h1{
      color: blue;
      font-size: 100px;
    }
  </style>
</head>

```

* 외부참조
  * 외부 css파일을 통해 참조




## CSS 선택자
* CSS에서 어떤 부분을 선택하느냐
```
    /* 전체 선택자 *(모든사람은) */
    * {
      color: red;
      
      font-size: 24px;
      
      margin: 0;
      /*CSS RESET */
    }



    /* 요소선택자 */
    h2{
      color: orange;
    }



    /* 클래스 선택자 */
    .green {
      color: green;
    }




    /* id 속성은 unique -> id 선택자(이름) */
    #purple{
      color: purple;
    }






    /* 선택자 및 결합자를 통해서 더욱 정밀한 작업가능 */


    /* 자식 선택자 */
    /* 바로 밑에 있는 것 중 p 태그(자식만) */

    .box > p {
      font-size: 30px;
    }





    /* 자손 선택자 */
    /* 본인이 포함한 모든 것들 중 p 태그 */

    .box p{
      color: blue;
    }


```


<br><br>

## CSS 상속
* 자식 자손 등에서 어떤 공유하는 부분

```
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    p {
      /* 상속됨 */
      color: red; 
      /* 상속 안됨 */
      border: 1px solid black;
    }

    span {
      /* border: 1px solid blue; */
    }
  </style>
</head>
<body>
  <p>안녕하세요 <span>김싸피</span> 입니다.</p>
</body>
</html>
```
## 크기

```
  <style>
    .fontsize {
      font-size: 30px;
    }
    .em {
      font-size: 1.5em;
    }

    .rem {
      font-size: 1.5rem;
    }
  </style>
```

* .em
  * 부모의 크기에 따라서 설정됨 
  
  * [x]em : 부모 글씨 싸이즈의 [x]배수

* .rem
  * 부모의 크기가 아닌 html문서의 기본 사이즈에 따라서 설정됨


  * [x]rem : html 문서 글씨 사이즈의 [x] 배수



<br><br><br><br>
<br><br><br><br>

# CSS Box Model

## 모든 요소는 네모 박스이고 위에서 아래로, 왼쪽에서 오른쪽으로 쌓인다.

* *inline direction*
* *block direction*

<br><br>

# Box model의 구성

### *1. Margin*
  * 테두리의 바깥의 외부 여백
  * 다른 요소와의 거리(여백)를 조정

### *2. Border*
  * 테두리 영역


### *3. padding*
  * 테두리 안쪽의 내부 여백, 요소의 배경색, 이미지는 padding 까지 적용된다.
  * 내부의 요소의 여백를 조절 할 때

### *4. Content*
  * 글이나 이미지등 요소의 실제 내용

<br><br><br><br>

## 예시


```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <Style>
    .box1{
      width: 500px;
      border-width: 2px;
      border-style: dashed;
      border-color: red;
      padding: 50px;
      margin: 0 auto;

    }
    .box2{
      width: 500px;
      border: 2px solid black;
      padding:  20px 30px;
      margin: 0 auto; 
      /* auto 가운데 정렬 */
    }
    

  </Style>

</head>
<body>
  <div class="box1">첫번째</div>
  <div class="box2">두번쨰</div>
</body>
</html>
```


## box-sizing
* *기본적으로 요소의 box-sizing은 content-box*
* *일반적으로 영역을 볼 때는 border-box로 설정 (테두리 까지 포함)*

* ## border-box가 권장된다.
```

      box-sizing: border-box;
      box-sizing: content-box;

```

## box 설정
```

 <style>
    div {
      width: 100px;
      height: 100px;
      border: 2px solid black;
      background-color: crimson;
    }

    .none {
      display: none;
    }

    .hidden {
      visibility: hidden;
    }
  </style>

```
*none의 경우 아예 화면상에 나오지 않는다. 공간차지 X*
*hidden은 공간을 차지하지만 화면에 표시되지 않는다.*


# CSS Position

## 문서 상에서 요소의 위치를 지정
* static : 모든 태그의 기본 값(기준 위치)
[https://developer.mozilla.org/ko/docs/Web/CSS/position](https://developer.mozilla.org/ko/docs/Web/CSS/position)

* relative : 상대 위치
  * 자신의 static 위치를 기준으로 이동
* absolute : 절대 위치
  * 자기 부모/조상 기준, 없는 경우 body
* fixed : 고정위치
  * 요소를 문서 흐름에서 제거 후 특정 레이아웃에서 고정

```
<!-- 기본 -->

position: static;



<!-- 기본위치 기준으로 상대위치 -->
position: relative;
top: 40px; left: 40px;


<!-- 부모 기준 없으면 body 기준  -->
position: absolute;
top: 40px; left: 40px;


<!-- 스크롤에서 보일 때는 static에 있는데 안보이면 고정 위치 -->
position: -webkit-sticky;
position: sticky;
top: 20px;

```