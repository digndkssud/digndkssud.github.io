# 데이터 종류

```scss
$number: 1;  // .5, 100px, 1em
$string: bold; // relative, "../images/a.png"
$color: red; // blue, #FFFF00, rgba(0,0,0,.1)
$boolean: true; // false
$null: null;
$list: orange, royalblue, yellow;
$map: (
  o: orange,
  r: royalblue,
  y: yellow
);

.box{
  width: 100px;
  color: red;
  position: relative;
}

```
---
# 반목문 @each (사용빈도 그렇게 높지 않다.)

```scss
$list: orange, royalblue, yellow;
$map: (
  o: orange,
  r: royalblue,
  y: yellow
);


//배열
@each $c in $list {
  .box{
    color: $c;
  }
}


// 객체
@each $k,$v in $map{
  .box-#{$k}{
    color: $v;
  }
}

```

# content

```scss
@mixin left-top{
  position: absolute;
  top: 0;
  left: 0;
  @content;
  // include 밑에 적은 내용들을
  // content의 위치에 대입
}

.container {
   width: 100px;
   height: 100px;
   @include left-top;
}

.box {
  width: 200px;
  height: 300px;
  @include left-top{
    bottom: 0;
    right: 0; 
    margin: auto;
  }
}

```