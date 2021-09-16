## Container - grid-template-rows, grid-template-columns

- 행과 열을 만들어 주는 property
```css
.container {
  border: 5px dashed orange;
  display: grid;
  grid-template-columns: repeat(3,1fr);
  grid-template-rows: repeat(2, 100px);

}
  /* repeat 함수를 이용해서 (반복 수, 값) 이용 */
 
  ```

## grid-template-areas

```css
.container {
  border: 5px dashed orange;
  width: 400px;
  height: 400px;
  display: grid;
  grid-template-columns: repeat(5,1fr);
  grid-template-rows: (3,1fr);
  grid-template-areas: 
    "hd hd hd hd hd"
    "ma ma ma . sb"   
    ". ft ft ft ft";
}

/* .은 비어있는 칸을 나타낼 때 사용 */

.item {
  background-color: paleturquoise;
  border: 3px solid blue;
  font-size: 24;
}

.header {
  grid-area: hd;
}

.main {
  grid-area: ma;
}

.sidebar {
  grid-area: sb;
}

.footer {
  grid-area: ft;
}

/* class를 grid만의 이름으로 정의 */

```

## Container- row-gap, column-gap, gap

- row-gap
  - 각각의 행들 간의 간격(gutter)을 설정
- column-gap
  - 각각의 열들 간의 간격을 설정

    ```css
      .container2 {
        border: 5px dashed orange;
        width: 400px;
        height: 400px;
        display: grid;
        grid-template-columns: repeat(2,1fr);
        grid-template-rows: (4,1fr);
        /* row-gap: 20px;
        column-gap: 50px;은 밑에 gap 속성으로 묶어 적을 수 있음 */
        gap : 20px 50px;
    }
    ```

## Container - grid-auto-rows, grid-auto-columns

- grid-template-rows나 grid-template-columns에서 명시적으로 지정한 cell 외에 다른 cell들의 크기를 암시적으로 지정해 줌

  ```css
  .container2 {
  border: 5px dashed orange;
  width: 400px;
  height: 400px;
  display: grid;
  grid-template-columns: repeat(3,1fr);
  grid-template-rows: (3,1fr);
  
  grid-auto-rows: 100px;
  grid-auto-columns: 50px;
  }
  ```

## grid-auto-flow

- 내부의 아이템들이 어떤 방향으로 채워질 지 설정
  
  ```css
  .container2 {
  border: 5px dashed orange;
  width: 400px;
  height: 400px;
  display: grid;
  grid-template-columns: repeat(3,1fr);
  grid-template-rows: (3,1fr);
  grid-auto-flow: row dense ;
  }
    /* dense는 빈 공간을 채우면서 흘러감 */

  ```

## Container - grid(shorthand)

- 외재적인(명시적인) 속성 : grid-template-rows, grid-template-columns
grid-template-areas
- 내재적인(암시적인) 속성 : grid-auto-rows, grid-auto-columns, grid-auto-flow

  ```css
  .container2 {
  border: 5px dashed orange;
  width: 400px;
  height: 400px;
  display: grid;
  
  /* grid-template-rows: 1fr 2fr;
  grid-template-columns: 100px 200px
  grid-auto-flow : column 
  밑에와 상동*/
  grid: 1fr 2fr/ auto-flow 100px 200px;
  
  }
  ```


## Container - justify-content, align-content

 - 선행조건: 컨테이너의 크기가 컨텐츠의 크기보다 커서 여유 공간이 있어야 함
 - flexbox의 내용과 같음
 - 전체의 컨테이너를 기준으로 중 아이템 덩어리를 어떻게 배치할지 결정
 - justify-content는 주축에 해당하고, align-content는 교차축에 해당

 ```css
 .container2 {
  border: 5px dashed orange;
  width: 100%;
  height: 500px;
 
  display: grid;
  grid-template-rows: repeat(3, 100px);
  grid-template-columns: repeat(3,100px); 
  justify-content: center;
  align-content: center;
}
```

## Container - justify-items, align-items

- 하나의 틀 안에서 각각의 item의 정렬에 관한 속성

```css
.container2 {
  border: 5px dashed orange;
  width: 100%;
  height: 500px;
 
  display: grid;
  grid-template-rows: repeat(3, 1fr);
  grid-template-columns: repeat(3,1fr); 
  justify-items: stretch;
  align-items: flex-end;
 }

 .item:nth-child(1) {
   width: 50px;
   height: 50px;
 }
 .item:nth-child(2) {
   justify-self: end;
 }
```


## Item - grid-row, grid-column

```css
.item {
  background-color: paleturquoise;
  border: 3px solid blue;
  font: size 24px;
  }

  .item:first-child {
    background-color:  coral;

    grid-row: 4/ span 2;
    grid-column: 2/ -1;
  
    /* grid-row : 행의 시작 줄 번호/ 행의 끝 줄 번호
    grid-column: 열의 시작 줄 번호/ 열의 끝 줄 번호
     span 속성을 사용할 때는 시작 줄 번호에서 span 값 만큼 차지
     */
  }
```

## Item - grid-area

- grid-row-start, grid-column-start, grid-row-end, grid-column-end 값을 한번에 설정하는 shorthand 속성
- grid-template-area가 사용하는 area 이름으로도 사용 가능
- 순서
  
  ```css
  /* grid-area: grid-row-start / grid-column-start / grid-row-end / grid-column-end 순으로 작성한다.*/

  
    /*grid-row: 4 / span 2;
    grid-column: 2 / -1;* 밑과 상동*/
    

    grid-area: 4 / 2 / span 2 / -1; 
  ```

## Item- order

- 기본값 : 0
- 정수만 사용 가능
- 값이 같으면 코드 순서가 앞에 있는 것이 먼저
- 흐름에 맞춰 순서가 정해짐

## Item - z-index

- 정수만 사용 가능
- 아이템이 겹쳤을 때 우선 적인 것을 화면 가까이 배치하거나 뒤로 배치 가능

## Grid 단위 - fr, min, content, max-content

- fr : 비율을 사용하여 나누어 가질 때 사용
- min-content : 텍스트 콘텐츠의 경우 가장 긴 단어 기준만큼 작아질 수 있는 범위 
  ```css
  .container2 {
  border: 5px dashed orange;
  
  display: grid;
  grid-template-rows: repeat(3,180px);
  grid-template-columns: min-content 1fr 1fr; 
  }
  /*min-content는 속성 값으로 들어갈 수 있음 */
  ```
- max-content : 텍스트의 경우 텍스트를 가장 길게 늘여쓸 까지의 범위

    
## Grid 단위 - auto-fill, auto-fit

- auto-fill: 남는 공간이 생기면 column이나 row가 자동으로 채워짐
- minmax(min,max) : 작아질 수 있는 최소의 크기 커질 수 있는 최대의 크기를 지정
  ```css
  .item {
  grid-template-columns: repeat(auto-fill minmax(100px, ifr));
  grid-auto-rows: 50px;
  }
  ```
- auto-fit : 컨텐츠 수가 작을 때 컨테이너가 커지면서 빈공간이 생기면 auto-fit을 이용해서 남는 공간이 꽉 채워짐
