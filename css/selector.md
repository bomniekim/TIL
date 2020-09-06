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

> .app <br> > `class` 값이 app인 요소 선택

<br>

### 4) 아이디 선택자 (ID Selector)

문서 내에서 특정 `id` 값을 가진 요소를 선택한다. <br>
(`id`는 문서 내의 고유한 값으로 지정해야 한다.)

> #app <br> > `id` 값이 app인 요소를 선택

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
  <li>Java</li>
  <!-- Java가 선택됨 -->
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
  <li>Java</li>
  <li>Python</li>
  <!-- Java, Python 선택됨 -->
</ul>
```

<br>
<br>
<br>

## 3. 가상 클래스 선택자(Pseudo-Class Selector)

요소의 특정 상태에 따라 스타일을 정의할 때 사용된다.
특정 상태에는 원래 클래스가 존재하지 않지만 가상 클래스를 임의로 지정하여 선택하는 방법이다.

가상 클래스는 마침표(.) 대신 **콜론(:)을 사용** 한다. CSS 표준에 의해 미리 정의된 이름이 있기 때문에 임의의 이름을 사용할 수 없다.

<br>
<br>

### 3.1. 링크 셀렉터(Link Pseudo-Classes), 동적 셀렉터(User action Pseudo-Classes)

<br>

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
<br>

## 4. 가상 요소 선택자(Pseudo-Elements Selector)

https://poiemaweb.com/css3-selector
