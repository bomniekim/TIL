# 스타일의 상속(inheritance)과 적용 우선 순위(cascading)
<br>

## 상속(Inheritance)

__상속__ 이란 상위(부모, 조상) 요소에 적용된 프로퍼티를 하위(자식, 자손) 요소가 물려 받는 것을 의미한다.<br> 상속 기능이 없다면 각 요소의 Rule set에 프로퍼티를 매번 각각 지정해야 한다.

> 상속되는 속성들(properties)
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
- white-space
    
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