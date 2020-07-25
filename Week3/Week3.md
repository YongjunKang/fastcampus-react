## 패스트캠퍼스 React

### Week3

사용 슬라이드
[Week3 라우팅](https://slides.com/woongjae/react-camp-3)
[Week4 컴포넌트 스타일링](https://slides.com/woongjae/react-camp-4)

#### Switch 와 NotFound

__Switch__
- 여러 Route 중 순서대로 먼저 맞는 하나만 보여줍니다.
- exact 를 뺄 수 있는 로직을 만들 수 있습니다.
- 가장 마지막에 어디 path 에도 맞지 않으면 보여지는 컴포넌트를 설정해서,
"Not Found" 페이지를 만들 수 있습니다.

Path에 해당하는 주소가 없을때 이동하는 NotFound 페이지 생성

```js
//NotFound.jsx

import React from 'react';

export default function NotFound() {
    return <h1>페이지를 찾을 수 없습니다.</h1>
}
```

```js
//App.js
function App() {
  return ( // Switch를 사용시 낮은 값이 아래로 가게 한다.
  <BrowserRouter>
    <Switch>
      <Route path="/profile/:id" component={Profile} />
      <Route path="/profile" exact component={Profile}/>
      <Route path="/login" component={login}/>
      <Route path="/about" component={About}/>
      <Route path="/" exact component={Home}/>
      <Route component={NotFound} />
    </Switch>
  </BrowserRouter>
  );
}
export default App;
```

#### JSX 링크로 라우팅 이동하기


NavLink 경로가 같으면 Active 한다.
```js
      <NavLink to="/" activeStyle={{fontSize: 5}}>
        Home으로 가기
      </NavLink>
// to="/"가 리액트 내의 주소와 동일하면 폰트사이즈가 5가 된다.
```

#### JS로 라우팅 이동하기
props.history.push("/");

#### withRouter = HOC
세상이 바뀌면서 HOC를 대체하는게 생겼다.

#### Redirect
advanced technique in React for reusing component logic.
=> 리액트에서 안써도 상관없지만 있으면 좋다.
=> 컴포넌트의 로직을 다시 사용하기 위해서 쓴다. (재사용 가능)

not part of the React API
=> API와 전혀 상관없다

a pattern that emerges from React’s compositional nature.
=> 리액트의 패턴이다.

A라는 컴포넌트를 받아 A를 복사 하는 형태가 아니라
받아서 다른 어딘가에 놓고 다시 주는 형태이다.

### Week4

### React Component Styling
