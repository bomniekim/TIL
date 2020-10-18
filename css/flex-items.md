## Flex Items 속성

### 1) `order`

flex items의 배치 순서를 설정한다.<br> HTML 코드를 변경하지 않고 `order` 속성 값을 지정하는 것으로 간단히 재배치할 수 있다는 장점을 가진다.<br>
기본 배치 순서는 `flex container`에 추가된 순서이다.

|값|의미|default|
|---|---|---|
|숫자|items의 배치 순서를 지정|`0`|
> 음수가 허용

<img src="../images/css/flex-order.png" width="600">

<Br>
<Br>

### 2) `flex-grow`

item의 증가하는 너비의 비율을 설정한다.
숫자가 클수록 더 많은 너비를 가진다.<Br>
item이 가변 너비가 아니거나, 값이 0일 경우 효과가 없다.

|값|의미|default|
|---|---|---|
|숫자|item의 증가 너비 비율을 설정|`0`|
> 음수 값은 무효

<br>
<br>

### 3) `flex-shrink`

item이 감소하는 너비의 비율을 설정한다.
숫자가 클수록 더 많은 너비가 감소한다.<br>
item이 가변 너비가 아니면 효과가 없으며 0을 지정하면 축소가 해제되어 원래의 너비를 유지한다.

|값|의미|default|
|---|---|---|
|숫자|item의 감소 너비 비율을 설정|`1`|
> 음수 값은 무효

<br>
<br>

### 4) `flex-basis`

item의 (공간 배분 전) 기본 너비를 설정합니다.<br>
값이 `auto`일 경우 width, height 등의 속성으로 item의 너비를 설정할 수 있다.<br>
하지만 단위 값이 주어질 경우 설정할 수 없다.

|값|의미|default|
|---|---|---|
|auto|가변 item과 같은 너비|✔|
|단위|px, em, cm 등 단위로 지정|

<br>
<br>

### `flex`

위의 2) ~ 4) 의 단축 속성으로써 item의 너비(증가, 감소, 기본)를 설정한다.

```css
    flex: 증가너비 감소너비 기본너비;
```
<br>
<br>

### 5) `align-self`

교차 축(cross-axis)에서 개별 item의 정렬 방법을 설정한다.

`align-items`는 container 내 모든 items의 정렬 방법을 설정하는 반면,
필요에 의해 일부 item만 정렬 방법을 변경하려고 할 경우 `align-self`를 사용한다.

이 속성은 align-items 속성보다 __우선한다__.

<img src="../images/css/align-self.png" widht="600">


