## transition-property, transition-duration

 - transintion-property
  - 트랜지션을 적용해야 하는 CSS의 속성의 이름 명시하여 나열한 속성만 트랜지션 하는 동안 움직임

- transition-duration
  - 트랜지션이 일어나는 지속 시간을 명시

  ```css
  .box {
  width: 300px;
  height: 80px;
  border: 2px dashed teal;
  background-color: darkgoldenrod;
  font-size: 50px;
  color: white;
  transition-property: all;
  transition-duration: 0.5s;
  }

  .box:hover {
  background-color: tomato;
  }
  ```

## transition-delay, transition-timing-function
  
  - transition-delay
    - 속성이 변한 시점과 트랜지션이 실제로 시작하는 사이에 기다리는 시간을 정의

  - transition-timing-function
    - 속성의 중간 값을 계산하는 방법을 정의하는 함수
    - 한마디로 변화율(?) 
      - ease, ease-in, linear, ease-out 등

      ```css
      .box {
      width: 300px;
      height: 80px;
      border: 2px dashed teal;
      background-color: darkgoldenrod;
      font-size: 50px;
      color: white;
      transition-property: all;
      transition-duration: 0.5s;
      transition-delay: 1s;
      transition-timing-function: ease-in;
      }

      .box:hover {
        background-color: tomato;
        height: 400px;
      }

      ```

## transition의 shorthand

- 속성의 순서가 중요
- transition: transition-property transition-duration  transition-delay transition-timing-function 

  ```css
  .box {
    transition: all 3s 0.5s linear;
   }
  ```


## transition + transform의 활용 예

```css
.Hello {
  width: 100px;
  height: 100px;
  border: 10px solid seagreen;
  border-radius: 30px;
  background-color:rgb(3, 200, 10);
  transition:  all 2s ease-in;
  transform-origin : bottom right;
      }
.Hello:hover {
  transform: rotate(360deg) translateY(30px);
  }