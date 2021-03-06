# HTML 태그 정리

## List Markup (리스트 마크업)

| **태그** | **정의**                              | **사용**                                   | **Display**  |
| ------ | ----------------------------------- | ---------------------------------------- | ------------ |
| `<ol>` | 순서가 있는 목록을 나타냄                      | - 보통 `<li>`요소를 포함하고 있고 `<li>`의 value 속성 값을 통해 목록 아이템의 순번을 지정<br />- reversed, start, type의 속성들이 있음<br />- 브라우저에서 자동으로 아라비아 숫자로 표현 | Inline-Block |
| `<ul>` | 순서가 중요하지 않은 목록을 나타냄                 | - 보통 `<li>`요소를 포함하고 있음<br />- 브라우저에서 자동으로 블릿으로 표현 | Block        |
| `<li>` | 목록을 나타냄                             | - 부모가 `<ol>`이면 순서가 있는 값을 가지고, 부모가 `<ul>`이면 순서가 없는 값을 가짐 | lnline-Block |
| `<dl>` | 용어, 설명 그룹에서 설명, 정의, 값을 나타냄          | - 용어를 정의 하는 `<dt>`요소와 용어를 설명하는 `<dd>`요소를 포함 | Block        |
| `<dt>` | `<dl>`요소의 용어, 설명 그룹에서 용어나 이름을 나타냄   | - `<dl>`의 하부 요소로  용어를 설명하는 `<dd>`요소와 함께 사용 | Inline-Block |
| `<dd>` | `<dl>`요소의 용어, 성명 그룹에서 설명, 정의 값을 나타냄 | - `<dl>`의 하부 요소로 정의된 용어 `<dt>`에 대한 설명과 함께 사용 | Inline-Block |

## Forms Markup (폼 마크업)

