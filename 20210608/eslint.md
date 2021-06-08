# eslint(프로젝트에 관한 약속)

```js
$ npm i -D eslint eslint-plugin-vue babel-eslint

//입력 후

.eslintrc.js 파일 생성 


module.exports = {
  env: {
    browser : true,
    node: true
  },
  extends: [
    // vue에 관한 설정
    //'plugin:vue/vue3-essential',// Lv1
    'plugin:vue/vue3-strongly-recommended', // Lv2
    //'plugin:vue/vue3-recommended', //Lv3
    // js에 관한 설정
    'eslint:recommended'
  ],
  parserOptions: {
    parser: 'babel-eslint' 
  },
  rules: {
    // 줄에 관한 설정
     "vue/html-closing-bracket-newline": ["error", {
      "singleline": "never",
      "multiline": "never"
    }],
    // '/' 관한 설정
    "vue/html-self-closing": ["error", {
      "html": {
        "void": "always",
        "normal": "never",
        "component": "always" 
      },
      "svg": "always",
      "math": "always"
    }]
  }
}

// ctrl + shift + p
// => 기본 설정: 설정 열기에 들어가서
// 해당 코드를 입력하면 오류가 있는 부분을 고쳐준다.
"editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    }
```