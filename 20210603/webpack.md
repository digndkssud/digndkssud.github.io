# webpack

```js

$ npm i -D webpack webpack-cli webpack-dev-server@next
// webpack => 번들러가 동작하기 위한 핵심적인 패키지
// webpack-cli => 터미널에서 입력하는 명령(커멘드 라인 인터페이스) 지원
// webpack-dev-server => 개발 특화 새로고침 그때 그때 해줌
"scripts": {
    "dev": "webpack index.html",
    "build":"webpack build index.html"
  }

// webpack.config.js을 생성해서 구성요소를 작성해주어야한다.
// node.js환경에서 동작한다.



// --------------------------------------------------------------------------------------
// webpack.config.js

// import
const path = require('path')


// export
module.exports = {
  // parcel index.html
  // 파일을 읽어들이기 시작하는 진입점 설정(js)
  entry: './js/main.js',

  // 결과물(번들)을 반환하는 설정
  output: {
    // path: path.resolve(__dirname,'dist'),// default 값으로 dist라는 폴더를 생성
    // filename:'main.js', // js 파일을 생성
    clean: true // 기존에 있는 다른 js 파일은 삭제하고 main.js만 남겨둔다
  }
}

// index.html을 삽입해서 개발서버 오픈하기 위한 번들러
$ npm i -D html-webpack-plugin

const HtmlPlugin = require('html-webpack-plugin')

// -------------------------------------------------------------------------------
// webpack.config.js에 추가 

// 번들링 후 결과물의 처리 방식 등 다양한 플러그인들을 설정
  plugins: [
    new HtmlPlugin({
      template: './index.html'
    })
  ],
// host의 이름을 직접적으로 지정 가능
devServer:{
    host: 'localhost'
  }

```