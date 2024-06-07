# TIL
Today I learned

## React

### 1. create-react-app

1. Node.js를 설치
2. npm install create-react-app -g 
3. create-react-app <app-name> 
(--scripts-version 1.1.5) 
4. cd <app-name> 
5. npm start

### 2. 프로젝트 구조
a. Lock 파일, package.json : 의존성 파일 버전(requirements 느낌)

b. node_module : npm install 된거 보관 폴더.

c. public : 웹서버 폴더. 스크립트는 src 폴더에

1. index.html : SPA 에선 하나만 존재

   ```html
   <div id="root"></div>
   ```
   여기다 나중에 리액트 마운트함 css도. 메타태그?

2. manifest.json : 앱 데이터 정의
   
d. src : 앱 파일들 폴더

1. index.js : DOM에서 root(index.html) 접근
2. app.js : 처음 스타터로 만들어짐
3. app.css : app.js 에서 사용되는 css
4. index.css : 전체 css

### 3. 컴포넌트

-> App.js에 있는 컴포넌트

```javascript
class App extends Component {
  render() {
    return (
      <div>
        <h1>Hola!</h1>
      </div>
    );
  }
}

export default App;
```

export default app == index. js 에서 가져온 것
하나의 루트 컴포넌트만 렌더링.
App.js에 다 때려박는 느낌?

#### React 컴포넌트 사용

```javascript
import React, { Component } from "react";
class App extends Component {
  render() {
    return (
      <div className="App">
        <h1>Hola!</h1>
        <h2>Name's TG.</h2>
      </div>
    );
  }
}
```

클래스 생성 후 컴포넌트 상속 == extends

render() 메서드는 모든 것을 하나의 div 요소 안에 리턴

### 4. 함수형 컴포넌트

클래스 컴포넌트 : render() 필요함!

함수형 : 없지만, 그래도 그냥 단순히 뭘 리턴함.

src 폴더에 만들고싶은컴포넌트명.js 생성

const나 let으로 선언 후 화살표 함수 사용 권장

```javascript
import React from "react";

const person = () => {
  return <p> I'm a person! </p>;
};

export default person;
```

#### 사용하려면

```javascript
import Person from "./Person/Person";
```

```javascript
<Person /> 
<Person></Person>
```