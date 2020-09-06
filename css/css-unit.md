# CSS 프로퍼티 값의 단위

CSS에서 사용되는 대표적인 크기의 단위는 다음과 같다.

<br>
<br>

## 1. `px` (픽셀)
`px`은 픽셀(화소) 단위로써 스크린 해상도를 기준으로 하는 단위이다.<br> 1px은 화소 1개 크기를 의미하며 디바이스 해상도(resolution)에 따라 상대적인 크기를 갖는다.

> 대부분의 브라우저는 1px을 1/96 인치의 절대단위로 인식한다.

px은 요소의 크기나 이미지의 크기 지정에 주로 사용된다.

<br>

## 2. `%`(백분율)

`%`는 백분률 단위의 상대 단위이다. <br>요소에 지정된 사이즈(부모 요소의 사이즈(상속된 사이즈)나 default 사이즈)에 영향을 받아 그에 대한 상대적인 사이즈를 설정한다. 

<br>

## 3. `em`

`em`은 배수(倍數) 단위의 상대 단위이다. em 단위는 상위 요소 크기의 몇 배인지로 사이즈를 설정한다.<br>

> _주의_<br>중첩된 자식 요소에 em을 지정하면 모든 자식 요소의 사이즈에 영향을 미치기 때문에 주의하여야 한다.

```html
<body>
  <div>child</div>
</body>
```
```css
div {
    font-size: 1.2em
    /* 16px * 1.2 = 19.2px */
    /* 대부분 브라우저의 기본 폰트 크기는 16px. */
}
```

em은 자기 자신의 font-size에 영향을 받는다.


<br>

## 4. `rem` (root em)

`rem`은 __최상위 요소(html)의 사이즈__ 를 기준으로 삼는 상대 단위이다.<br>em과 달리 최상위 부모의 값(하나)을 기준으로 하기 때문에 중첩된 자식 요소에서도 크기를 지정하는데 혼동없이 사용할 수 있다는 장점을 가진다.

`<html>`의 `font-size`는 브라우저마다 다르며, reset-css 등의 라이브러리를 사용하는 경우 사이즈 지정이 되어있지 않은 상태이므로 기본 값을 사용하거나 사용자가 직접 값을 지정할 수 있다.

```css
html {
    font-size: 14px;
}
```

<br>

## 5. 뷰포트(Viewport) 단위


---

[여기](https://developer.mozilla.org/ko/docs/Learn/CSS/Building_blocks/Values_and_units)


### References
- [MDN CSS 값과 단위](https://developer.mozilla.org/ko/docs/Learn/CSS/Building_blocks/Values_and_units)
- https://poiemaweb.com/css3-units

