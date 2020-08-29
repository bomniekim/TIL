# image tag & multimedia tags

이미지와 멀티미디어 태그

- &lt;img&gt;
- &lt;audio&gt;
- &lt;video&gt;
- &lt;img&gt;
- &lt;img&gt;

## `<img>`

문서에 이미지를 삽입할 때 사용하는 태그이다.

<br>
속성

- `src` : **(필수)** 이미지 url
- `alt` : **(필수)** 이미지의 대체 텍스트 설명

> 빈 문자열(alt="")을 사용한 경우, 이미지가 콘텐츠의 중요 부분이 아니므로(장식 또는 추적용 픽셀 등), 비 시각적 브라우저가 렌더링을 하지 않아도 된다는 의미이다. 시각적 브라우저에서도 alt 특성이 비어있을 경우 깨진 이미지 아이콘을 표시하지 않는다.

- `width`, `height` : 이미지의 가로/세로 너비

<br>
반응형 웹의 이미지를 위한 속성

> CSS의 @media 대신 HTML의 `<img>`의 `srcset`과 `sizes` 속성을 이용하여 쉽게 반응형 이미지를 설정할 수 있다.

- `srcset` (source set)
- `sizes`

<br>

사용예시

```html
<img
  srcset="
    images/ex_small.png   400w,
    images/ex_medium.png  700w,
    images/ex_large.png  1000w
  "
  src="images/ex.png"
  alt="example image"
/>
```

#### `<srcset>`

브라우저가 사용할 수 있는 이미지 소스의 후보이다. 쉼표로 구분하는 한 개 이상의 문자열 목록입니다. 각각의 문자열은 다음 구성요소로 이루어집니다.
`<srcset>`은 브라우저에 출력될 이미지들과 그 이미지들의 원본 크기를 지정한다. (2장 이상)

사용할 이미지를 사이즈별로 2장 이상 준비하여 srcset 속성에 작성합니다.
단, 주의사항은 이미지의 크기로 px단위가 아닌 w 디스크립터 혹은 x 디스크립터를 입력해야 하며, 작은 크기 이미지부터 순서대로 입력합니다

#### `<sizes>`

특정 뷰포트 크기에서 출력될 최적화된 이미지의 사이즈 지정
