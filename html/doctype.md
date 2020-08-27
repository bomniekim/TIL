# DOCTYPE, `<head>` 태그

<br>

## DOCTYPE

<br>
DOCTYPE(DTD, Document Type Definition: 문서 형식 정의)은 마크업(Markup) 언어에서 문서의 형식(버전)을 정의한다.

<br>

DOCTYPE은 HTML 문서의 버전 정보를 알려주는 역할을 한다. 이는 웹 브라우저에 우리가 제공할 HTML 문서를 어떤 버전의 해석 방식으로 구조화하면 되는지를 지정해준다.

<br>
현재는 'HTML 5' 버전이 표준이다.

<br>

```html
<!-- HTML 5 -->
<!DOCTYPE html>
```

<br>

> [W3C 문서 형식 정의 권고사항](https://www.w3.org/QA/2002/04/valid-dtd-list.html)

<br>

<br>

## `<head>`

`<head>` 태그는 해당 HTML 문서에 대한 정보(metadata)를 담는다.

<br>

> `<head>` 태그 내에서 사용되는 태그들

- `<title>`

- `<meta>`

- `<link>`

- `<style>`

- `<base>`

- `<script>`

<br>
<br>

### `<title>`

`<title>` 태그는 해당 HTML 문서의 제목을 표시한다. 이 정보는 브라우저에서 웹 페이지 탭에 노출된다.

<br>
<br>

### `<meta>`

HTML 문서(웹페이지)에 관한 정보(제작자, 내용, 키워드 등)를 검색엔진이나 브라우저에 제공한다. 다른 메타관련 요소로 나타낼 수 없는 메타데이터를 저장할 때 사용한다. 빈(Empty) 태그이다.

<br>

`<meta>` 태그가 제공하는 메타데이터는 다음 네 유형 중 하나이다.

| 속성         | 의미                                                                           | (예시)값                                   |
| ------------ | ------------------------------------------------------------------------------ | ------------------------------------------ |
| `charset`    | 문자를 인코딩하는 방식을 설정한다.                                             | utf-8, euc-kr                              |
| `name`       | 검색엔진 등에 제공하기 위한 정보의 종류(메타 데이터)를 지정한다.               | author, description, keywords, viewport 등 |
| `http-equiv` | 유사한 이름의 HTTP 헤더가 제공하는 정보와 동일한 "프래그마 지시문"을 지정한다. |
| `itemprop`   | 사용자 정의 메타데이터를 지정한다.                                             |

- `content`는 `name`, `http-equiv` 속성의 값을 설정할 때 사용한다.

<br>

사용예시

```html
<head>
  <!-- 문자를 인코딩하는 방식을 설정한다. -->
  <meta charset="utf-8" />

  <!-- 제작자의 정보를 표시한다. -->
  <meta name="author" content="Bomin Kim" />

  <!-- 사이트에 대한 설명을 표시한다. -->
  <meta name="description" content="This website is Awesome!" />
</head>
```

<br>

> [&lt;meta&gt;: 문서 서 레벨 메타데이터 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/meta)

<br>
<br>

### `<link>`

현재 문서와 외부 문서를 연결할 때 사용하는 태그이다. HTML 외부에서 작성된 문서, 특히 CSS 파일을 불러와 연결시키거나 아이콘 연결 등을 할 때 사용된다. 빈(Empty) 태그이다.

| 속성   | 의미                                                  | 값                      |
| ------ | ----------------------------------------------------- | ----------------------- |
| `rel`  | **(필수)** 현재 문서와 외부 문서와의 관계를 지정한다. | `stylesheet`, `icon` 등 |
| `href` | 외부 문서의 절대/상대경로                             | 경로 url                |

<br>
<br>

사용예시

```html
<head>
  <link rel="stylesheet" href="style.css" />
  <link rel="shortcut icon" href="favicon.ico" type="image/x-icon" />
</head>
```

<br>
<br>

### `<style>`

`<style>` 태그 안에는 CSS로 스타일을 작성한다. 일반적으로 CSS는 `<link>` 태그를 사용하여 외부에 작성하는 것이 좋으나 문서나 문서 일부에 대한 스타일 정보를 포함할 때 사용한다.

<br>

사용예시

```html
<head>
  <style type="text/css">
    div {
      color: blue;
    }
  </style>
</head>
```

<br>
<br>

### `<base>`

문서 내의 모든 상대 경로(URL)가 사용할 기준 URL을 지정한다. 문서에는 하나의 `<base>` 요소만 존재할 수 있다.

```html
<head>
  <base href="./css/" />
  <link rel="stylesheet" href="style.css" />
  <!-- 위의 경우 참조될 url의 주소는 ./css/style.css 이다. -->
</head>
```

<br>
<br>

---

### References

- [head 태그에는 무엇이 있을까? HTML의 메타데이터](https://developer.mozilla.org/ko/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML)

- [&lt;head&gt;: 문서 메타데이터 (헤더) 요소](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head)
- [&lt;meta&gt;: 문서 레벨 메타데이터 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/meta)
- [&lt;title&gt;문서 정보 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/title)
- [&lt;link&gt;: 외부 리소스 연결 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/link)
- [&lt;style&gt;스타일 정보 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/style)
- [&lt;base&gt;](https://developer.mozilla.org/ko/docs/Web/HTML/Element/base)

- [입문자에게 추천하는 HTML, CSS 첫걸음 | HEROPY Tech](https://heropy.blog/2019/04/24/html-css-starter/)
