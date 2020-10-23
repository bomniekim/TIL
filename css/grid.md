# 그리드(Grid)

CSS `Grid`(그리드)는 __2차원__(행과 열)의 레이아웃 시스템을 제공한다.<br>
Flexible Box가 비교적 단순한 1차원 레이아웃을 위한 것이라면, 좀 더 복잡한 레이아웃을 위해 CSS Grid를 사용할 수 있다.

CSS Grid는 예전부터 핵(Hack)으로 불린 다양한 레이아웃 대체 방식들을 해결하기 위해 만들어진 특별한 CSS 모듈이다.


## Grid Container & Grid Items

`CSS Grid`는 CSS Flex와 같이 Container(컨테이너)와 Item(아이템)이라는 두 가지 개념으로 구분되어 있다.
Container는 Items를 감싸는 부모 요소이며, Items는 컨테이너 안에서 배치되는 복수의 자식 요소들이다.

<br>
<br>

## Grid Container 속성

### 1) `display`

Grid Container(컨테이너)의 layout 배치를 정의하는 속성이다.

|값|의미|
|---|---|
|`grid`| block 특성의 Grid Container를 정의|
|`inline-grid`| inline 특성의 Grid Container를 정의|


> Grid를 사용하기 위해 container의 `display` 값을 필수로 작성해야 한다. 정의된 container의 자식 요소들은 자동으로 Grid Items로 정의된다.

<br>
<br>

### 2) `grid-template-rows`

__명시적 행__(`Track`)의 크기를 정의한다.
동시에 라인(Line)의 이름도 정의할 수 있다.<br>


```css
.container {
  display: grid;
  grid-template-rows: 1행크기 2행크기 ...;
  grid-template-rows: [line 이름] 1행크기 [line 이름] 2행크기 [line 이름] ...;
}
```

```css
.container {
  grid-template-rows: 100px 200px;
}
/* 각 행의 크기를 정의. */

.container {
  grid-template-rows: [first] 100px [second] 200px [third];
}
/*  각 라인의 이름과 행의 크기를 동시에 지정 가능 */

.container {
  grid-template-rows: [row1-start] 100px [row1-end row2-start] 200px [row2-end];
}
/* 라인에 중복된 이름 지정 가능 (2번째 line의 이름은 row1-end이면서 row2-start임) */
```

> 각 라인은 행과 열의 개수대로 숫자(양수/음수) 라인 이름이 자동으로 지정되어 있어서, 꼭 필요한 경우가 아니면 라인 이름을 정의하지 않아도 된다.




<hr>

### References

- [이번에야말로 CSS Grid를 익혀보자 via 1분코딩](https://studiomeal.com/archives/533)






