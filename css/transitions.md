# Transitions(전환)

기본적으로 CSS 속성 값의 변경에 따른 표시의 변화(transition)는 지체없이 즉시 발생한다.

트랜지션(`transition`)은 CSS 속성의 시작과 끝(전환 효과)을 지정하여 값의 변화가 일정 시간(duration)에 걸쳐 일어나도록 애니메이션 처리하여 변화를 부드럽게 한다.

transition 은 아래 속성들의 단축 속성이다.

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

타이밍 함수(애니메이션 효과를 계산하는 방법)을 지정한다.

<Br>
<Br>

### 4) `transition-delay`

전환 효과의 대기시간을 설정한다.

<br>
<br>

### 단축 속성