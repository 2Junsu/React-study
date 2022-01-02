input handling
---
오늘의집 클론코딩 프로젝트를 진행하면서, 회원가입 페이지에서 실시간으로 가입 정보의 형식이 맞는지 틀린지를 체크하는 것을 구현했는데 이때 event.target을 처음 사용해봤다.


아래의 컴포넌트는 styled-components를 사용해 디자인한 input이다. 컴포넌트의 name을 설정해주고 onInput에 handleChange 함수를 넣어준다. 이렇게 하면 input의 값이 변경될 때마다 handleChange 함수가 실행된다. 참고로 onInput은 input 값이 변경된 직후에 발생하고, onChange는 input 값이 변경된 후에 포커스를 잃을 때 발생한다.
```javascript
<Input
   name="email"
   placeholder="이메일"
   onInput={handleChange}
   borderColor={textColor.email}
/>
```
---
아래의 함수는 사용자가 input에 값을 입력 시에 해당 값을 받아서 setState 해 주는 handleChange 함수이다.
```javascript
const handleChange = (e) => {
   const changed = {
     ...form,
     [e.target.name]: e.target.value,
   }
   console.log(changed)
   setForm(changed)
 }
```
매개변수 e가 넘어오면서 e.target.name은 위에서 Input 컴포넌트에서 설정했던 name과 같은 값을 갖고, e.target.value는 e로 넘어온 input에 입력된 값이 된다. 이를 이용하여 state값을 변경했다.
changed 객체에서 spread 연산자를 사용하여 이전에 저장돼있던 form의 값을 불러오고, 그 후에 event의 값을 사용함으로써 바뀐 값만 form에 저장되도록 구현했다.
만약 spread 연산자를 사용하지 않으면 state의 값이 모두 비고 event의 값만 state에 저장되게 된다. 이를 막기 위해 우선 state에 저장된 값을 불러온 후에 event의 값도 저장한 것이다.
