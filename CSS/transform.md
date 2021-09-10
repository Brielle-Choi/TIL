## transform
- 요소에 회전, 크기 조절, 기울이기, 이동 효과를 부여할 수 있음
- 변형 함수는 오른쪽에서 왼쪽으로 하나 씩 순서대로 적용

- transform-funciton
  - 크기- scale
    - 2D로만 조절 가능
    - scale(sx,sy)
      - 실제 컨텐츠 사이즈가 줄어드는 것이 아니라 보여지는 이미지만 줄어듬
    - scalex :x축만
    - scaley: y축만
      ```css
        #sample {
        width: 400px;
        transform: scale(0.5);
        } 
      ```

  - 회전- rotate
      - rotate(a)
      - angle은 자료형
        - deg, grad, rad, turn

        ```css
        #sample {
        width: 400px;
        transform: scale(0.5) rotate(45deg);
         }
        ```
  - 이동- translate
    - 한가지 값만 입력시 x의 값으로 인식
    - length나 percentage 입력 가능
    - translatex : x축만, translatey : y 축만

  - 기울이기-skew
    - 한가지 값만 입력시 x의 값으로 인식
    - deg, grad, rad 등
    - skewX, skewY

    
        ```css
        #sample {
        width: 400px;
        transform: skew(20deg,0)
         }
        ```

  - 기준점-transform-origin
    - 기준점 변경
    - 기본값 : center
    ```css
        #sample {
        width: 400px;
        transform: scale(0.5) rotate(45deg) translate(100px,200px) transform-origin: top left;
      ;
      }
      ```