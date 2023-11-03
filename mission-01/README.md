# Homework Mission-01
과제 그 첫번째</br>
### 과제 수행 시간
+ 11.03 18 : 30 ~ 11.04 05:05 (현재 리드미 작성시간)</br>
+ 11.04 엄청 친한 친구의 결혼식으로 인한 밤샘 과제

### 개발 환경
+ HTML
+ CSS


### 목표
+ 첫 과제 이니만큼 최대한 따라해보자.
+ 다양한 방법을 시도해보자.
+ 포기하지말고 부딪히고 깨지자.

### 아쉬웠던 점
+ 일단 코드를 보시면 아시겠지만 absolute 로 도배되어있다.
+ 과제하면서 이게 맞나? 싶을정도로 도배되어있다.
+ float 및 flex 의 제대로된 활용법이 아직 미숙하다.
+ 친구의 결혼식을 가야하기 때문에 과제를 심도있게 하지 못한점.
</br></br></br>

# 코드 설명
```html
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <link rel="stylesheet" href="./css/normalize.css" />
  <link rel="stylesheet" href="./css/mission-01.css" />
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300;400;700&display=swap" rel="stylesheet">
  <title>Mission-01</title>
</head>
```
기본 HTML 설정 및 폰트 삽입
</br></br></br></br>

```html
<body>

  <div class="box">
    <div class="box1">
    </div>

    <div class="box2">
      <div class="handcream">
      </div>
      <div class="tea">
      </div>

    </div>
  </div>
</body>
```
Box들 분류

1. 제일 큰 Box (box1 과 box2 포함)
2. box1 (이곳에 꿀생강차 가 들어감)
3. box2 (핸드크림 과 보리차가 들어감)
4. handcream 상자
5. tea 상자
</br></br></br></br>

```css
/* 버튼 및 구매버튼 활성화 */

/* 초기 버튼 모양 */
.button-init {
  width: 42px;
  height: 42px;
  flex-shrink: 0;
  color: rgba(0, 0, 0, 20);
  border: 0;
  position: absolute;
  bottom: 20px;
  left: 20px;
  background: url(/images/button.svg);
  display: block;
  cursor: pointer;
}

/* 구매하기 버튼 */
.button-buy {
  position: absolute;
  left: 20px;
  bottom: 20px;
  display: none;
  background: var(--blue-600);
  width: 112px;
  height: 42px;
  padding: 0;
  border: 0;
  color: #fff;
  animation-name: fadein;
  animation-duration: 0.2s;
}

/* 구매하기 텍스트 */
.buy-text {
  color: var(--White);
  font-family: Noto Sans;
  font-size: 13px;
  font-style: normal;
  font-weight: 500;
  line-height: 120%; /* 16.8px */
  position: absolute;
  right: 40px;
  top: 12px;
  width: 52px;
  height: 17px;
}

/* 구매하기 이미지 */
.buy-arrow {
  width: 6px;
  height: 10px;
  position: absolute;
  top: 15px;
  right: 18px;
}

/* 구매하기 링크 */
.button-buy a {
  display: block;
  width: 100%;
  height: 100%;
  cursor: pointer;
}

/* 구매하기에 hover 시 색깔 */
.button-buy a:hover {
  background: #003f8e;
}

/* 초기 버튼을 누를 때 구매하기 버튼 설정 */
.button-init:focus + .button-buy {
  display: block; 
}

/* 애니메이션 */
@keyframes fadein {
  0%{
    opacity: 0;
  }
  100%{
    opacity: 1;
  }
}

/* 박스 활성화 */
.box1:hover,
.tea:hover,
.handcream:hover {
  border: 1px solid var(--blue-600);
}
```
공통으로 들어갈 버튼 설명

</br></br></br></br>
```html
<div class="box">
    <div class="box1">
      <img class="honey-logo" src="/images/logo.png" alt="" />
      <span class="honey-text">따뜻한 차 향기</span>
      <button type="button" class="button-init"></button>
      <button type="button" class="button-buy">
        <a href="/mission-01.html">
          <span class="buy-text">구매하기</span>
          <img class="buy-arrow" src="/images/angle-right.svg" alt="" />
        </a>
      </button>
      <img class="honey-product" src="/images/product.png" alt="" />
    </div>
```
```css
.box {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

/* 윗 박스 설정 */

.box1 {
  border: 1px solid var(--gray-500);
  width: 502px;
  height: 310px;
  position: relative;
  /* display: flex; */
}
```
```css
/* 꿀생강차 설정 */

.honey-logo {
  width: 112px;
  height: 67px;
  position: absolute;
  top: 75px;
  right: 317px;
}

.honey-text {
  color: var(--gray-800);
  text-align: center;
  font-family: Noto Sans;
  font-size: 24px;
  font-style: normal;
  font-weight: 700;
  line-height: 150%;
  position: absolute;
  top: 155px;
  right: 274px;
  width: 200px;
  height: 37px;
}

.honey-product {
  width: 222px;
  height: 270px;
  position: absolute;
  top: 20px;
  right: 28px;
}
```
+ 꿀생강차가 들어가는 곳
+ 제일 큰 박스를 2 박스로 나누어 flex : column 으로 레이어 나눔
+ 그 중 위의 박스에 꿀생강차를 배치
</br></br></br></br>


그 후는, 코드의 반복.
