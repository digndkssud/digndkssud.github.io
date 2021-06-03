# Babel

```plaintext
ES6, ES7, ES8에서 작성된 파일을
구형 브라우저에서도 구동할 수 있게
ES5로 변환해주는
컴 파 일 러
```
```js
$ npm i -D @babel/core @babel/preset-env

// 터미널에 입력 후
// .babelrc.js라는 파일을 생성 시킨다
// 그 후 하기의 코드 추가. 
module.exports = {
    presets: ['@babel/preset-env']
}

// main.js에서 

async function test(){
  const promise = Promise.resolve(123)
  console.log(await promise)
}
test()

// 위와 같이 적으면 
// regeneratorRuntime is not defined 오류가 콘솔창에 뜸
// 그래서 

$ npm i -D @babel/plugin-transform-runtime

module.exports = {
    presets: ['@babel/preset-env'],
    plugins: [
        ['@babel/plugin-transform-runtime']
    ]
}
// plugins 추가

```

# parcel - 커맨드 라인 인터페이스(CLI)

https://ko.parceljs.org/cli.html


```js
// ex
$ npm run dev
// 다음과 같이 포트번호를 지정해 줄 수도 있다.
"dev": "parcel index.html --port 1216",
```