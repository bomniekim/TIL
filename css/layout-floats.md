# Floats

모던 웹 페이지는 style과 layout을 담당하는 CSS를 사용하여 화면에 요소를 원하는 위치에 배열하는 layout을 구성하는 것이 바람직하다.

`float` 은 텍스트 내부에 이미지를 포함하고, 텍스트의 흐름을 자연스럽게 이어가게 구현할 수 있도록 도입되었다. <br> 레이아웃을 구성할 때 블록 레벨 요소는 수직으로 정렬된다. float 은 이러한 블록 레벨 요소를 왼쪽이나 오른쪽으로 띄운 후 가로(수평) 정렬하기 위해 사용되는 중요한 기법이다.

> float 이란 기본 레이아웃 흐름에서 벗어나 요소의 모서리가 페이지의 왼쪽이나 오른쪽에 이동하는 것이다.

<Br>

<img src="../images/css/float.png" width="600">

<br>
<br>

#### float 은 다음의 3 가지 속성을 가진다.

- `none` : 요소 띄움 없음 (default)

- `left` : 요소를 왼쪽으로 띄움
- `right` : 요소를 오른쪽으로 띄움


<Br>

#### [사용법]
```css
  img {
      float: left;
  }
```
<br>
<br>

## float 해제 하기

`float` 속성이 적용된 후 그 요소의 주위로 다른 요소들 역시 흐르게 되는데 이를 방지하기 위해서는 속성을 해제해야 한다.

<Br>

### 1) 형제 요소에 `clear`: (left, right, both) 지정 

`float` 속성이 추가된 요소의 다음 형제 요소에 clear 속성을 추가하여 해제한다.

|값|의미|default|
|---|---|---|
|`none`|요소 띄움 허용|✔︎|
|`left`|왼쪽 띄움 해제||
|`right`|오른쪽 띄움 해제||
|`both`|(추천) 양쪽 띄움 모두 해제||


```html
<div class="float-left">float</div>
<div class="float-left">float</div>
<div class="next">next</div>
```
```css

.float-left {
  float: left;
}

.next {
  clear: left;
}
```

<img src="../images/css/clear-left.png" width="400">

<br>

### 2) 부모 요소에 `overflow`: (hidden, auto) 지정 

float 속성이 추가된 요소의 부모 요소에 overflow 속성을 추가한다.

```html
<div class="parent">
  <div class="child">float</div>
  <div class="child">float</div>
</div>
<div class="next">next</div>
```
```css
.parent{
  overflow: hidden; /* or 'auto' */
}
.child {
  float: left;
}
```

> 1&rpar; 의 그림과 같은 모습으로 배치됨.

불필요한 형제 요소를 만들지 않고 `float` 속성을 해제할 수 있으나 `overflow` 는 `float` 의 해제와 실제로는 무관한 속성임으로 hack 이다.

<br>

### 3) __부모 요소에 `clearfix` 클래스 추가 (추천!)__

`float` 속성이 추가된 요소의 부모요소에 미리 지정된 `clearfix` 클래스를 추가한다.

```html
<div class="parent clearfix">
  <div class="child">float</div>
  <div class="child">float</div>
</div>
```
```css
.clearfix::after{
    content: "";
    clear: both;
    display: block; /* or 'table' */
}
```

__`::after`__ 선택자를 이용해 `float` 속성이 적용된 요소의 뒤쪽에 가상요소를 만들고 `clear` 속성을 지정해 `float` 을 해제한다.<br>
이를 통해 `clearfix` 클래스가 지정된 부분 안에서는 float 을 자유롭게 이용할 수 있다.

> 단, 자식 요소는 float 이 적용되는 요소만 배치해야 해제가 용이함으로 이 점을 주의하자!

<br>
<br>

## `display` 속성의 변경

`float` 속성이 추가된 요소는 `display` 속성의 값이 대부분 __`block`__ 으로 바뀐다.

> 가장 대표적으로 `inline` 요소인 `<span>`이 `block` 으로 변경된다.

<br>
<br>

---
### References
- [MDN Floats](https://developer.mozilla.org/ko/docs/Learn/CSS/CSS_layout/Floats)
- [W3C CSS Layout - float and clear](https://www.w3schools.com/css/css_float.asp)
- [poiemaweb - float](https://poiemaweb.com/css3-float)
- [Positioning things in CSS using floats](https://medium.com/@anasansari157/positioning-things-in-css-using-floats-9721d833d283)
