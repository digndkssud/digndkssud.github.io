# NPM 프로젝트 생성

```plaintext

$ npm init -y
$ npm i -D parcel-bundler
$ npm install bootstrap@next


main.js에서 

import bootstrap from 'bootstrap/dist/js/bootstrap.bundle'


main.scss에서 

@import "../node_modules/bootstrap/scss/bootstrap";

```
---

# 테마 색상 커스터마이징

main.scss

```scss

@import "../node_modules/bootstrap/scss/functions";
@import "../node_modules/bootstrap/scss/variables";
@import "../node_modules/bootstrap/scss/mixins";


$theme-colors: (
  "primary":    $primary,
  "secondary":  $secondary,
  "success":    $success,
  "info":       $info,
  "warning":    $warning,
  "danger":     $danger,
  "light":      $light,
  "dark":       $dark
);


@import "../node_modules/bootstrap/scss/bootstrap";
```

# 성능 최적화(트리 쉐이킹)
---

```js
//dropdown 관련된 데이터만
import Dropdown from 'bootstrap/js/dist/dropdown'

// bootstrap의 components의 via JavaScript

var dropdownElementList = [].slice.call(document.querySelectorAll('.dropdown-toggle'))
var dropdownList = dropdownElementList.map(function (dropdownToggleEl) {
  return new bootstrap.Dropdown(dropdownToggleEl)
})
// => 

var dropdownElementList = [].slice.call(document.querySelectorAll('.dropdown-toggle'))
dropdownElementList.map(function (dropdownToggleEl) {
  return new Dropdown(dropdownToggleEl)
})

$ npm i @popperjs/core

// 초기화 해줘야하는 컴포넌트는 서로 상이.

import Modal from 'bootstrap/js/dist/modal'

new Modal(document.querySelector('myModal'), {
  backdrop: 'static', // 모달이 띄어질 때 배경을 클릭해도 모달이 안 꺼짐
})



```