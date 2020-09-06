# 선택자(Selector)

**선택자(selector)** 란 웹 페이지의 HTML 요소를 대상으로 스타일을 지정할 하기 위해 사용된다.
<br>복수 개의 셀렉터를 연속하여 지정할 수 있으며 쉼표( , )로 구분한다.

<br>
<br>

## 1. 기본 선택자

<br>

### 1) 전체 선택자 (Universal Selector)

문서 내부의 모든 요소를 선택한다.

> \* (Asterisk)

<br>

### 2) 태그 선택자 (Type Selector)

특정 태그를 선택한다.

> span

<br>

### 3) 클래스 선택자 (Class Selector)

문서 내에서 특정 `class`값을 가진 요소(들)를 선택한다.

> **.app** <br> > `class` 값이 app인 요소 선택

<br>

### 4) 아이디 선택자 (ID Selector)

문서 내에서 특정 `id` 값을 가진 요소를 선택한다. <br>
(`id`는 문서 내의 고유한 값으로 지정해야 한다.)

> **#app** <br> > `id` 값이 app인 요소를 선택

<br>
<br>
<br>

## 2. 복합 선택자(Combinators)

<br>

### 1) 일치 선택자(Basic Combinator)

조건을 동시에 만족하는 요소를 선택한다.

> **span.app**<br>> `<span>`이면서 `class` 값이 app인 요소 선택

<br>

### 2) 자식 선택자(Child Combinator)

부모를 기준으로 특정한 자식 요소를 선택한다.

> **div > ul**<br>> div의 자식 요소 `<ul>`을 선택

<br>

### 3) 후손(하위) 선택자(Descendant Combinator)

특정 선택자를 기준으로 그 후손(하위) 요소를 선택한다.
<br> _띄어쓰기_ 가 선택자의 기호로 사용된다.

> **span .app**<br>> span의 하위 `class` 중 값이 app인 요소를 선택 (span은 조건일 뿐!)

<br>

### 4) 인접 형제 선택자(Adjacent Sibling Combinator)

특정 선택자의 다음 형제 요소 하나만 선택한다.

> **.app + li**

```html
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li class="app">JS</li>
  <li>Java</li> <!--선택-->
</ul>
```

<br>

### 5) 일반 형제 선택자(General Sibling Combinator)

특정 선택자의 다음 모든 형제 요소를 선택한다.

> **.app ~ li**

```html
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li class="app">JS</li>
  <li>Java</li> <!--선택-->
  <li>Python</li> <!--선택-->
</ul>
```

<br>
<br>
<br>

## 3. 가상 클래스 선택자(Pseudo-Class Selector)

요소의 특정 상태에 따라 스타일을 정의할 때 사용된다.
특정 상태에는 원래 클래스가 존재하지 않지만 가상 클래스를 임의로 지정하여 선택하는 방법이다. <br>
가상 클래스는 마침표(.) 대신 **콜론(:)을 사용** 한다. CSS 표준에 의해 미리 정의된 이름이 있기 때문에 임의의 이름을 사용할 수 없다.

<br>

### 3.1. 링크 가상 클래스(Link Pseudo-Class), 동적 가상 클래스(User action Pseudo-Class)

### 1) hover

> **a:hover**<br>> `a`에 마우스(포인터)가 올라가 있는 동안만 선택

### 2) active

> **a:active**<br>> `a`를 마우스로 클릭하는 동안에만 선택

### 3) focus

> **input:focus**<br>> `input`이 포커스 되어있는 동안에만 선택<br> [대화형 콘텐츠](https://developer.mozilla.org/ko/docs/Web/Guide/HTML/Content_categories#%EB%8C%80%ED%99%94%ED%98%95_%EC%BD%98%ED%85%90%EC%B8%A0)에서 사용 가능

### 4) link, visited

> **a:link**<br>> `a`가 방문하지 않은 링크일 때 <br> > **a:visited**<br>> `a`가 방문한 링크일 때

<br>
<br>

### 3.2. 구조 가상 클래스 (Structural Pseudo-Class)

### 1) first-child

> **p:first-child** <br>> `p`가 형제 요소 중 첫번째 요소라면 선택

### 2) last-child

> **p:last-child** <br>> `p`가 형제 요소 중 마지막 요소라면 선택

### 3) nth-child

> **p:nth-child(n)** <br>> `p`가 형제 요소 중 n번째 요소라면 선택<br>**(`n` 키워드 사용 시 `0`부터 해석한다.(Zero-base))**

<br>

[사용예시 1]
```css
.app li:nth-child(2) {
  color: tomato;
}
```

```html
<ul class="app">
  <li>HTML</li>
  <li>CSS</li> <!-- 선택 -->
  <li>JavaScript</li>
</ul>
```
<br>

[사용예시 2]
```css
.app li:nth-child(2n+1) {
  color: tomato;
  /* n 키워드 사용 시 0부터 시작하여 1,3 */
}
```

```html
<ul class="app">
  <li>HTML</li> <!-- 선택 -->
  <li>CSS</li> 
  <li>JavaScript</li> <!-- 선택 -->
  <li>Java</li> 
</ul>
```
<br>

[사용예시 3]
```css
.app p:nth-child(1) {
  color: tomato;
  /* n 키워드 사용 시 0부터 시작하여 1,3 */
}
```

```html
<!-- 선택된 요소 없음 -->
<div class="app">
  <span>HTML</span> 
  <p>CSS</p> 
  <p>JavaScript</p>
  <span>Java</span> 
</ul>
```
> .app의 첫번째 자식 요소가 `p`가 아니기 때문에 선택되는 요소가 없음

<br>

### 4) nth-of-type

요소의 타입(태그이름)과 동일한 타입인 형제 요소 중 해당 요소가 n번째 요소라면 선택한다.


> **p:nth-of-type(2)** <br>> 형제 요소 중 2번째 `p`요소를 선택<br>**(`n` 키워드 사용 시 `0`부터 해석한다.(Zero-base))**

<br>

[사용예시 1]
```css
.app p:nth-of-type(2) {
  color: tomato;
}
```

```html
<div class="app">
  <div>HTML</div> 
  <p>CSS</p> 
  <p>JavaScript</p> <!--선택-->
  <span>Java</span> 
</ul>
```

<br>

[사용예시 2]
```css
.app .red:nth-of-type(1) {
  color: red;
}
```

```html
<!-- 선택된 요소 없음 -->
<ul class="app">
  <li>HTML</li> 
  <li class="red">CSS</li> 
  <li>JavaScript</li> 
  <li class="red">Java</li> 
</ul>
```
> 첫번째 자식 요소의 `class`가 red가 아니기 때문에 선택되는 요소가 없음

> cf) first-of-type, last-of-type, nth-last-of-type(n)

