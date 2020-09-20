# Transitions(전환)

기본적으로 CSS 속성 값의 변경에 따른 표시의 변화(transition)는 지체없이 즉시 발생한다.

트랜지션(`transition`)은 CSS 속성의 시작과 끝(전환 효과)을 지정하여<br>
값의 변화가 일정 시간(duration)에 걸쳐 일어나도록 애니메이션 처리하여 변화를 부드럽게 한다.


<Br>

### 1) `transition-property`

전환 효과를 지정할 속성 이름을 지정한다.

|값|의미|default|
|---|---|---|
|`all`|모든 속성에 전환 효과 지정|✔︎|
|`속성이름`|전환 효과를 지정할 대상 속성 지정||

<Br>
<Br>

### 2) `transition-duration`

전환 효과의 지속시간 설정한다.
|값|의미|default|
|---|---|---|
|시간값|전환 효과가 지속되는 시간 설정|`0s`|

<br>

> 시간 값으로 소수점을 쓸 수 있으며, 초 단위(`s`) 또는 밀리 초 단위(`ms`)로 지정한다.<br>
transition-duration 프로퍼티값은 transition-property 프로퍼티값과 1:1 대응한다. 

<Br>
<Br>

### 3) `transition-timing-function`


타이밍 함수(애니메이션 효과를 계산하는 방법)을 사용하여 transition의 진행 속도를 조절한다. [eaisng 함수](https://easings.net/ko)라고도 한다.

|값|의미|cubic-bezier()값|default|
|---|---|---|---|
|`ease`|빠르게-느리게|(.25, .1, .25, 1)|✔︎|
|`linear`|일정하게|(0, 0, 1, 1)||
|`ease-in`|느리게-빠르게|(.42, 0, 1, 1)|
|`ease-out`|빠르게-느리게|(0, 0, .58, 1)|
|`ease-in-out`|느리게-빠르게-느리게|(.42, 0, .58, 1)|
|`cubic-bezier( n, n, n, n )`| 자신만의 정의(`0~1`)|
|`steps(n)`|`n`번 분할된 애니메이션(애니메이션을 스텝으로 쪼갬)|
|`inherit`|부모 요소의 속성 값 상속|

<Br>

-  `cubic-bezier()`를 통해 수치화하는 것이 브라우저에 더 최적화된 상태이다. [cubic-bezier()](https://www.w3schools.com/cssref/func_cubic-bezier.asp)를 사용할 때 쓰는 값은 [여기](https://cubic-bezier.com/#.17,.67,.83,.67)를 참조.

> 사용예시는 [여기](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function)에서 확인

<Br>
<Br>

### 4) `transition-delay`

전환 효과의 대기시간(초 단위(s) 또는 밀리 초 단위(ms))을 설정한다.

|값|의미|default|
|시간|전환 효과의 대기시간을 설정|`0s`|

<br>
<br>

### 단축 속성

`transition` 은 위의 모든 속성들 한번에 작성하는 단축 속성이다.
> [W3C shorthand syntax](https://www.w3.org/TR/css-transitions-1/#transition-shorthand-property)
``` 
  transition: property duration function delay
```

- 단축 속성으로 작성 시 `transition-duration`은 __반드시 지정__ 해야 한다. 지정하지 않는 경우 기본값 0이 셋팅되어 어떠한 트랜지션도 실행되지 않는다. 기본값은 아래와 같다.
```css
.box {
    transition: all 0 ease 0;
}
```

- `transition` 은 변형하고자 하는 본래의 요소에 지정하는 것이 적합하다.

<br>
<br>

---
### References
- [transition via MDN](https://developer.mozilla.org/ko/docs/Web/CSS/transition)
- [Using CSS transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
- [transition-timing-function via coding-factory](https://www.codingfactory.net/10942)
- [transition via poiemaweb](https://poiemaweb.com/css3-transition)

