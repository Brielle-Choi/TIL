# Box Model

- content : 콘텐츠가 표시되는 영역
  - width, height의 크기를 가짐
- padding : 콘텐츠와 테두리(border) 사이의 여백
- border : padding과 margin 사이의 테두리
  - 기본값 : 0
- margin :  가장 바깥 쪽 레이어로 콘텐츠와 패딩, 테두리를 둘러 
싸면서 해당 박스와 다른 요소 사이 공백 역할

## width, height

- width : 요소의 너비를 설정
  - 기본값 : auto - blcok일 경우 100%로 차지할 수 있는 전부를 차지, inline일 경우 width의 값이 적용되지 않음.
  - 상속이 되지 않음
- height : 요소의 높이를 결정
   - 기본값 : auto, 컨텐츠의 높이 만큼  차지, 위와 상동

## max-width, min-width, max-height, min-height

 - 기본값 : auto
 - 상속이 되지 않음
 - 부모요소의 가로, 세로 길이에 따라서 더이상 줄어들거나 늘어나지 않게 하는 속성

  ```css
  .container {
    width: 50%;
    min-width: 300px;
    height: 300px;
    
    background-color: lightcoral;
  }
  ```

## margin

- 단축 속성 : margin-top, marin-right, margin-bottom, margin-left
- 기본값 : 0
- 상속이 안됨
  ```css
  /*여기서 10px는 상하, 20px는 좌우에 적용됨 */
  .child {
  margin: 1opx 20px;
  }
  ```


- percentage를 margin의 단위로 사용시 부모요소 width의 값을 기준으로 설정

## margin collapsing

- 마진 상쇄, 마진 겹침, 마진 중복 등으로 불림
- 여러 블록 요소들의 위/아래 margin이 경우에 따라 가장 큰 크기를 가진 margin으로 결합(상쇄)되는 현상
- 인접 형제일 경우
  - 두 형재요소의 위/아래 여백이 만나 상쇄
- 부모-자식요소 간
  - 부모 블록에 border, padding, inline content가 없어서 부모와 자식의 margin-top이 만나는 경우
  - 부모블록에 border, padding, inline content가 없고, 부모-자식을 분리할 height 값이 지정되지 않아 부모와 자식의 margin-bottom이 만나는 경우
- 빈 블록
  - border,padding,content가 없고, height 또한 존재하지 않으면, 해당 블록의 margin-top과 margin-bottom이 상쇄 됨

## padding

- 단축 속성 
- 음수 값을 사용할 수 없음
- &lt;percentage&gt;를 쓸 경우 무조건 부모 요소의 width를 기준!!!

## 테두리 - border-style , border-width, border-color

- border-style 
  - 기본값 : none
  - 값 : solid ,dashed, dotted 등

- border-width
  - 값 : 키워드(thin, medium, thick), &lt;length&gt; 값을 사용해도 됨

- border-color
  - border 색상 지정

  ```css
      .box {
        width: 100px;
        height: 300px;

        border-style: dotted solid;
        border-width: 10px;
        border-color: wheat tomato;
      }
      /* boreder-style을 none으로 지정하면 width와 color을 설정해도 0으로 돼서 보이지 않음 */
  ```

## border(shorthand)

- 스타일을 지정하지 않으면 기본값이 none이 사용돼 테두리가 보이지 않음
- 순서 상관 없음
- 외곽선(outline): button 같은 것에 추가하는 것으로 border랑 다름

  ```css
  .box {
    width; 100px;
    height: 100px;

    border: solid red 5px;
  }
  ```

## border-radius

-  요소 테두리 경계의 꼭짓점을 둥글게 만듦
-  &lt;percentage&gt;로 입력할 경우 가로축 값은 요소 박스의 너비에 대한 백분율이고 세로축 값은 박스의 높이에 대한 백분율
- 음수값은 사용할 수 없음
- 값 순서 : left-top right-top right-bottm left-bottm 혹은 마주 보는 값끼리 사용 가능

## box-sizing

- 요소의 너비와 높이를 계산하는 방법을 지정
- 값
  - 기본값 : content-box
    -> width와 height 속성이 콘텐츠 영역만 포함하고 안팎 여백과 테두리는 포함하지 않음,content의 순수한 width와 height (border, padding, margin의 크기는 넣지 않음)
  - border-box
  -> width와 height 속성이 padding과 border는 포함하고 margin은 포함하지 않음; padding과 border가 요소 상자 안에 위치; content 외에 border, padding을 합한 것이 컨테이너의 width와 height

    ```css
    * {
      border-box: border-box;
    }
    ```