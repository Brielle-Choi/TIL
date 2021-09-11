## @keyframes
- 개발자가 애니메이션 중간중간의 특정 지점들을 거칠 수 있는 키프레임들을 설정
- %가 의미하는 것은 애니메이션의 시작과 끝 상태를 의미, 만약 이 타임셋이 정해져 있지 않으면 무효.
- 두개의 속성을 나열 할땐 'from'과 'to'사용

```css
.FA {
  width: 100px;
  height: 100px;
  border: 10px solid seagreen;
  border-radius: 30px;
  background-color:rgb(3, 200, 10);

  animation: my-first-one 2s infinite;
}
  
@keyframes my-first-one {
  0% {font-size: 20px;
  }
  50% {width: 300px;
  font-size: 80px;}
  100% {font-size: 20px;}
}
```
## animation name, animation-duration
- animation name
  - 기본값: none
  - 대소문자 구분
  - 알파벳, 숫자(0-9), underscores(_), dashes(-)만 사용 가능
  - 어떤 @keyframes을 쓸건지 정의함
- animation-duration
  - 한 사이클이 완료하는데 걸리는 시간
  - 음수 값은 유효하지 않음 (cf anmation-delay는 음수값 허용)
  - s, ms 단위 사용

## animation-delay, animation-timing-function

- animation-delay
  - 애니메이션이 시작할 시점을 지정
  - 음수 값을 지정하면 애니메이션이 즉시 시작되지만 애니메이션 시퀀스 도중부터 시작함
  - ease, ease-in-out, linear 등의 값
  - 기본값: ease

  ```css
  div {
    width: 100px;
    height: 100px;
    border: 10px solid seagreen;
    border-radius: 30px;
    background-color:rgb(3, 200, 10);
    animation: my-first-one 1s infinite
  }

  .FA1 {
    background-color: rgb(3, 200, 10);
    animation-delay: 0.7s; 
  }
  .FA2 {
    background-color: rgb(101, 125, 153);
    animation-delay: 1s;
  }
  .FA3 {
    background-color: rgb(200, 3, 141);
    animation-delay: -0.3s;
  }
    
  @keyframes my-first-one {
    0% {font-size: 20px;
    }
    50% {width: 300px;
    font-size: 80px;}
    100% {font-size: 20px;}
  }
  ```
 ## animation-iteration-count, animation-direction

- animation-iteration-count
  - 반복 횟수
  - 기본값 : 1
- animation-direcrion  
  - 값
    - normal : 매 사이클마다 정방향으로 재생 (기본값)
    - reverse : 매 사이클마다 역방향으로 재생
    - alternate : 매 사이클마다 각 주기의 방향을 뒤집으며 첫 번째 반복은 정방향으로 진행
    - alternate-reverse : 매 사이클마다 각 주기의 방향을 뒤집으며 첫 번째 반복은 역방향으로 진행
    ```css
            .box1 {
          animation-name: rotate;
          animation-duration: 2s;
          animation-timing-function: linear;
          animation-iteration-count: infinite;
          animation-direction: alternate;
          }

        @keyframes rotate {
          from {
            transform: rotate(0);
          }
          to {
            transform: rotate(360deg);
          }
        }1
    ```
## animation-play-state
 - running : 기본값
 - paused
 - 애니메이션을 멈추거나 동작 시킬 수 있음

## animation-fill-mode
- 값
  - none : 애니메이션은 실행되지 않을 떄 스타일 적용 하지 않음
  - forwards : 대상은 실행 된 애니메이션의 마지막 keyframe에 의해 설정된 계산 된 값을 유지 (기존 스타일 ->keyframe 시작 ->keyframe 마지막)
  - backwards : 기존스타일을 아예 건너뛰고 keyframes 시작->기존 스타일

  ```css
    div {
    width: 100px;
    height: 100px;
    border: 10px solid green;
    background-color: greenyellow;
  }

  .box2 {  
    animation: fill-mode 2s linear;
    animation-fill-mode: forwards; 
    }


  @keyframes fill-mode {
    0% { background-color: blueviolet;}
    50% { background-color: blue;}
  100% { background-color: cornflowerblue;}
  }
  ```


