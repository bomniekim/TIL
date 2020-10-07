# Flexbox (CSS3 Flexible Box)

`Flexbox`는 모던 웹을 위하여 제안된 기존 layout보다 더 세련된 방식의 니즈에 부합하기 위한 CSS3의 새로운 layout 방식이다.

과거에는 화면 상의 요소를 수평 구조로 만드는 속성이 명확하지 않았기 때문에, `<table>`나 `float` 혹은 `inline-block` 등을 사용하여 구현하였다.<br>하지만 이러한 방법들은 다양한 문제를 가지고 있었고 구성의 차선책에 불과하였다.

이를 개선하기 위해 요소의 사이즈가 불명확하거나 동적으로 변화할 때에도 유연한 레이아웃을 실현할 수 있는 `Flexbox`가 고안되었다. <Br>이는 복잡한 레이아웃이라도 적은 코드로 보다 간단하게 표현할 수 있는 장점이 있다.

<br>

## Flex Container & Flex Items


`Flexbox`는 __flex items__ 이라 불리는 복수의 자식 요소와 이들을 정렬하기 위해 감싸는 __flex container__ 부모 요소로 구성된다.


<img src="../images/css/flex-base.jpg" width="600">


### Flex Container 속성

### 1) `display`

flex container(부모 요소)의 layout 배치를 정하는 속성이다.

|값|의미|
|---|---|
|`flex`| block 특성의 Flex Container를 정의(수직 쌓임)|
|`inline-flex`| inline 특성의 Flex Container를 정의(수평 쌓임)|

<br>

> `flex` 또는 `inline-flex`는 부모 요소에 반드시 지정해야 자식 요소가 flex item이 되어 flexbox를 사용할 수 있다.

<br>
<br>

### 2) `flex-direction`

flex container의 __주축(main axis)__ 방향을 설정한다.

|값|의미|default|
|---|---|---|
|`row`|items를 왼쪽에서 오른쪽(수평축)으로 표시|✔︎|
|`row-reverse`|items를 오른쪽에서 왼쪽(반대 수평축)으로 표시||
|`column`|items를 위에서 아래(수직축)로 표시||
|`column-reverse`|items를 아래에서 위(반대 수직축)로 표시||

<br>

<img src="../images/css/flex-direction.png" width="600">



### 주 축(main-axis)과 교차 축(cross-axis)

위에서 언급했었던 주 축(main-axis)과 교차 축(cross-axis)의 개념은 다음과 같습니다.
값 row는 Items를 수평축으로 표시하므로 이때는 주 축이 수평이며 교차 축은 수직이 됩니다.
반대로 값 column은 Items를 수직축으로 표시하므로 주 축은 수직이며 교차 축은 수평이 됩니다.
즉, 방향(수평, 수직)에 따라 주 축과 교차 축이 달라집니다.


### 시작점(flex-start)과 끝점(flex-end)

시작점(flex-start)과 끝점(flex-end)이라는 개념도 있습니다.
이는 주 축이나 교차 축의 시작하는 지점과 끝나는 지점을 지칭합니다.
역시 방향에 따라 시작점과 끝점이 달라집니다.



<hr>

### References
- [Understanding the CSS3 Flexbox](http://blogs.quovantis.com/understanding-the-css3-flexbox/)










