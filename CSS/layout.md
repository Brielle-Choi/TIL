## display -inline, block, inline-block

- inline 요소 : ex) span
  - 영역의 크기가 내부 콘텐츠 크기로 정해진다
  - margin, padding의 top/bottom의 여백을 지정할 수 없다
  - 여러 요소가 가로 배치가 된다

- blcok 요소 : ex) div
  - 영역의 크기를 width, height 지정할 수 있다
  - width를 지정하지 않으면 가로 전체를 차지한다
  - 여러 요소가 세로 배치가 된다

- Inline-block 요소 : ex) input
  - 영역의 크기를 width, height 지정할 수 있다
  - 여러 요소가 가로 배치가 된다

  ```css
  span {
    display: inline-block;
    width: 100px;
    height: 40px;

  }
  ```

## 요소를 없애는 방법 - dispaly: none, visibility: hidden

- display: none은  아예 요소를 레이아웃에서 사라지게 됨
- visibility는 문서의 레이아웃을 변경하지 않고 요소를 보이거나 숨김
  - 기본값 : visible
  - 값이 hidden을 주면 레이아웃에는 숨겨지지 않지만 요소가 숨겨짐

## float
- 한 요소가 보통 흐름으로부터 빠져 텍스트 및 인라인 요소가 그 주위를 감싸는 자기 컨테이너의 좌우측을 따라 배치되어야 함을 지정 (block이나 inline의 기존의 계산 방법을 무시하고 별도의 flow를 가짐)
- 기본값 : none
- 다른 값: left, right

## position과 Normal Flow

- position: 문서 상에 요소를 배치하는 방법을 지정
  - 기본값 : static (normal flow)
- normal flow : 요소의 레이아웃을 변경하지 않을 시 배치하는 방법 

## position - relative

-  요소를 일반적인 문서 흐름(normal flow)에 따라 배치하고, 자기 자신(position이 static일 때)을 기준으로  top, right, bottom, left의 값에 따라 오프셋을 적용

```css
 #box {
   position: relative;
   top: 50px;
   left: -80px;
 }
 /* position이 static일 때 top, bottom, left, right 속성을 사용할 수 없음; relative 일 때 top , bottom을 같이 설정하면 bottom 속성이 무시됨, left, right도 상동 */
 ```

## position - absolute

- 요소를 일반적안 문서 흐름(noraml flow)에서 제거하고, 페이지 레이아웃에 공간도 배정하지 않음; 대신 가장 가까운 위치 지정 조상 요소에 대해 상대적으로 배치
- 조상 중에서 position이 static이 아닌 요소를 찾아 기준점을 삼음
- 조상 중 그런 요소가 없다면 초기 컨텡이닝 블록(body)을 기준으로 삼음

```css
  #parent {
    position: relative;

  /* child의 부모 요소인 parent의 position이 static이 아닌 relative이므로 parent를 기준으로 배치 */

  #child {

    position : absolute;
    top: 100px;
    left: 20px;
  }
```

## position - fixed

- 요소를 일반적인 문서 흐름에서 제거
- 페이지 레이아웃에 공간도 배정하지 않음
- 뷰포트의 초기 컨테이닝 블록을 기준으로 삼아 배치
- 스크롤을 따라 위치가 변하지 않고 고정됨

  ```css
  #box {
    position: fixed;
    bottom: 40px;
    right: 40px;
  }
  ```

## position - sticky

- 요소를 일반적인 문서 흐름에 따라 배치
- 테이블 관련 요소를 포함해 가장 가까운 스크롤 되는 조상과 표 관련 요소를 포함한 컨테이닝 블록을 기준으로 top, right, bottom, left의 값에 따라 오프셋을 적용
- 어느순간에 걸려서 동작을 하지 않음
- 스크롤 되는 조상의 하위에 설정해야 동작이 됨

## overflow

- 요소의 콘텐츠가 너무 커서 요소의 블록 서식 맥락에 맞출 수 없을 때 처리법
- 기본값 : visible
- 다른 값 : hidden, scroll, auto

## z-index

- z축의 순서를 지정
- 기본값 : auto
- 다른 값: 정수
- 기본적인 쌓임 순서: position이 static인 요소들이 아닌 요소들보다 뒤에 있음
- 크기가 클수록 화면에 가깝게 출력
 



