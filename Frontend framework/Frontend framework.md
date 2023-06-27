React와 Vue
==========

## ※ 차이점
### 1. React 
- 단방향 데이터 바인딩
- React 는 UI 라이브러리이다. UI 조작 외에 전역 상태 관리, 라우팅, ajax 등의 기능은 별도의 라이브러리를 통해 사용해야 한다.
    - 이러한 이유로 Redux, react-router, axios 등의 라이브러리 사용법 또한 익혀야 하기 때문에 진입장벽이 높다.
    - React 는 기본적으로 UI 라이브러리이고 코딩 방식에 자유도가 높다.
    - 개발자간 코딩 방식이 상이할 수 있다.
- JSX(JavaScript XML) 형태로 코드를 작성하기 때문에 JavaScript 숙지가 필요하다.
```
function App() {
  return (
    <h1>Hello</h1>
  );
}
```
- 파일별로 컴포넌트를 분리할 수 있으며 다른 곳에서 재사용하는 것이 매우 용이하다.
- TypeScript 를 사용한 구현이 Vue 보다 쉽다.
- React Native 를 사용한 모바일 개발이 가능하다.

### 2. Vue
- 양방향 데이터 바인딩
- Vue 는 프레임워크다.
  - 프레임워크에서 지정한 문법으로 개발해야 한다.
  - 개발자간 코딩 방식이 비슷해진다.
- 일반적인 HTML, JS, CSS 영역이 나눠져있고, HTML 중간에 자바스크립트를 많이 섞지 않기 때문에 HTML 스럽게 볼 수 있어서 페이지 구조 파악이 쉽다.
- Vue 문법에 따라 코드를 작성하는데 상대적으로 React 보다 간단하다.
```
React 의 if
function App() {
    const  conditional = () => {
        if (true) {
            return <p>참</p>
        } else {
            return <p>거짓</p>
        }
    }
    return (
        <div>(conditional())</div>
    );
}

Vue 의 if
<template>
    <div>
        <p v-if="show">참</p>
        <p v-else>거짓</p>
    </div>
</template>
```