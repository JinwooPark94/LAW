# HTML 태그 정리

## Core Attributes (공통 속성)

### 1. id

고유 한 요소를 식별 하기 위해 사용하며 id에 해당하는 요소를 참조하기 위해 CSS와 Javascript에서 사용가능함

```html
<p id="food">HARIBO</p>
```

### 2. class

여러개 해당하는 요소가 동일한 값을 가질수 있게 하며 css 요소를 참조하는데 사용

```html
<p class="color_Blue">HARIBO</p>
<p class="color_Blue">KEYBOARD</p>
<p class="color_Blue">MOUSE</p>
```

### 3. title

요소에 제목을 추가할 수 있으며 모든 브라우저는 요소가 겹쳐서 표시되거나 포커스가 있을 때 이 속성 값을 표시 

### 4. style

요소에 스타일을 적용할 수 있으며 요소 안에는 CSS 코드를 사용

```html
<p style="background-color: black; color: yellow;">글자색은 노랑이며 백그라운드 색은 블랙<p>
```

> style 요소는 되도록 HTML안에 사용하지 않는 것이 좋으며 직접 .css파일을 추가하여 style을 주는 것이 바람직함 

## Language Attributes (언어 속성)

### 1. dir

`ltr(left to right)`, `rtl(right to left)`로 요소의 텍스트 방향성을 지정

###  2. lang

요소의 내용과 텍스트를 포함하는 요소의 특성에 대한 기본 언어를 지정

## Keyboard Attributes (키보드 속성)

### 1.accesskey

사용자 에이전트에 의해 요소를 활성화시키거나 포커스를 갖게끔 하는 단축키를 생성

```html
<a href="https://jinwoopark94.github.io" accesskey="g">My github homepage</a><br>
<a href="http://jinwoopark.com" accesskey="j">Jinwoo`s homepage</a>
```

#### 각 브라우저 마다 사용 방법

| 브라우저              | 윈도우                                      | 리눅스                         | 맥                             |
| ----------------- | ---------------------------------------- | --------------------------- | ----------------------------- |
| Internet Explorer | [Alt] + *accesskey*                      | N/A                         |                               |
| Chrome            | [Alt] + *accesskey*                      | [Alt] + *accesskey*         | [Control] [Alt] + *accesskey* |
| Firefox           | [Alt] [Shift] + *accesskey*              | [Alt] [Shift] + *accesskey* | [Control] [Alt] + *accesskey* |
| Safari            | [ALT] *+입니다 accesskey*                   | N / A                       | [제어] [ALT] *+입니다 accesskey*   |
| Opera             | Opera 15 이상 : [ALT] *+입니다 accesskey* **Opera 12.1 이상 : [SHIFT] [Esc] 키 *+입니다 accesskey* |                             |                               |

### 2. tabindex

#### 2-1. tabindex="1"

`1`은 문서안에서 가장 먼저 초점을 받을 수 있지만  자연스러운 마크업 순서를 거스르기 때문에 주의해서 사용

#### 2-2. tabindex="0"

`0`은 키보드 초점을 받을 수 없는 `div`, `p`와 같은 요소도 초점을 받을 수 있게 만들어줌

#### 2-3. tabindex="-1"

키보드 초점을 받을 수 있는 요소도 초점을 받을 수 없도록 만들어 줌

> 키보드 접근성에 있어서 중요한 요소!!

참고 : http://naradesign.net/wp/2012/05/10/1786/

## Else Attributes (이외 속성)

### 7. **draggable** 

`true`, `false`로 요소가 드래그 가능한지 여부를 지정

### 8. **spellcheck** 

`true`, `false`로 요소의 내용이 맞춤법 검사 및 문법 검사를 받는 요소를 나타내는 지 여부