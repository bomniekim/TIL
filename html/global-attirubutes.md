# 전역 속성(global attributes)

전역 속성(global attributes)이란 모든 HTML 요소에서 공통적으로 사용 가능한 속성이다.

<br>
<br>

## `class`

요소에 별칭을 지정한다. 한 요소에 여러 `class`를 지정할 수 있으며 공백으로 구분한다.

```html
<!-- a 와 b 라는 2 개의 클래스를 지정 -->
<div class="a b">division</div>
```

<br>

## `id`

문서에서 고유한 식별자(idenifier)를 지정한다.

<br>

## `style`

요소에 지정할 CSS를 선언한다. (inline style)

```html
<span style="color: blue;">text</span>
```

<br>

## `title`

요소의 정보(설명)을 지정합니다.

```html
<div title="title">show title</div>
```

<br>

## `lang`

요소에서 사용하는 주요 언어를 지정한다.

```html
<p lang="en">This paragraph is English</p>
<p lang="ko">이 단락은 한글입니다.</p>
<p lang="fr">Ce paragraphe est défini en français.</p>
```

<br>

## `data-*`

사용자 정의 데이터 속성을 지정한다.

> HTML에 JavaScript에서 이용할 수 있는 데이터(정보)를 저장하는 용도로 사용한다.

```html
<!-- data-custom-data-attributes -->
<h2 id="me" data-my-name="BominKim" data-my-color="blue">bomnie</h2>
```

```javascript
// dataset.customDataAttributes
const me = document.getElementById("me");
console.log(me.dataset.myName); // "BominKim"
console.log(me.dataset.myColor); // "blue"
```

<img src="../images/html/data.png" width="500">

<br>
<br>
<br>

## `draggable`

요소가 [Drag and Drop API](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API)를 사용 가능한지 여부를 지정한다.
이 속성을 지정하면 해당 요소를 드래그(Drag)할 수 있다. 기본값은 auto 이므로, 드래그 하기를 원하면 아래와 같이 draggable="true"라고 지정해야 한다.

```html
<div draggable="true">Drag it!</div>
```

<br>

## `hidden`

해당 요소가 아직(not yet), 또는 더 이상(no longer) 관련이 없음을 나타내는 Boolean 속성이다. 브라우저는 hidden 속성을 설정한 요소를 렌더링 하지 않기에 요소를 숨길 때 사용한다.

```html
<form id="hidden-form" action="/form-action" hidden>
  <input type="text" name="id" value="bomnie" />
</form>
<button form="hidden-form" type="submit">전송</button>
```

> &lt;form&gt; 에 `hidden` 속성을 부여하여 `<input>`이 렌더링 되지는 않지만 <br>[전송] 버튼 클릭 시 `file:///form-action?id=bomnie` url로 데이터가 전송된 것을 확인할 수 있다.

<br>
<br>

## `tabindex`

<kbd>Tab</kbd> 키를 이용해 요소를 순차적으로 포커스(Focus)하며 탐색할 순서를 지정한다.

- [대화형 콘텐츠(Interactive Content)](https://developer.mozilla.org/ko/docs/Web/Guide/HTML/Content_categories#%EB%8C%80%ED%99%94%ED%98%95_%EC%BD%98%ED%85%90%EC%B8%A0)는 기본적으로 코드 순서대로 탭 순서가 지정된다. (default: tabindex="0")
- 비대화형 콘텐츠에 tabindex="0"을 지정하면 대화형 콘텐츠와 같이 탭 순서를 사용한다.
  > 단, 비대화형 요소를 사용해 만든 대화형 컴포넌트는 접근성 트리에 나타나지 않으므로, 보조 기술이 해당 컴포넌트로 탐색하거나 조작하는 것을 방지한다.
- tabindex="-1"로 설정하면 포커스는 가능하지만 탭 순서에서 제외된다.
- tabindex="1" 이상의 양수 값은 논리적 흐름을 방해하기 때문에 사용을 추천하지 않는다.

<br>
<br>
<br>

---

### References

- [MDN global attributes](https://developer.mozilla.org/ko/docs/Web/HTML/Global_attributes)
- [한눈에 보는 HTML 요소 [전역 속성] by heropy](https://heropy.blog/2019/05/26/html-elements/#jeonyeog-sogseong-global-attributes)
