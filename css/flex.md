# Flexbox (CSS3 Flexible Box)

`Flexbox`는 모던 웹을 위하여 제안된 기존 layout보다 더 세련된 방식의 니즈에 부합하기 위한 CSS3의 새로운 layout 방식이다.

과거에는 화면 상의 요소를 수평 구조로 만드는 속성이 명확하지 않았기 때문에, `<table>`나 `float` 혹은 `inline-block` 등을 사용하여 구현하였다.<br>하지만 이러한 방법들은 다양한 문제를 가지고 있었고 구성의 차선책에 불과하였다.

이를 개선하기 위해 요소의 사이즈가 불명확하거나 동적으로 변화할 때에도 유연한 레이아웃을 실현할 수 있는 `Flexbox`가 고안되었다. <Br>이는 복잡한 레이아웃이라도 적은 코드로 보다 간단하게 표현할 수 있는 장점이 있다.

<br>

## Flex Container & Flex Items


`Flexbox`는 __flex items__ 이라 불리는 복수의 자식 요소와 이들을 정렬하기 위해 감싸는 __flex container__ 부모 요소로 구성된다.

- Flex Container 관련 속성은 [이 문서](https://github.com/bomniekim/TIL/blob/master/css/flex-container.md)를 참조.
- Flex Items 관련 속성은 [이 문서](https://github.com/bomniekim/TIL/blob/master/css/flex-items.md)를 참조.


<img src="../images/css/flex-base.jpg" width="600">

<br>
<br>


### 주 축(main-axis)과 교차 축(cross-axis) 

flexbox 에서 축(axis)의 개념은 container의 자식 요소인 items의 배치 흐름의 방향에 대한 것이다.<br>
주 축은 배치 흐름과 같은 방향의 축을 말하고, 교차 축은 주 축을 가로 지르는 축을 말한다.<Br>
값 `row`는 items를 __수평__ 축으로 배치하므로 이때는 주 축이 수평이며 교차 축은 수직이 된다.<br>
반대로 값 `column`은 items를 __수직__ 축으로 배치하므로 주 축은 수직이, 교차 축은 수평이 된다.<br>
_즉, 방향(수평, 수직)에 따라 주 축과 교차 축이 달라진다._

<br>
<br>


### 시작점(flex-start)과 끝점(flex-end)

시작점(`flex-start`)과 끝점(`flex-end`)이라는 개념도 있다.<br>
이는 주 축이나 교차 축의 시작하는 지점(axis start)과 끝나는 지점(axis end)을 지칭하는 것으로써 이 역시 방향에 따라 시작점과 끝점이 달라진다.

<img src="../images/css/flex-axis.png" width="700">



<br>
<br>




<hr>


### References
- [flexbox via MDN](https://developer.mozilla.org/ko/docs/Learn/CSS/CSS_layout/Flexbox)

- [CSS Flex(Flexible Box) 완벽 가이드
 by heropy](https://heropy.blog/2018/11/24/css-flexible-box/)
- [Understanding the CSS3 Flexbox](http://blogs.quovantis.com/understanding-the-css3-flexbox/)
- [모던 레이아웃 - 플렉스박스(Flexbox)](https://webclub.tistory.com/628)










