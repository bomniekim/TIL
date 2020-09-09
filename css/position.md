# Position

`position` 은 요소의 위치 지정 방법(배치)의 유형(기준)을 지정하는 속성이다. <br>`top`, `bottom`, `left`, `right` 속성과 함께 사용하여 위치를 지정한다.

<br>

## Box Offset

- `top`

- `bottom`

- `right`

- `left`



## 1) `static` (기본 위치)

`static` 은 `position` 의 default 값으로 `position` 를 지정하지 않았을 때와 같다.

기본적인 요소의 배치 순서에 따라 위에서 아래로, 왼쪽에서 오른쪽으로 순서에 따라 배치되며 부모 요소 내에 자식 요소로써 존재할 때는 부모 요소의 위치를 기준으로 배치된다.

기본적으로 이 값을 지정할 일은 없지만 이미 설정된 position을 무력화하기 위해 사용될 수 있다.

`top`, `bottom`, `left`, `right`, `z-index` 속성은 무시된다.

<br>
<br>

## 2) `relative` (상대 위치)

요소를 일반적인 흐름에 따라 배치하고,
<u>자기 자신</u>을 기준으로 `top`, `bottom`, `left`, `right` 를 사용하여 위치를 이동시킨다.

> static을 선언한 요소와 relative를 선언한 요소의 차이점은 좌표 프로퍼티의 동작 여부뿐이며 그외는 동일하게 동작한다.


