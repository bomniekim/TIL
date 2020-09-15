# Transform(변형)

`transform`은 좌표공간을 변형함으로써 일반적인 문서 흐름을 방해하지 않고 콘텐츠의 형태와 위치를 바꾼다.

요소에 이동(`translate`), 회전(`rotate`), 확대축소(`scale`), 비틀기(`skew`) 효과를 부여하기 위한 함수를 지정한다.

단 애니메이션 효과를 제공하지는 않기 때문에 정의된 프로퍼티가 바로 적용되어 화면에 표시된다.<br> 따라서 애니메이션 효과를 부여할 필요가 있다면 `transition`이나 `animation`과 함께 사용해야 한다.

<Br>

## 2D Transfrom

2D transform 은 속성 값으로 변환함수(transform function)를 사용한다. 변환함수는 다음과 같다.

<img src="../images/css/2d-transform.png" width="700">

<br>
<br>

### 1) `translate`

요소를 X축 또는 Y축의 이동 값에 따라 수평/수직으로 재배치한다.

## 3D Transform

<br>
<br>

## 단축 속성
```
  transform: func1, func2, func3 ...;
  transfrom: 원근법 이동 크기 회전 기울임;
```