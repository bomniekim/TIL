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
동시에 라인(Line)의 이름도 정의할 수 있다.
<br>
<Br>

### 3) `grid-template-columns`

__명시적 열__(`Track`)의 크기를 정의한다.
동시에 라인(Line)의 이름도 정의할 수 있다.<br>

<br>

> `grid-template-rows` 와 `grid-template-columns` 의 사용방법은 같다. <br> 따라서 아래의 사용방법에서 rows를 columns로 바꾸면, 행과 관련된 값이 열에 관련된 값으로 바뀐다.

<br>

### 사용방법

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

<br>
<br>

### 4) `grid-template-areas`





<hr>

### References

- [이번에야말로 CSS Grid를 익혀보자 via 1분코딩](https://studiomeal.com/archives/533)






