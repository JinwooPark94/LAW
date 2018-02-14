# HTML 태그 정리

## Tables (테이블)

### **`<table>`**

### 1. 정의

데이터를 표의 형태로 나타냄

### 2. 사용

- 요소를 레이아웃 목적으로 사용하면 안됨
- `<table>` 속성은 여러가지가 있지만 MDN에서는 태그 안에 속성을 사용하기 보다는 CSS을 이용한 스타일링 하는 것을 추천 

### 3. **Display**

Block

------

### `<thead>`

### 1. 정의

`<table>`요소의 Header행을 그룹화 하기 위해 지정

### 2. 사용

- `<caption>`, `<colgroup>`, `<col>` 다음에 기술
- 보통 `<tr>` 요소를 포함

### 3. Display

Inline-Block

------

### `<tbody>`

### 1. 정의

`<table>`요소의 데이터행을 그룹화하기 위해 지정

### 2. 사용

- `<caption>`, `<colgroup>`, `<col>`, `<thead>`, `<tfoot>` 다음에 기술

### 3. Display

Inline-Block

------

### `<tfoot>`

### 1. 정의

`<table>`요소의 푸터행을 그룹화하기 위해 지정

### 2. 사용

- 보통 `<tr>`요소를 포함 
- `<caption>`, `<colgroup>`, `<col>` 다음에 기술
- `<thead>` 요소 다음에 `<tbody>` 이전에 기술

### 3. Display

Inline-Block

------

### `<caption>`

### 1. 정의

`<table>`요소의 제목을 지정

### 2. 사용

- `<table>`요소의 바로 다음에 기술
- 테이블의 문맥을 소개하며 쉽게 이해할 수 있도록 함

### 3. Display

Inline-Block

------

### `<colgroup>`

### 1. 정의

`<table>`요소에서 하나 이상의 행의 그룹을 나타냄

### 2. 사용

- `<table>`요소 안에 표의 열을 구조적인 그룹화를 위한 요소
- `<caption>`요소 바로 뒤에 `<thead>`, `<tfoot>`, `<tbody>` 요소 이전에 기술
- `<col>`요소를 포함

### 3. Display

Inline-Block

------

### `<col>`

### 1. 정의

`<colgroup>` 요소에서 하나 이상의 행을 나타냄

### 2. 사용

- 표의 열에 대해 속성값과 스타일 공유를 위한 요소
- `<table>`요소 안의 `<colgroup>`요소 안에서 사용
- `<caption>`요소 바로 뒤에 `<thead>`, `<tfoot>`, `<tbody>` 요소 이전에 기술

### 3. Display

Inline-Block

------

### `<tr>`

### 1. 정의

`<table>` 요소에서 행을 정의

### 2. 사용

- `<tr>`, `<td>` 요소를 포함

### 3. Display

Inline-Block

------

### `<th>` 

### 1. 정의

`<table>` 요소에서 제목 셀을 정의

### 2. 사용

- `<tr>` 요소 아래에 사용해야 함
- `colspan` 속성을 통하여 열 병합을 수로 지정
- `rowspan` 속성을 통하여 행 병합을 수로 지정
- `header` 속성을 통하여 대응하는 헤더셀의 id 컨텐트 속성 값을 지정

### 3. Display

Inline-Block

------

### `<td>`

### 1. 정의

`<table>` 요소에서 데이터 셀을 정의

### 2. 사용

- `<tr>` 요소 아래에 사용해야 함
- `colspan` 속성을 통하여 열 병합을 수로 지정
- `rowspan` 속성을 통하여 행 병합을 수로 지정
- `header` 속성을 통하여 대응하는 헤더셀의 id 컨텐트 속성 값을 지정

### 3. Display

Inline-Block

------

## Images and Image maps (이미지와 이미지 맵)

### `<img />`

### 1. 정의

이미지를 삽입을 위함

### 2. 사용

- `alt` 속성을 통하여 이미지가 url이 잘못되거나 이미지가 표시되지 않는 사용자에게 이미지 대신 텍스트로 표시
- `src` 속성을 통하여 이미지 주소를 나타냄
- `usemap` 속성을 통하여 이미지와 관련된 이미지맵이 있음을 나타냄

### 3. Display

Block

------

### `<map>`

### 1. 정의

`<area>` 요소와 함께 사용되며 이미지 맵을 정의

### 2. 사용

- `<name>` 속성은 필수 속성이며 맵에 이름을 부여하고 참조 할 수 있음
- 이미지에 하나 이상의 영역을 지정하여 각 영역에 링크 설정 가능

### 3. Display

Block

------

### `<area>`

### 1. 정의

`<map>`요소와 함께 사용되며 이미지맵의 영역을 지정

### 2. 사용

- `shape` 속성을 통해 영역의 형태를 지정
  - default : 화면 전체
  - rect : 사각형
  - circle : 원형
  - poly : 다각형


- `coords` 속성을 통해 영역의 좌표를 지정
- `href` 속성을 통해 해당 영역 클릭시 이동할 url 지정
- `alt` 속성을 통해 이미지가 url이 잘못되거나 이미지가 표시되지 않는 사용자에게 이미지 대신 텍스트로 표시

### 3. Display

Inline-Block

------

