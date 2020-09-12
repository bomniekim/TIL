# Background

다음은 요소에 배경을 설정할 때 지정하는 요소들이다.

- `background-color` : 배경 색상 지정
- `background-image` : 하나 이상의 배경 이미지 지정
- `background-repeat` : 배경 이미지의 반복 여부 지정
- `background-position` : 배경 이미지의 위치 지정
- `background-attachment` : 배경 이미지의 스크롤 여부 지정
- `background-size` : 배경 이미지의 크기 지정


<br>
<br>

## 1) `background-color`

요소의 배경 색상을 지정한다.

|값|의미|default|
|---|---|---|
|색상|요소의 배경 색상||
|`transparent`|투명|✔︎|

```css
.box { 
  background-color: tomato;
}
```

<br>

<br>

## 2) `background-image`

요소의 배경에 __하나 이상의 이미지__ 를 삽입한다.

|값|의미|default|
|---|---|---|
|none|이미지 없음|✔︎|
|url("경로")|이미지 경로||
<br>

```css
.box {
    background-image: url("../images/css/image.png");
    width: 120px;
    height: 80px;
}
```
> 배경 이미지 삽입 시, 요소의 크기가 설정되어야 배경 이미지가 보인다.

```css
.box2 {
    background-image:
    url("../images/css/image1.png"),
    url("../images/css/image2.png"),
    url("../images/css/image3.png");
}
```
> 하나 이상의 배경 이미지를 지정하는 경우, `,`로 구분하며 __먼저 작성된 이미지가 더 위에 쌓인다.__

<br>
<br>

## 3) `background-repeat`

요소의 배경 이미지의 반복 여부를 설정한다.

|값|의미|default|
|---|---|---|
|`repeat`|배경 이미지를 수직, 수평으로 반복|✔︎|
|`repeat-x`|배경 이미지를 수평으로 반복||
|`repeat-y`|배경 이미지를 수직으로 반복||
|`no-repeat`|반복 없음||

#### 사용예시는 [여기](https://developer.mozilla.org/ko/docs/Web/CSS/background-repeat)를 참조.

<br>
<br>

## 4) `background-position`

요소의 배경 이미지의 좌표를 설정하여 위치를 지정한다.

|값|의미|default|
|---|---|---|
|`%`|왼쪽 상단 모서리는 `0% 0%`,<br>오른쪽 하단 모서리는 `100% 100%`|`0% 0%`|
|방향|방향(`top`, `bottom`, `left`, `right`, `center`)을 입력하여 위치 설정||
|단위|px, em, cm 등||

<br>

### [사용예시]
- 값이 방향일 경우
```css
  background-position: 방향1, 방향2;
```

방향 순서 상관 없이 작성 가능하다. 가운데 위치 시 `center` 하나만 지정하면 된다. 

<br>

- 값이 단위(`%`, `px` 등)일 경우
```css
  background-position: X축, Y축;
```
`left` / `right` 는 X축에 관한 개념이므로 1 번 자리에 작성한다.<br>
`top` / `bottom` 는 Y축에 관한 개념이므로 2 번 자리에 작성한다.

- `%`는 부모요소를 기준으로 하며, 방향과 단위를 같이 사용할 수 있다.

<br>
<br>

## 5) `background-attachment`

요소가 스크롤될 때 배경 이미지의 스크롤 여부(특성)을 설정한다.

|값|의미|default|
|---|---|---|
|scroll|배경 이미지가 요소를 따라서 같이 스크롤|✔︎|
|fixed|배경 이미지가 뷰포트(Viewport)에 고정되어, 요소와 같이 스크롤 되지 않음 (e.g [스타벅스](https://www.starbucks.co.kr/index.do))|
|local|요소 내 스크롤 시 배경 이미지가 같이 스크롤|
> local 은 지역적으로 스크롤을 할 수 있도록 설정할 때 사용한다.


#### 사용예시는 [여기](https://developer.mozilla.org/ko/docs/Web/CSS/background-attachment)를 참조.

<br>
<br>

## 6) `background-size`

요소의 배경 이미지의 크기를 설정한다.

|값|의미|default|
|---|---|---|
|`auto`|배경 이미지가 원래의 크기로 표시|✔︎|
|단위| - px, em, % 등 단위로 지정<br> - width, height 형태로 입력 가능 (e.g `120px 330px`)<br> - width 만 입력하면 비율에 맞게 지정됨 (e.g `120px`)||
|`cover`| - 배경 이미지의 크기 비율을 유지하며, 요소의 더 __넓은__ 너비에 맞춰짐<br> - 이미지가 잘릴 수 있음 
|`contain`| - 배경 이미지의 크기 비율을 유지하며, 요소의 더 __좁은__ 너비에 맞춰짐<br> - 이미지가 잘리지 않음

<br>

- `cover`
```css
.img {
  background-image: url("imageUrl") /* 400 * 400*/  
  width: 400px;
  height: 300px;
  background-size: cover;
}
```
<img src="../images/css/cover.png" width="400">

> 요소의 __넓은__ 너비(400px)에 맞추어 요소 사이즈 조절.

<br>

- `contain`
```css
.img {
  background-image: url("imageUrl") /* 400 * 400*/  
  width: 400px;
  height: 300px;
  background-size: contain;
}
```
<img src="../images/css/contain.png" width="400">

> 요소의 __좁은__ 너비(300px)에 맞추어 요소 사이즈 조절.

<br>
<br>


### 단축 속성(shorthand)

```css
  background: color || imgUrl || repeat || position || attachment
```
<br>

### 접근성 고려사항

브라우저는 배경 이미지에 대한 어떠한 추가적인 정보를 접근성 보조 기술에 제공하지 않는다. 특히 스크린 리더의 경우 배경 이미지의 존재 유무조차 알려주지 않는다. 그렇기 때문에 이미지가 페이지 를 이해하거나 설명하는 데 필수적인 정보를 갖고 있다면 문서에서 semantic하게 설명하는 편이 좋다.

> 예를 들어
[text-intent를 이용한 웹 접근성
](https://github.com/bomniekim/TIL/blob/master/css/font.md#user-content-text-intent%EB%A5%BC-%EC%9D%B4%EC%9A%A9%ED%95%9C-%EC%9B%B9-%EC%A0%91%EA%B7%BC%EC%84%B1) 등을 사용하자!

<br>
<br>

--- 
### References
- [background via MDN](https://developer.mozilla.org/ko/docs/Web/CSS/background)
- [poiemaweb CSS background](https://poiemaweb.com/css3-background)
- [CSS background - Shorthand property](https://www.w3schools.com/css/css_background_shorthand.asp)