<br>

### 5) 부정 선택자(Negation Pseudo-Class)

해당하지 않는 모든 요소를 선택한다.

> __li:not(.app)__<br>> `li`중에 `class`가 app이 아닌 모든 요소를 선택

<br>
<br>
<br>

## 4. 가상 요소 선택자(Pseudo-Elements Selector)

요소의 특정 부분에 스타일을 적용하기 위하여 사용된다.<br>가상 요소에는 __두개의 콜론(::)__ 을 사용한다. CSS 표준에 의해 미리 정의된 이름이 있기 때문에 임의의 이름을 사용할 수 없다.

<br>

### 1) before

> __li::before__ <br> > li 요소 __내부의 앞__ 에, 내용(content)을 삽입

### 2) after
> __li::after <br> > li 요소 __내부의 뒤__ 에, 내용(content)을 삽입

```css
div::before {
 content: "<";
 color: tomato;
}

div::after {
 content: ">";
 color: tomato;
}
```
```html
<div>tag</div>
```

<img src="../images/css/tag.png" width="150">

<br>
<br>
<br>
<br>

## 5. 속성 선택자(Attribute Selector)

지정된 어트리뷰트를 갖는 모든 요소를 선택한다.

### 1) attr
> __a[href]__  <br>> `a` 요소 중에 `href` 속성을 갖는 모든 요소를 선택\.

<br>

### 2) attr=value
> __a[target="_blank"]__  <br>> `a` 요소 중에 `target` 속성 값이 "_blank"인 모든 요소를 선택.

<br>

### 3) attr^=value
> __p[class^="btn-"]__  <br>> `p` 요소 중에 `class` 속성 값이 "btn-"로 시작하는 모든 요소를 선택.

<br>

### 4) attr$=value
> __p[class$="app"]__  <br>> `p` 요소 중에 `class` 속성 값이 "app"으로 끝나는 모든 요소를 선택.

<br>

### 5) attr~=value
지정된 속성의 값이 지정된 value를 __(공백으로 분리된) 단어__ 로 포함하는 요소를 선택한다.
> __h1[title~="first"]__  <br>> `h1` 요소 중에 `title` 속성 값에 "first"를 단어로 포함하는 모든 요소를 선택.

```css
h1[title~="first"] {
  color: tomato;
}
```
```html
<h1 title="heading first">Heading first</h1> <!--선택-->
<h1 title="heading-first">Heading-first</h1>
<h1 title="heading second">Heading second</h1>
```

<br>

### 6) attr|=value
지정된 속성의 값과 일치하거나 지정 속성 값 뒤 연이은 하이픈(“값-“)으로 시작하는 요소를 선택한다.
> __p[lang|="en"]__<br>>  `p` 요소 중에 `lang` 값이 "en"과 일치하거나 "en-"로 시작하는 요소를 선택

```css
p[lang|="en"] {
  color: blue;
}
```
```html
<p lang="en">Hello!</p> <!--선택-->
<p lang="en-us">Hi!</p> <!--선택-->
<p lang="ko">안녕!</p>
<p lang="us">Hi!</p>
```

<br>

### 7) attr*=value
지정된 속성 값을 포함하는 요소를 선택한다.
> __div[class*="test"]__<br>> `div` 중에서 `class` 값에 "test"를 포함하는 요소를 선택

```css
div[class*="test"] {
  color: blue;
}
```
```html
<div class="first_test">div1</div> <!--선택-->
<div class="second">div2</div>
<div class="test">div3</div> <!--선택-->
<p class="test">p1</p>
```

<br>





---
### References
https://poiemaweb.com/css3-selector
