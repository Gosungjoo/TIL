# css
## media query
* css를 위한 언어
* 반응형 css를 위한 중요한 요소
<br><br>
---
<br><br>

# 기본 문법
* css에 작성

```
@media type ( conditional ){
  css1 ..;
  css2 ..;
  css3 ..;
}

```

```
@media only print (){
  * {
    color:black;
  }

}
```

* 제일 많이 쓰는 경우
```
@media (min-width: 500px){

}
@media (max-height: 500px){

}

```

* and , or 연산도 지원한다.
```

@media (min-width: 500px), (min-height: 500px){
<!-- or -->
}



@media (min-width: 500px) and (min-height: 500px){
<!-- and -->
}
```

<br><br>
---
<br><br>

# 이미지 생성
## Favicon 생성기
[favicon.io](https://favicon.io)

# 모달
### #id 부분을 햇갈리면 안된다. 일치시켜야함
### body에 넣어야함 다른 구조의 아래에 들어가면 정상 동작이 안되는 경우가 있다.


# Web 정리 중요요소
## THML hyper Text Markup language
 * HTML 문서의 기본구조
 * DOM
 * 시맨틱 태그
 * 주요 태그와 속성
  * table, form, input 
## CSS
  * 단위(크기,속성)
  * 선택자 및 우선순위
  * 박스 모델
  * 인라인, 블록 요소 특징
  * Position
    * static
    * relative
    * absolute (out of flow)
    * fixed (out of flow)
    * **Flex**
      * align, justify 중요
      * axis, container - item
## 반응형 웹
* Booststrap
  * Grid System
  * Breakpoint
