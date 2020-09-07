# 박스 모델(Box Model)

모든 HTML 요소는 Box 형태의 영역을 가지고 있다. 이 Box는 콘텐트(Content), 패딩(Padding), 테두리(Border), 마진(Margin)로 구성된다.

<img src="../images/css/box-model.png" width="600">

브라우저는 박스 모델의 크기(dimension)와 프로퍼티(색, 배경, 모양 등), 위치를 근거로 하여 렌더링을 실행한다.

<br>
<br>

## `content`

요소의 텍스트나 이미지 등의 실제 내용이 위치하는 영역이다. `width`, `height`를 갖는다.

### 1) width
> 요소의 가로 너비

|값|의미|default|
|---|---|---|
|`auto`|브라우저가 너비를 계산|`auto`|
|단위|`px`, `em`, `%` 등||

<br>

### 2) height
> 요소의 세로 높이

|값|의미|default|
|---|---|---|
|`auto`|브라우저가 높이를 계산|`auto`|
|단위|`px`, `em`, `cm` 등||

<br>

### 3) 박스의 최대/최소 너비/높이

- `max-width` / `max-height` : 기본값은 none

- `min-width` / `min-height` : 기본값은 0

<Br>
<Br>

## `margin`

요소의 '__외부(바깥) 여백__'을 지정한다.
> 음수 값(Negative Values)을 사용할 수 있다.

|값|의미|default|
|---|---|---|
|단위|`px`, `em`, `cm` 등|`0`|
|`auto`|브라우저가 너비를 계산||
|`%`|_부모 요소의 __너비___ 에 대한 비율로 지정||

<br>

[사용법]
```css
.box {
    margin: 10px 20px 30px 40px;
    /* top - right - bottom - left */
    margin: 10px 20px 40px;
    /* top - (right/left) - bottom */
    margin: 10px 40px;
    /* (top/bottom) - (right/left) */
    margin: 10px;
    /* all */
}
```

<br>

## 마진 중복(병합,상쇄 Margin Collapse)

마진의 특정 값들이 '중복'되어 합쳐지는 현상이다. 이는 버그(오류)가 아니며 우회하거나 응용할 수 있다. 다음은 마진 중복이 발생하는 경우이다.

<br>

### 1) 형제 요소들의 `margin-top` 과 `margin-bottom` 이 만났을 때

<img src="../images/css/mc_adjacent.png" width="600">

> margin: 30px을 설정한 `div` <br> `margin-top` 과 `margin-bottom`이 만나는 부분의 마진 상쇄가 발생했다.

<img src="../images/css/mc_adjacent2.png" width="600">

> 형제 요소의 `margin-left`와 `margin-right`가 중첩되는 경우는 마진이 상쇄되지 않고 보존된다.

<br>


### 2) 부모 요소의 `margin-top` 과 자식 요소의`margin-top` 이 만났을 때
### 2) 부모 요소의 `margin-bottom` 과 자식 요소의`margin-bottom` 이 만났을 때







