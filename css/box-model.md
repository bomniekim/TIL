# 박스 모델(Box Model)

모든 HTML 요소는 Box 형태의 영역을 가지고 있다. 이 Box는 콘텐트(Content), 패딩(Padding), 테두리(Border), 마진(Margin)로 구성된다.

<img src="../images/css/box-model.png" width="600">

브라우저는 박스 모델의 크기(dimension)와 프로퍼티(색, 배경, 모양 등), 위치를 근거로 하여 렌더링을 실행한다.

<br>
<br>

## `content`

요소의 텍스트나 이미지 등의 실제 내용이 위치하는 영역이다. `width`, `height`를 갖는다.

### 1) width
> 요소의 너비

|값|의미|default|
|---|---|---|
|`auto`|브라우저가 너비를 계산|`auto`|
|단위|`px`, `em`, `%` 등||
