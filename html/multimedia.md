# 이미지와 멀티미디어 태그

<br>

## `<img>`

문서에 이미지를 삽입할 때 사용하는 태그이다.

#### 속성

- `src` : **(필수)** 이미지 url
- `alt` : **(필수)** 이미지의 대체 텍스트 설명

> 빈 문자열(alt="")을 사용한 경우, 이미지가 콘텐츠의 중요 부분이 아니므로(장식 또는 추적용 픽셀 등), 비 시각적 브라우저가 렌더링을 하지 않아도 된다는 의미이다. 시각적 브라우저에서도 alt 특성이 비어있을 경우 깨진 이미지 아이콘을 표시하지 않는다.

- `width`, `height` : 이미지의 가로/세로 너비로 고정된 이미지 크기를 유지할 때 사용한다.

<br>
반응형 웹의 이미지를 위한 속성

> CSS의 @media 대신 HTML의 `<img>`의 `srcset`과 `sizes` 속성을 이용하여 쉽게 반응형 이미지를 설정할 수 있다. (단, IE 미지원)

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
  sizes="(min-width: 1000px) 700px"
  src="images/ex.png"
  alt="example image"
/>
```

<br>
<br>

### `<srcset>`

`<srcset>`은 브라우저가 사용할 수 있는 이미지 소스의 후보로써 브라우저에 출력될 이미지들과 그 이미지들의 원본 크기를 지정한다. (2장 이상)

- **작은 크기 이미지부터 순서대로 입력한다.**
- `src`와 `srcset`를 함께 지정할 경우 `srcset`의 지정값을 사용할 수 없을 때 유효하다.
- 이미지의 크기로 px단위가 아닌 `w`/`x` 디스크립터를 입력해야 한다.

> `w` 디스크립터(Width descriptor)는 이미지의 원본 크기(가로 너비)를 의미한다. <br>브라우저는 지정된 w 디스크립터를 통해 각 이미지의 최적화된 픽셀 밀도를 계산한다.

> `x` 디스크립터(Device pixel ratio descriptor)는 이미지의 비율을 의미한다. <br>디바이스의 픽셀 비율(Device pixel ratio)과 일치하는 값으로 최적화 선택된다.

> - w 디스크립터를 사용하면 x 디스크립터를 사용하지 않아도 되어 많은 경우 w 디스크립터의 사용을 추천한다.

<br>
<br>

### `<sizes>`

미디어 조건과 함께 특정 뷰포트 크기에서 출력될 최적화된 이미지의 사이즈 지정한다.

> 위의 사용예시에서 (min-width: 1000px)은 ‘뷰포트 너비(가로)가 1000px 이상일 때’를 의미하며,<br> 700px은 지정한 미디어 조건일 때 이미지를 ‘700px로 최적화 출력하겠다’를 의미한다.

- 미디어 조건을 생략한 경우, <br>뷰포트 너비와 상관없이 `sizes`에 설정한 크기의 이미지만 사용한다.

- sizes와 width를 같이 작성할 경우 width가 우선한다.

<br>
<br>

## `<audio>`

문서에 소리 컨텐츠를 삽입할 때 사용하는 태그이다.

#### 속성

- `src`: 오디오 소스 url
- `autoplay`: 전체 오디오 파일의 다운로드를 기다리지 않고 가능한 빠른 시점에 재생을 시작한다.
  > [autoplay 설정 유의사항](https://developer.mozilla.org/ko/docs/Web/HTML/Element/audio#attr-autoplay)
- `controls`: 오디오 재생, 볼륨, 탐색, 일시 정지의 제어 메뉴를 표시한다.
- `loop`: 재생이 끝나면 다시 처음부터 재생한다.
- `preload`: 페이지가 로드될 때 파일을 로드할지의 지정한다.(힌트 제공)
  - none: 로드하지 않음
  - metadata: 메타데이터만 로드(default)
  - auto/"": 사용자가 사용하지 않더라도 자동으로 로드
    > `autoplay`와 `preload`를 함께 지정하면 `autoplay`가 우선한다.
- `muted`: 음소거 설정
  <br>
  <br>

## `<video>`

문서에 비디오 플레이백을 지원하는 동영상 컨텐츠를 삽입할 때 사용한다.

#### 속성

- `src` : 동영상 소스 url
- `autoplay`
- `controls`
- `preload`
- `loop`
- `muted`
- `poster`: 동영상 썸네일 이미지 URL
- `width` / `height`: 동영상 가로/세로 너비

<br>
<br>

## `<figure>` / `<figcaption>`

브라우저에게 삽입된 이미지와 그에 관한 설명이 연결되어 있다는 개념을 알려주기 위해 사용되는 태그이다.

- `<figure>`: 이미지나 삽화, 도표 등의 영역을 지정한다.
- `<figcaption>`: `<figure>` 요소가 포함하는 이미지 등의 멀티미디어에 대한 설명을 표시한다.

사용예시

```html
<figure>
  <img src="light.jpg" alt="light image" />
  <figcaption>
    Light is the natural agent that stimulates sight and makes things visible.
  </figcaption>
