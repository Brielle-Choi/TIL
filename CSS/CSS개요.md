## CSS는 어떻게 생겼을까
- CSS는 룰기반(rule-based)의 언어
- CSS를 통해 특정 요소, 혹은 특정 요소들의 집합의 스타일 규칙을 정의할 수 있음
  - 선택자(Selector): 스타일을 지정할 HTML 요소를 선택
  - 선언블록(declaration block): 중괄호 {}내부의 여러 선언들을 작성
  - 선언(declaration) : 속성과 값으로 이루어진 쌍
  - 선택자 {하나 이상의 선언}의 형태로 이루어진 하나의 Rule(혹은 Rule set)
  - 주석 : /* 내용 */
- CSS 적용방법
  - 내부스타일(embeded) : 전체 html &lt;style&gt;요소를 적용, &lt;head&gt;태그에 사용
  - 인라인 스타일(inline) : 딱 하나의 요소에만 적용, style 속성 사용
  - 외부스타일(external) : css 파일을 따로 만들어 &lt;link&gt; 요소를 사용

## 캐스캐이딩 원칙
- 스타일 우선순위
  - 동일한 스타일이라도 선언된 곳에 따라 우선순위가 정해진다.
    - 브라우저에 의해 정의된 스타일 < 개발자가 선언한 스타일 < 사용자가 구성하는 스타일
  - 적용 범위가 적을수록 우선시 된다.
    - tag스타일 < class스타일 < id스타일 <인라인 스타일
  - 소스 코드의 순서가 뒤에 있으면 덮어쓴다.
- 스타일 상속
  - 부모 요소에 있는 스타일 속성들이 자식 요소로 전달된다.
    - 자식 요소에서 재 정의할 경우, 부모의 스타일을 덮어쓴다.
    - 상속이 되지 않는 속성도 있다.(예: 배경 이미지, 배경 색 등)

