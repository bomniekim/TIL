# 블록(block) 요소 vs. 인라인(inline) 요소

## block element

```css
display: block;
```

**블록 요소** 는 기본적으로 부모 요소의 전체 공간을 차지하여 사용 가능한 최대 가로 너비를 사용하여 "블록"을 만든다.

> A block-level element always starts on a new line and takes up the full width available (stretches out to the left and right as far as it can).
> <br> > <br>
> 특징

- `width: 100px, height: 0` 으로 시작하여 수직으로 쌓인다.

- margin, padding 의 상하좌우 모든 값을 지정하여 사용할 수 있다.
- layout 작업에 최적화된 태그이다.
- `<div>`,`<h>`,`<p>` 등 <br>

<br>
<br>

## inline element

```css
display: inline;
```

**인라인 요소** 는 콘텐츠의 흐름을 끊지 않고, 요소를 구성하는 태그에 할당된 공간만 차지한다.

> An inline element does not start on a new line and only takes up as much width as necessary.

특징

- `width: 0, height: 0` 으로 시작하여
  수평으로 쌓인다.
- margin, padding 의 위/아래 값을 지정할 수 없다.
- text 작업에 최적화된 태그이다.

- `<span>`,`<img>`,`<a>`,`<strong>` 등
  <br>
  <br>
  <br>

# Refernece

- [MDN 블록 레벨 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Block-level_elements)
- [MDN 인라인 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Inline_elements)
- [MDN display](https://developer.mozilla.org/ko/docs/Web/CSS/display)