</figure>
```

<br>
<br>

# 내장 컨텐츠 태그

<br>

## `<iframe>`

중첩 브라우징 맥락을 나타내는 요소로 현재 문서 안에 다른 HTML 페이지를 삽입할 때 사용한다.

#### 속성

- `src`
- `width`(default: 300) / `height`(default: 150)
- `allowfullscreen`: 전체 화면 모드 사용 여부
- `sandbox`: 보안을 위한 추가적인 제약조건을 설정

  - allow-forms: 양식 제출 가능
  - allow-scripts: 스크립트 실행 가능
  - allow-same-origin: 같은 출처(도메인)의 리소스 사용 가능
    > [sandbox 속성 보기](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-sandbox)

<br>

## `<canvas>`

Canvas API이나 WebGL API를 사용하여 그래픽이나 애니메이션을 랜더링할 때 사용한다.

> [MDN Canvas API](https://developer.mozilla.org/ko/docs/Web/HTML/Canvas)

<br>
<br>

# 스크립트 태그

<br>

## `<script>`

스크립트 코드를 문서에 포함하거나 외부 스크립트를 참조할 때 사용하는 태그이다.

#### 속성

- `src` : 스크립트 소스 url
- `type` : [MIME 타입](https://developer.mozilla.org/ko/docs/Web/HTTP/Basics_of_HTTP/MIME_types) 설정
- `async`: 스크립트의 비동기적 실행 여부 (`src` 속성 필수)
- `defer`: 문서 파싱(구문 분석) 후 작동 여부 (`src` 속성 필수)

<br>

> cf) 문서 내 `<script>`위치에 따른 스크립트 파싱과 실행 과정

- `<head>` 태그 내 포함 시
  ![head](../images/html/head.png)

  😡사용자가 웹 사이트를 보는 데까지 많은 시간 소요

- `<body>` 태그 내 포함 시
  ![body](../images/html/body.png)

  😊기본적인 컨텐츠를 빨리 볼 수 있음 <br>
  😡자바스크립트에 의존적인 문서인 경우 정상적인 페이지를 보는데 오래 걸림

- `async` <br>
  html 문서와 js 파일을 병렬적으로 파싱
  ![async](../images/html/async.png)
  😊병렬적으로 파싱하므로 다운로드 시간을 줄일 수 있음<br>
  😡html 파싱 전에 js가 실행되므로 원하는 DOM 요소의 조작에 제약을 받음<br>
  😡정의된 스크립트의 순서에 상관없이 다운로드 순으로 실행되어 실행 순서가 중요한 경우 문제가 될 수 있음

- `defer`
  문서를 파싱하는 동안 필요한 js 파일을 전부 다운받은 후에 순차적으로 실행됨
  ![defer](../images/html/defer.png)
  😊가장 효율적이고 안전함

```html
<iframe
  width="951"
  height="535"
  src="https://www.youtube.com/embed/tJieVCgGzhs"
  frameborder="0"
  allow="accelerometer;encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen
></iframe>
```

---

### References

- [MDN &lt;img&gt;: 이미지 삽입 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/img)
- [MDN 반응형 이미지](https://developer.mozilla.org/ko/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)
- [MDN &lt;audio&gt;](https://developer.mozilla.org/ko/docs/Web/HTML/Element/audio)
- [MDN &lt;video&gt;: 비디오 삽입 요소](https://developer.mozilla.org/ko/docs/Web/HTML/Element/Video)
- [MDN &lt;figure&gt;](https://developer.mozilla.org/ko/docs/Web/HTML/Element/figure)/ [MDN &lt;figcaption&gt;](https://developer.mozilla.org/ko/docs/Web/HTML/Element/figcaption)
- [MDN &lt;iframe&gt;: The Inline Frame element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)
- [HTML IMG의 srcset과 sizes 속성 by heropy](https://heropy.blog/2019/06/16/html-img-srcset-and-sizes/)
