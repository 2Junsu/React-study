비동기 처리를 위한 promise에 대해 배웠다.
promise는 비동기 처리가 수행이 되었는지, 되었다면 성공적으로 되었는지를 알 수 있는 객체이다.

pending : 비동기 처리 수행 전
fulfilled : 수행 성공
rejected : 수행 실패
settled : 수행 성공 or 실패

의 4가지의 상태가 존재한다. 이 promise로 구성된 비동기 함수는 promise 객체를 반환하고, 이 객체의 후속 처리 메서드(then)을 통해서 비동기 처리 결과를 받아서 처리해야 한다.

```javascript
let promise = new Promise((resolve, rejected)=>{
  setTimeout(()=>resolve("성공"),1000)
 })
 
 promise.then(result=>{
  console.log(result)
 }
```

여기에서 async, await라는 개념이 등장하는데, 내가 이전까지 잘 이해하지 못 했던 개념이다. 이번 기회에 강의를 들으면서 전보다는 조금은 이해가 된 것 같은데 많이 써 보면서 비동기 처리와 친해져야겠다.
async 키워드는 함수 앞에 붙여서 사용하고, async 함수는 항상 promise 객체를 반환한다.
await 키워드는 async과 짝꿍으로 해당 키워드가 붙으면 promise가 처리될 때까지 기다렸다가 그 이후에 결과를 반환한다. (즉, 함수 실행을 잠시 중단한다.)

```javascript
async function exam() {
  let promise = new Promise((resolve, reject) => {
    setTimeout(() => resolve('성공'), 1000)
  })

  console.log('before await : ', promise)

  let result = await promise
  console.log('after await : ', promise)
  console.log('result : ', result)
}
```

exam 함수를 실행하면 before await에서 출력되는 promise값은 아직 1초가 지나지 않았으므로 비동기 처리가 수행되지 않아서 pending이 출력된다.
await 키워드를 쓴 후에 그 아래에서 다시 한 번 promise값을 출력해보면 after await에서는 fulfilled가 출력된다.
이처럼 await 키워드는 함수 실행을 잠시 중단하고, promise가 처리된 후에 실행하는 역할을 한다.
