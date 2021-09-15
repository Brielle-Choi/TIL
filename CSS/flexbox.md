## Container - flex-direction
  1. 주축의 위치
    - vertical
    - horizon

  2. 주축의 방향
    - 정방향
    - 역방향

- 값
  - row : 주축의 시작점과 끝점이 콘텐츠 방향과 동일하며 기본값
  - row-reverse : 시작점과 끝점이 반대에 위치
  - column : 주축이 블록 축과 동일 (세로 방향)
  - column-reverse : column과 방향 반대로

    ```css
    .container {
      height: 500px;
      border: 5px dashed orange;
      display: flex;
      flex-direction: column;
    }

    .item {
      width: 50px;
      height: 50px;
      margin: 5px;
      background-color: paleturquoise;
      border: 3px solid blue;

    }
    ```
## Container - flex-wrap, flex-flow (shorthand)

- flex-wrap
  - flex-item 요소들이 강제로 한줄에 배치되게 할 것인지 , 또는 가능한 영역 내에서 벗어나지 않고 여러행으로 나누어 표현 할 것인지 결정하는 속성
  - 값
    - nowrap : 기본값이며 flex-item을 한 줄에 배치
    - wrap : flex-item 요소들이 내부 로직에 의해 분할되어 여러 행에 걸쳐서 배치, 일반적으로 위에서 아래로 쌓이는 순서
    - wrap-reverse : wrpa의 요소가 나열되는 시작점과 끝점의 기준이 반대로 배치
  - 자기의 본래 크기 속성을 지킬 수 있음
- flex-flow
  - flex-direction과 flex-wrap을 같이 쓸 수 있는 단축 속성


## Item - order
- 단일 item에서 사용하는 속성
- 플렉스 또는 그리드 컨테이너 안에서 현재 요소의 배치 순서를 지정
- 기본 값: 0
- 아이템의 정렬 순서를 바꿀 수 있고 아이템의 정렬 순서는 오름차순(정수 사용)

  ```css
  .container {
    height: 200px;
    border: 5px dashed orange;
    display: flex;
    flex-flow: row wrap;
  }
    /* item 속성을 사용하려면 container(부모요소)에 display:flex가 설정이 되있어야 함 */

  .item {
    width: 50px;
    height: 50px;
    margin: 5px;
    background-color: paleturquoise;
    border: 3px solid blue;
  }

  .item:nth-child(3) {
    order: -1;
  }
  .item:nth-child(4) {
    order: 8;
  }
  .item:nth-child(5) {
    order: 2;
  }
  ```

## Item - flex-grow
  
  - 수용이 가능한 공간이 남았다면 아이템끼리 나누어 사용할 수 있음
  - 만약 형제 요소로 렌더링 된 모든 flex-item 요소들이 동일한 flex-grow 값을 가진다면 flex-container 내부에서 동일한 공간을 할당 받음
  - 형제 요소들이 각기 다른 flex-grow 값을 가진다면 그에따라 다른 공간값을 갖음
  - item의 크기가 container의 크기보다 작아야 함
  - 기본값 : 0
  - 음수 값은 사용할 수 없음

    ```css
    .item:nth-child(3) {
      order: -1;
      flex-grow: 1;
    }

    .item:nth-child(4) {
      order: -1;
      flex-grow: 2;
    }

    .item:nth-child(1) {
      order: -1;
      flex-grow: 4;
    }

## Item - flex-shrink

  - flex-item 요소의 크기가 flex-container 요소의 크기보다 커야함
  - 기본값 :1
  - 음수는 안됨
  - 줄어든 영역을 item 요소들끼리 값에 따라 나누어 줄어든다
  
      ```css
      .item:nth-child(1) {
      flex-shrink: 0;
    }
    .item:nth-child(2) {
      flex-shrink: 1;
    }
    .item:nth-child(3) {
      flex-shrink: 2;
    }
    ```

## Item - flex-basis

- flex-item의 초기 크기를 지정
- flelx-basis의 값을 0으로 설정하면 flex-grow나 flex-shrink의 정확한 비율 값을 알 수 있음
- 기본값 : auto

  ```css
  .item {
  width: 200px;
  height: 50px;
  margin: 5px;
  background-color: paleturquoise;
  border: 3px solid blue;
  flex-basis: 0;
  }

  .item:nth-child(1) {
    flex-grow: 5;
  }
  .item:nth-child(2) {
    flex-grow: 1;
  }
  .item:nth-child(3) {
    flex-grow: 3;
  }
  ```

## Item- flex(shorthand)

- flex-grow, flex-shrink, flex-bais의 단축 속성
- 값이 한 개 일 때,
  - &lt;number&gt;를 지정하면 그 값은 flex-grow의 값
  - &lt;length&gt; 또는 &lt;percentage&gt;를 지정하면 flex-basis가 됨
  - none, auto, initial과 같이 키워드를 사용할 수 있음
- 값이 두 개일 때
  - 첫 번째 값은 무조건 &lt;number&gt;여야 하며 flex-grow가 된다
  - 두 번째 값은 &lt;number&gt; 지정하면 flex-shrink이며, &lt;length&gt;나 &lt;percentage&gt; 또는 auto를 지정하면 flex-basis이다.
- 한 개 또는 두개의 단위 없는 숫자 값을 사용할 때, flex-basis의 값은 auto가 아니라 0이 됨
- 값이 세 개일 경우 :
  - flex-grow flex-shink flex-basis 순서로 사용
- flex: initial는 flex: 0 1 auto 와 동일
- flex: auto 는 flex: 1 1 auto 와 동일
- flex: none 은 flex: 0 0 auto 와 동일

## Container- justify-content

- 주축을 중심으로 아이템을 어떻게 정렬할 것인가 , 주축의 시작점인지 끝점인지를 잘 봐야 함
- flex-direction의 값에 따라 달라짐
- 값
  - flex-start
  - flex-end
  - center
  - space-between : 첫 flex-item과 마지막 flex-item이 container 끝 쪽으로 붙음
  - space-around : 첫 flex-item과 마지막 flex-item이 container 사이에 공간이 다른 flex-item 사이의 공간만큼 있음

    ```css
      .container {
      height: 200px;
      border: 5px dashed orange;
      display: flex; 
      flex-direction: row; 
    }
      

    .item {
      width: 200px;
      height: 50px;
      margin: 5px;
      background-color: paleturquoise;
      border: 3px solid blue;
      }
    .container:nth-child(1) {
      justify-content: space-between;
    }
    .container:nth-child(2) {
      justify-content: space-around;
    }
    ```

## Container - align-items

- flex(한 줄)가 전체 container에서 어디다 둘 지에 대한 설정
- space-between과 space-around 사용 가능하지 않음

## Container - align-content

- 여러 줄의 flex에 대한 정렬
- space-between과 space-around 사용 가능

  ```css
  .container:nth-child(1) {
  
  align-items: space-between;
  }
  ```

## Item - align-self

- 한 가지 아이템에만 정렬을 따로 적용하고 싶을 때 사용

  ```css
    .container:nth-child(1) {
    
    align-items: center;
  }


  .item:nth-child(4) {
    align-self: flex-start;
  }

    /* 4번 째 아이템만 정렬 다름; 위 align-items: center은 무시하게 됨 */
  
  ```







