# CSS layout
## css layout techniques


1. Display
2. Position
3. Float
4. Flexbox
5. Grid


# float

```
<style>
.floatbox{

  float : left;
  <!-- float : right; -->

}
</style>

```

 * 텍스트를 표현할 때 보통 사용한다.
 * 원하는 표현이 안될 수 있으니 유의 

## clearfix

* 원하는 표현을 위해서 float를 div로 감싸고 해당 div의 클래스 이름을 clearfix로 한다.

```

.clearfix::after{
  content : "";
  display : block;
  clear : both;



}


```

* 이렇게 하면 float했을 때 공중에 떠서 content들이 겹치는 현상을 없앨 수 있다.
<br><br><br>

# Flexbox

* CSS flexble Box Layout
* 행과 열 형태로 아이템을 배치하는 레이아웃 모델

1. main axis
2. cross axis 

## Flexbox 구성요소
```
{

  display : flex;

}

```
* Flox Conteainer
* Flex Item


* 왜 만들었을까?
  1. 수직정렬
  2. 아이템의 너비 간격을 동일하게



## Flex - direction
1. row
2. row-reverse
3. column
4. column-reverse

* 역방향의 경우 태그 선언 순서와 시각적으로 다르다!

## flex-wrap
1. wrap
2. nowrap

[FLEX](https://studiomeal.com/archives/197) 강의 사이트
*https://studiomeal.com/archives/197*


```
.Container {
  dlsplay : flex;

  flex-direction: row;
	/* flex-direction: column; */
	/* flex-direction: row-reverse; */
	/* flex-direction: column-reverse; */

} 


.items {


}
```
* row (기본값)
  * 아이템들이 행(가로) 방향으로 배치됩니다.

* row-reverse
  * 아이템들이 역순으로 가로 배치됩니다.

* column
  * 아이템들이 열(세로) 방향으로 배치됩니다.


* column-reverse
  * 아이템들이 역순으로 세로 배치 됩니다.

```
.container {
  
  dlsplay : flex;
	flex-wrap: nowrap;
	/* flex-wrap: wrap; */
	/* flex-wrap: wrap-reverse; */
}

```
```
nowrap (기본값)
줄바꿈을 하지 않습니다. 넘치면 그냥 삐져 나가요.

wrap
줄바꿈을 합니다. float이나 inline-block으로 배치한 요소들과 비슷하게 동작해요.

wrap-reverse
줄바꿈을 하는데, 아이템을 역순으로 배치해요. 그림을 보면 이해하실 수 있을 거예요.
```

## flex-flow
 *flex-direction과 flex-wrap을 한꺼번에 지정할 수 있는 단축 속성이예요.*
 *flex-direction, flex-wrap의 순으로 한 칸 떼고 써주시면 됩니다.*
```
.container {
	flex-flow: row wrap;
	/* 아래의 두 줄을 줄여 쓴 것 */
	/* flex-direction: row; */
	/* flex-wrap: wrap; */
}
```


## justify-content
* justify 키워드가 나왔죠? 메인축 방향으로 아이템을들 정렬하는 속성이예요.
```
.container {
	justify-content: flex-start;
	/* justify-content: flex-end; */
	/* justify-content: center; */
	/* justify-content: space-between; */
	/* justify-content: space-around; */
	/* justify-content: space-evenly; */
}
```

## align-items
* align 키워드가 나왔죠? 수직축 방향으로 아이템을들 정렬하는 속성이예요.

```
.container {
	align-items: stretch;
	/* align-items: flex-start; */
	/* align-items: flex-end; */
	/* align-items: center; */
	/* align-items: baseline; */
}
```


## 예제
```
.container {
	align-items: stretch;
	/* align-items: flex-start; */
	/* align-items: flex-end; */
	/* align-items: center; */
	/* align-items: baseline; */
}


.container {
	flex-wrap: wrap;
	align-content: stretch;
	/* align-content: flex-start; */
	/* align-content: flex-end; */
	/* align-content: center; */
	/* align-content: space-between; */
	/* align-content: space-around; */
	/* align-content: space-evenly; */
}
```


# boot strap

## CDN
* 컨텐츠를 효율적으로 전달하기 위해 쓰는 방법
* 링크 형태로 받는다.


## spacing
```
.mt-1{
  margin-top: 0.25rem !important;
}
```

```
<div class = "box mx-1">box1</div>
```
## color
```
생략
```

[http://bootstrapk.com/getting-started/](http://bootstrapk.com/getting-started/)
<br><br><br><br>

# 반응형 Web
## Grid system
* 요소들의 디자인과 배치에 도움을 주는 시스템
* 기본 요소
  * Column : 실제 컨텐츠를 포함하는 부분
  * Gutter : 칼럼과 칼럼 사이의 공간
  * Container : Column 을 담고 있는 공간


## 기본 구성

```
<div class = "container">
  <div class = "row">
    <div class = "col">1</div>
    <div class = "col">2</div>
    <div class = "col">3</div>
  </div>


</div>


```

* row에서 flex로 잡아주는 결과를 볼 수 있다.

## break point
* Grid options
  * .col-
  * .col-sm-
  * .col-md-
  ...

* Gutter width
  *  1.5 rem(0.75 on left , right 
  * 16*0.75 = 12 pixel


*총 12를 나눠서 구현한다.*
```
<!-- 1줄이 12이므로 4개로 나누어 보여준다. -->
<div class="row">
  <div class="box col-3">1</div>
  <div class="box col-3">2</div>
  <div class="box col-3">3</div>
  <div class="box col-3">4</div>
</div>


<!-- 3+3+3+4 이므로 13이다 4는 넘어간다. -->
<div class="row">
  <div class="box col-3">1</div>
  <div class="box col-3">2</div>
  <div class="box col-3">3</div>
  <div class="box col-4">4</div>
</div>

<div class="row">

  <div class="box col-3">1</div>
  <div class="box col-3">2</div>
  <div class="box col-3">3</div>
  <div class="box col-4">4</div>
</div>
<div class="row">

  <div class="box col-6">
    <div class="row">
      <div class="box col-3">1</div>
      <div class="box col-3">2</div>


    </div>
  </div>


  <div class="box col-6">
    <div class="row">
      <div class="box col-3">3</div>
      <div class="box col-3">4</div>    


    </div>
  </div>

</div>



```

* bootstrap에 여러 형식이 있으므로 참고하자