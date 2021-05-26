# 색상 내장 함수

```scss
.box{
  $color: royalblue;
  width: 200px;
  height: 100px;
  margin: 20px;
  border-radius: 10px;
  background-color: $color;
  &.built-in { // box를 참조하는 built-in
    background-color : mix($color, red);
    // 두 가지의 색상을 섞어 씀
    background-color : lighten($color, 10%);
    // 첫 번째 색상을 해당 숫자 퍼센테이지만큼 밝게 만들어준다.


    background-color : saturate($color, 40%);
    // 색상을 해당 퍼센테이지만큼 채도를 높여준다.
    background-color : desaturate($color, 40%);
    // 색상을 해당 퍼센테이지만큼 채도를 낮춘다.


    background-color : grayscale($color);
    // 해당 색상을 회색화한다.


    background-color : invert($color);
    // 해당 색상을 반전시킨다. 


    background-color : rgba($color, .5);
    // 두번째는 투명값


  }
  &:hover{
    background-color : darken($color, 10%);
    // 첫 번째 색상을 해당 숫자 퍼센테이지만큼 어둡게 만들어준다. 
  }
}
```

---
# 가져오기

```scss
// sub.scss

body {
  .container{
    background-color: orange;
  }
}

// main.scss

@import "./sub.scss";
// 확장자 명은 생략 가능
@import "./sub","./sub2";

$color: royalblue;

.container {
  h1 {
    color: $color;
  }
}

```

