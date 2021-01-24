# Express 시작하기

## 설치

```
$ npm init
$ npm install express
$ npm install express --save			// 디렉터리에 종속 항목으로 모듈 설치
$ npm install express-generator -g		// express 애플리케이션 생성기
```



## Hello World 예제

app.js

```
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
    res.send('Hello World!');
});

app.listen(port, () => {
    console.log('Example app listening at http://localhost:' + port);
});
```



## Express 애플리케이션 생성기

```
$ npm install express-generator -g			// 생성기 설치
$ express --view=pug myapp			// myapp 프로젝트 생성
```



## 기본 라우팅

```
app.method(path, handler)
```

- app: express의 인스턴스
- method: http 요청 메소드
- path: 서버 경로
- handler: 라우터가 일치할 때 실행되는 함수 



```
app.get('/', function(req, res){
  res.send('Hello World!');
});
```

- 홈 페이지에서 Hello World!로 바로 응답



```
app.post('/', function (req, res) {
  res.send('Got a POST request');
});
```

- post 요청에 응답



```
app.put('/user', function (req, res) {
  res.send('Got a PUT request at /user');
});
```

- put 요청에 응답



```
app.delete('/user', function (req, res) {
  res.send('Got a DELETE request at /user');
});
```

- delete 요청에 응답

// 라우팅 안내서에서 자세하게 다룰 예정



## Express에서 정적 파일 제공

이미지, CSS, js 파일과 같은 정적 파일을 제공

```
app.use(express.static('public'));
```

- http://localhost:3000/stylesheets/style.css