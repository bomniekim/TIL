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
    
> 상속되지 않는 경우(상속받지 않는 요소 또는 상속되지 않는 프로퍼티), `inherit` 키워드를 사용하여 명시적으로 상속받게 할 수 있다.
