# 스타일의 상속(inheritance)과 적용 우선 순위(cascading)
<br>

## 상속(Inheritance)

__상속__ 이란 상위(부모, 조상) 요소에 적용된 프로퍼티를 하위(자식, 자손) 요소가 물려 받는 것을 의미한다.<br> 상속 기능이 없다면 각 요소의 Rule set에 프로퍼티를 매번 각각 지정해야 한다.

> 상속되는 속성들(properties)
: 대부분 text를 다루는 속성들
- font
  - font-size
  - font-weight
  - font-style
  - line-height
  - font-family
- color
- text-align
- text-indent
- text-decoration
- opacity / visibility
- letter-spacing
- white-space 등
    
> 강제 상속: 상속되지 않는 경우(상속받지 않는 요소 또는 상속되지 않는 프로퍼티), `inherit` 키워드를 사용하여 명시적으로 상속받게 할 수 있다.<br>


```html
<div class="parent">
    parent
  <div class="child">child</div>
</div>
```
```css
.parent {
    position: absolute;
    /* 상속되지 않는 position 속성 */
}
.child {
    position: inherit;
    /* 강제 상속 받아 부모의 position과 동일 */
}
```
> '자식'을 제외한 '후손'에게는 적용되지 않으며, 모든 속성이 강제 상속을 사용할 수 있는 것은 아니다.

<br>
<br>
<br>

## 캐스캐이딩(Cascading)

요소는 하나 이상의 CSS 선언에 영향을 받을 수 있다. 이때 충돌을 피하기 위해 CSS 적용 우선순위가 필요한데 이를 캐스캐이딩(Cascading Order)이라고 한다.

캐스캐이딩에는 다음과 같이 세가지 규칙이 있다.
> 1. __명시도__
<br>대상을 명확하게 특정할수록 명시도가 높아지고 우선순위가 높아진다.
<br><br>[명시도의 점수]<br><br>1&rpar; 가장 중요(<code>!important</code>): 모든 선언을 무시하고 가장 우선한다. (`∞` point)<br>
2&rpar; 인라인 선언 : HTML <code>style</code> 속성 사용 (`1000` point)
<br>
3&rpar; 아이디 선택자 (`100` point)
<br>
4&rpar; 클래스 선택자 (`10` point)
<br>
5&rpar; 태그 선택자 (`1` point)
<br>
6&rpar; 전체 선택자 (0 point)
<br>
7&rpar; 상속 (점수 없음): 상속 받은 속성은 항상 우선하지 않는다.



> 2. __중요도__
<br>CSS가 어디에 선언 되었는지에 따라서 우선순위가 달라진다.

> 3. __선언순서__
<br>선언된 순서에 따라 우선 순위가 적용된다. 즉, 나중에 선언된 스타일이 우선 적용된다.