| **태그**       | **정의**                                   | **사용**                                   | **Display**  |
| ------------ | ---------------------------------------- | ---------------------------------------- | ------------ |
| `<form>`     | section에 기술된 다른 HTML 요소의 모든 프로퍼티와 메소드 공유 | - `action`속성을 통해 필드 내용을 보낼 URL 지정<br />- `method`속성을 통해 폼을 post 또는 get 방식으로 처리<br />- `name`속성을 통해 링크나 스크립트를 통해 이 폼을 참조할 수 있게 식별자 지정 | Block        |
| `<fieldset>` | 여러개의 콘트롤과 라벨을 그룹화함                       | - `disabled`속성을 통해 첫번째 `legend`요소를 제외한 모든 자식 요소를 비활성화 시킴<br />- `form` 속성을 통해 다른 폼 소유자와 명시적으로 연관<br />- `name`속성을 통해 요소의 이름을 지정<br />- `legend`요소를 이용해 캡션 부여 가능<br />- 중첩하여 사용 가능 | Inline-Block |
| `<legend>`   | `<fieldset>`요소를 이용하여 그룹화한 범위의 설명         | - 전역 속성만 포함                              | Inline-Block |
| `<label>`    | 사용자 인터페이스에 대한 설명                         | - `label` 요소의 범위에 텍스트와 컨트롤을 포함<br />- `for` 속성을 통하여 폼 컨트롤의 `id`속성과 같은 값을 지정하여 동기화를 목적으로 함 | Inline-Block |
| `<input>`    | 폼 안에 기본적인 컨트롤 생성                         | - `type` 필수 속성이며 여러가지 타입을 지정 가능<br />`type="text"` : 텍스트 입력필드<br />`type="password"` : 비밀번호 입력필드(값이 " * "로 가려짐)<br />`type="checkbox"` : 체크박스 생성 (복수 선택 가능)<br />`type="radio"` : 라디오버튼 생성 (복수 선택 불가능)<br />`type="submit"` : 송신버튼 생성<br />`type="reset"` : 리셋버튼 생성<br />`type="button"` : 범용버튼 생성<br />`type="image"` : 이미지버튼 생성<br />`type="file"` : 파일올리기 위한 버튼 생성<br />`type="hidden"` : 보여지지 않는 필드 생성<br />- `name` 속성을 통하여 `input` 이름 지정<br />- `value` 속성을 통하여 `input` 초기값 지정<br />- `max` 속성을 통하여 `input` 허용하는 값의 최대값 지정<br />- `min` 속성을 통하여  `input` 허용하는 값의 최소값 지정<br />- `maxlength` 속성을 통하여 `input` 의 최대 입력 문자수 지정<br />- `placeholder` 속성을 통하여 사용자가 데이터를 입력하는데 힌트 지정 | Block        |
| `<select>`   | 선택목록 생성                                  | - `autofocus` 속성을 통하여 페이지를 로드할때 자동 포커스 지정<br />- `disabled` 속성을 통하여 모든 조작이 불가능하게 하여 데이터를 서버에 전송 하지 않음<br />- `form` 속성을 통하여 다른 폼 소유자와 명시적으로 연관시키기 위해 사용<br />- `multiple` 속성을 통하여 복수 선택 가능<br />- `required` 속성을 통하여 필수 요소인지 지정<br />- `size` 속성을 통하여 제공할 목록 갯수 지정<br />- `name` 속성을 통하여 식별자 지정<br />- 한개 이상의 `option`요소를 포함하고 있어야 함<br />- `optgroup`  요소를 통해 항목 그룹화 가능 | Block        |
| `<optgroup>` | `<select>`요소의 자식 요소이며 `option`요소로 이루어진 항목 | - `disabled` 속성을 통하여 요소 모두를 비활성화 시킴<br />- `label` 속성을 통하여 라벨을 지정(필수)<br />-  동일한 레이블을 가진 옵션 요소들의 그룹<br />- `option` 요소를 자식으로 가짐 | Block        |
| `<option>`   | `<select>` 요소의 자식 요소로 각 항목을 정의           | -  `disabled` 속성을 통하여 옵션 요소를 비활성화 시킴<br />- `label` 속성을 통하여 라벨을 지정<br />- `selected` 속성을 통하여 기본으로 선택된 상태를 지정<br />- `value` 속성을 통하여 선택 되었을때 값을 서버로 보냄<br />- `<optgroup>`을 이용하여 그룹핑 가능 | Inline-Block |
| `<textarea>` | 여러줄의 텍스트를 편집할 수 있는 컨트롤 생성                | - `autofocus` 속성을 통하여 페이지 로드시 자동 포커스를 받도록 지정<br />- `cols` 속성을 통하여 표시될 폭을 문자수로 지정<br />- `rows` 속성을 통하여 표시될 줄 수 지정<br />- `name` 속성을 통하여 식별자 지정<br />- `disabled` 속성을 통하여 선택, 변경 불가능하게 하며 데이터가 서버에 전송 되지 않음<br />- `form` 속성을 통하여 다른 폼 소유자와 명시적으로 연관시키기위해 사용<br />- `maxlength` 속성을 통하여 속성을 통하여 최대 입력 문자수 지정<br />- `placeholder` 속성을 통하여 사용자가 데이터를 입력하는데 힌트 지정<br />- `readonly` 속성을 통하여 컨트롤 조작 불가능 상태로 만드며 데이터는 서버에 전송함<br />- `required` 속성을 통하여 필수요소인지 지정 | Block        |
| `<button>`   | 버튼 생성                                    | - `autofocus` 속성을 통해 페이지 로드시 자동 포커스를 받도록 지정<br />- `disabled` 선택, 변경 등 조작이 불가능하며 데이터도 서버에 전송되지 않음<br />- `name` 속성을 통하여 식별자 지정<br />- `type` 속성을 통하여 버튼의 종류 지정 가능<br />`type="submit"` : 폼을 제출<br />`type="reset"` : 폼을 리셋<br />`type="button"` : 아무것도 하지 않음<br />`value` 속성을 통하여 전송되는 데이터 값 지정<br />- `input` 요소로 생성하는 버튼과 같지만 이미지나 텍스트등을 포함해 유연한 디자인 가능 | Block        |

### 

