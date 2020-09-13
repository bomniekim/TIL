# Stacking Context (쌓임 맥락)


## Stacking Context

Stacking Context 는 가상의 `z-index`을 사용한 HTML 요소의 3차원 개념화이다. <Br>
요소들이 서로 겹치는 경우 쌓여있는 순서(stacking order)를 통해 어떤 요소가 사용자와 더 가깝게 있는지(더 위에 쌓여있는지)를 결정한다. 

<br>

## `z-index`

`z-index` 는 요소의 쌓임 순서를 지정하는 속성으로 하나의 정수(양수/음수 모두 가능) 값을 가진다.<Br>요소에 __`position` 속성을 필수로 지정한 후__ `z-index` 속성을 지정해야 작동하며 속성의 값이 클수록 사용자와 가까운 곳에 위치한다. 

<img src="../images/css/x-y-z.png" width="600">

<br>
<br>

## When is a stacking context formed?

stacking context 는 문서 어디에서나, 다음 조건 등을 만족하는 요소가 생성합니다.

- 문서의 최상위 요소 (`<html>`)

- position 속성이 지정된 요소 중 `static` 이 아니면서 `z-index`가 auto가 아닌 요소
- `flexbox`의 자식 요소 중 z-index가 auto가 아닌 요소
- `grid` 의 자식 요소 중 z-index가 auto가 아닌 요소
- `opacity`가 1보다 작은 요소
- 다음 속성 중 하나라도 `none`이 아닌 값을 가진 요소.
    - `transform`
    - `filter`
    - `perspective`
    - `clip-path`
    - `mask` / `mask-image` / `mask-border`

> 더 많은 조건은 [여기](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context#%EC%8C%93%EC%9E%84_%EB%A7%A5%EB%9D%BD)를 참조.

<br>
<br>

## Stacking Order

1. `static` 을 제외한 `position` 속성의 값이 있을 경우 가장 위에 쌓인다. (값은 무관)
2. 모든 요소에 `position` 이 존재한다면, `z-index` 속성의 숫자 값이 높을수록 위에 쌓인다.
3. `position` 속성의 값이 있고, `z-index` 속성의 숫자 값이 같다면, HTML의 마지막 코드(가장 나중에 작성한 코드(요소))일수록 위에 쌓인다.

```
position > z-index > html 마지막 코드
```
<img src="../images/css/stacking-order.png">

<Br>
<Br>
---
### References
- [stacking context via MDN](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context)
- [z-index via MDN](https://developer.mozilla.org/ko/docs/Web/CSS/z-index)
- [z-index 적용 via MDN](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Positioning/Understanding_z_index/Adding_z-index)
- [z-index via codrops](https://tympanus.net/codrops/css_reference/z-index/)
- https://liyulinnyu.github.io/techpages/stackingorder.html