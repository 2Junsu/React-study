react-router-dom이 v6으로 업데이트 되면서 몇 가지 달라진 점이 있다.
index.js에서
<BrowserRouter>
  <App />
</BrowserRouter>
의 형태로 쓴 후, App.js에서는 BrowserRouter를 안 써도 된다.

Switch가 Routes로 변경되었다.
또한 Route 내의 component가 element로 변경되었다.
중첩 라우팅을 방지하는 exact가 사라졌다.

한 페이지에 대해서도 최소 단위 컴포넌트로 만들어 보는 것을 배웠다.
이전에 했던 여기저기 차박지 프로젝트에서는 최소 단위 컴포넌트를 만들지 않아서 리액트의 장점인 재사용성을 제대로 활용하지 못 했다.
이번 기회에 컴포넌트로 나눠보는 것을 경험함으로써 리액트의 장점을 느꼈다.
