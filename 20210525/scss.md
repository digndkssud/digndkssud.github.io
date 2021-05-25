# 재활용(Mixins)


```scss

@mixin center {
  display: flex;
  justify-content: center;
  align-items: center;
}

.container {

  @include center;
  .item {
    @include center;
  }

}
.box {
  @include center
}
```
---

# 재활용(mixin) 인수
```scss
@mixin box($size: 100px, $color: tomato) {
  width: $size;
  height: $size;
  background-color: $color;
}

.container{
  @include box(200pxm, red);
  .item{
    @include box($color: green);// 키워드 인수
  }
}

.box {
  @include box;
}

```
---

# 반복문

```scss
 
@for $i from 1 through 10{
  .box:nth-child(#{$i}){
    width: 100px * $i;
  }
}

```
---
# 함수
```scss
@mixin center{
  display: flex;
  justify-content: center;
  align-items: center;
}

@function ratio($size, $ratio){
  @return $size * $ratio
}

.box{
  $width: 100px;
  width: $width;
  height: ratio($width, 1/2); 
  @include center;
}
```