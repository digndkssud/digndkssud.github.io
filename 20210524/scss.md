# & - 상위 선택자 참조

```scss
.btn {
  postion: absolute;
  &.active{
    color: red; 
  }
} 

.list{
  li {
    &:last-child{
      margin-right: 0;   
    }
  }
}

.fs{
  &-small{ font-size: 12px; }
  &-medium{ font-size: 14px; }
  &-large{ font-size: 16px; }
}

```
---

# 중첩된 속성

```scss
.box{
// font - 네임스페이스
  font:{
    weight: bold;
    size: 10px;
    family: sans-serif;
  };
  // => font-weight, font-size, font-family
  // 끝날 때는 꼭 ;으로 마무리
  margin:{
    top: 10px;
    left: 20px;
  };
  padding:{
    top: 10px;
    bottom: 40x;
    left: 20px;
    right: 30px;
  };

  
}
```
---
# 변수

```scss


.container{
  $size: 200px;
  // size라는 변수에 100px이라는 값을 담아둔다
  position: fixed;
  top: $size;
  .item{
    $size: 100px; 
    width: $size;
    height: $size;
    transform: translateX($size);
  }
  left: $size; 
  // size가 item이라는 곳에서 재할당 되면 
  // 재할당 된 이후의 size는 재할당 된 값을 유지한다.
}
.box {
  width: $size;
}
```
---
# 연산
```scss
div{
  width: 20px + 20px
  height: 40px - 10px;
  font-size: 10px * 2;
  
  margin: 30px / 2; // => 지원 안 됨...

  margin: (30px / 2);
  margin: $size / 2;
  margin: 10px + 12px / 2; // 16px

  padding 20px % 7;
}

span { 
  font-size: 10px;
  line-height: 10px;
  font : 10px / 10px;
}

div{
  width: calc(100% - 200px);
}

```