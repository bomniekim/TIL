# Transform(변형)

`transform`은 좌표공간을 변형함으로써 일반적인 문서 흐름을 방해하지 않고 콘텐츠의 형태와 위치를 바꾼다.

요소에 이동(`translate`), 회전(`rotate`), 확대축소(`scale`), 비틀기(`skew`) 효과를 부여하기 위한 함수를 지정한다.

단 애니메이션 효과를 제공하지는 않기 때문에 정의된 프로퍼티가 바로 적용되어 화면에 표시된다.<br> 따라서 애니메이션 효과를 부여할 필요가 있다면 `transition`이나 `animation`과 함께 사용해야 한다.

<Br>

## 2D Transfrom

2D transform 은 속성 값으로 변환함수(transform function)를 사용한다. 변환함수는 다음과 같다.

<img src="../images/css/2d-transform.png" width="700">

<br>

### 1) `translate`(이동)

요소를 X축 또는 Y축의 이동 값에 따라 수평/수직으로 재배치한다.

<br>

### 2) `scale`(확대/축소)

요소의 크기를 X축으로 x배, Y축으로 y배 확대 또는 축소 시킨다.

<br>

### 3) `rotate`(회전)

요소를 지정한 각도만큼 회전시킨다.

<br>

### 4) `skew`(비틀기/기울임)

요소를 X축으로 x 각도만큼, Y축으로 y 각도만큼 기울인다.

<br>

> 사용예시

<img src="../images/css/2d-transform-ex.png" width="400">

<br>
<br>

## position vs. translate()

`position` 은 말 그대로, 요소를 특정 지점에 배치하고 끝나는 개념이지만<br>`translate` 은 좌표 공간을 변형하여 다른 요소에 영향을 미치지 않고 위치를 변경할 수 있다.

요소를 특정 위치에 위치시키기 위한 것이 `position` 의 성격인 반면, 움직임이 필요한 모션의 경우는 `translate` 을 지정해야 한다.

즉, `translate` 이 애니메이션에 최적화된 방법!

<img src="../images/css/position-vs-translate.png" width="500">

> 위의 경우는 transform-translate, 아래는 position - top/left 활용 

<br>
<br>

## 3D Transform

3D transform 은 속성 값으로 변환함수(transform function)를 사용한다. 변환함수는 다음과 같다.

<img src="../images/css/3d-transform.png" width="700">

> `transform` 단축 속성에서 여러 변형 함수를 함께 `perspective()` 를 사용하는 경우 __가장 먼저__ 작성해야 적용된다.

<br>
<br>

## `transform` 관련 속성

### 1) `transform-origin`

요소 변환의 기준점을 설정한다.

```css
  transform-origin: x y z;

  /* default : 요소의 정중앙 */
  transform-origin: 50% 50% 0;
```

|값|의미|default|
|---|---|---|
|X축|`left`, `right`, `center`, `%`, 단위|50%|
|Y축|`left`, `right`, `center`, `%`, 단위|50%|
|Z축||0|

<br>

> 다양한 사용예시는 [여기](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin)를 참조.

<Br>


### 2) `transform-style`

3D 변환 요소의 하위 요소도 3D 변환을 사용할 지 설정한다. 

|값|의미|default|
|---|---|---|
|`flat`|하위 요소에 3D 변환을 사용하지 않음|✔︎|
|`preserve-3d`|하위 요소에 3D 변환을 사용함||

<br>

> 다양한 사용예시는 [여기](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-style)를 참조.

<br>

### 3) `perspective`

__하위 요소__ 를 관찰하는 원근 거리를 설정한다. 

### 4) `perspective-origin`

원근 거리의 기준점을 설정한다. 

### 5) `backface-visibility`

3D 변환으로 회전된 요소의 뒷면 숨김을 설정한다.





## 단축 속성
```
  transform: func1, func2, func3 ...;
  transfrom: 원근법 이동 크기 회전 기울임;
```

---
### References
- [translate() vs positioning 비교](https://mygumi.tistory.com/238)