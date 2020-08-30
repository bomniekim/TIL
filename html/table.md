# 표 컨텐츠(table)

## `<table>`

표(table)를 표현할 때 사용한다.
모든 표 컨텐츠를 아우르는 태그이다.

<br>
<br>

## `<tr>`,`<th>`,`<td>`

- `<tr>` : 표의 행(줄)을 생성한다. `<th>`와 `<td>`를 자식요소로 가진다.
- `<th>`: 칸(cell)의 header를 지정한다.
- `<td>`: 데이터를 포함하는 칸(cell)을 지정한다.

<br>
<br>

### `<th>`

머리글 칸을 나타내는 데이터를 표시한다.<br>
기본적으로 굵은 글씨로 표시된다.

<br>

#### 속성

- `abbr`: cell content에 대한 간단한 설명을 작성한다.
- &#127775; `colspan` / `rowspan`: 병합하려는 열/행의 수를 지정한다.
- `scope`: 해당 &lt;th&gt;가 누구의 머리글 칸인지를 명시한다.
  - `col`: 자신의 열
  - `colgroup`: 모든 열
  - `row`: 자신의 행
  - `rowgroup`: 모든 행
  - `auto` : default
- `headers`: 다른 머리글 칸의 id와 같은 값으로 연결해 관련성을 나타낸다.

> 사용예시

```html
<table>
  <caption>
    데이터의 타입과 값
  </caption>
  <tr>
    <th colspan="2" id="th-data">데이터</th>
  </tr>
  <tr>
    <th headers="th-data">타입</th>
    <th headers="th-data">값</th>
  </tr>
  <tr>
    <th>알파벳</th>
    <th>A</th>
  </tr>
</table>
```

<br>

### `<td>`

일반 칸의 데이터를 표시한다.

#### 속성

- `headers`
- `colspan` / `rowspan`

<br>
<br>

## `<caption>`

표의 전체 제목을 표시한다.

- 열리는 `<table>` 바로 다음에 작성해야 한다.
- `<table>` 당 하나의 `<caption>`만 사용 가능하다.

<br>
<br>

## `<colgroup>` / `<col>`

표의 열들을 공통적으로 정의하는 컬럼(`<col>`:column)과 그의 집합(`<colgroup>`:column group)을 정의한다.<br>
주로 스타일을 일괄적으로 처리하기 위해 사용한다.

<br>

#### 속성

- `span`: 연속되는 열의 수를 숫자로 정의한다.

사용예시

```html
<table>
  <caption>
    Superheros and sidekicks
  </caption>
  <colgroup>
    <col />
    <col span="2" class="batman" />
    <col span="2" class="flash" />
  </colgroup>
  <tr>
    <td></td>
    <th scope="col">Batman</th>
    <th scope="col">Robin</th>
    <th scope="col">The Flash</th>
    <th scope="col">Kid Flash</th>
  </tr>
  <tr>
    <th scope="row">Skill</th>
    <td>Smarts</td>
    <td>Dex, acrobat</td>
    <td>Super speed</td>
    <td>Super speed</td>
  </tr>
</table>
```

<br>
<br>

## `<thead>` / `<tbody>` / `<tfoot>`

테이블의 영역을 묶어주기 위해 사용한다. 레이아웃에는 영향을 주지 않고 브라우저에게 의미를 전달한다.

<br>
<br>

---

### References

- [표 컨텐츠 by heropy](https://heropy.blog/2019/05/26/html-elements/#pyo-kontenceu)
- [MDN table](https://developer.mozilla.org/ko/docs/Web/HTML/Element/table)
