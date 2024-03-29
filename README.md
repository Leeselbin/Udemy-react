# Udemy-react

### 특징

- SPA(Single Page Application)
- CSR(Client Side Rendering)

유데미 한입크기로 잘라 먹는 리엑트 강의


- 함수선언식 으로 표현된애들은 프로그램 실행전에 코드에 최상단으로 올라간다

```javascript
console.log(helloB()); // (O) 함수 선언식 함수들은 호이스팅되서 실행됨
console.log(helloA()); // (x) 함소 표현식 함수들은 에러가난다. 위에다하면

let helloA = function () {
  return "hi";
}; // 함수 표현식

console.log(helloA()); // (O) 여기서는 실행이된다.

function helloB() {
  return "hi";
} // 함수 선언식
```

- 함수 표현식 호이스팅이 안된다!!!!

```javascript
let helloA = () => {
    return "hi";
}

let helloA = () => return hi;
```

#### 객체선언

```
let person = new Object(); // person 객체 생성
let person = {};  // 객체 리터럴 방식
```

- 벨류값은 어떠한 자료형이 들어와도 상관없다
- key값은 무조건 String타입 이어야한다.
- key끼리 중복되도 error는 안난다 하지만 중복하지마라!!

```javascript
let person = {
  key: "value", // 프로퍼티 (객체 프로퍼티)
  key1: 123,
  key2: true,
  key3: undefined,
  key4: [1, 2],
  key5: function () {},
}; // 객체 리터럴 방식
```

---

#### 배열

- 배열에 자료형이 다달라도 들어간다~

```
let arr = new Array();
let arr = [];  // 배열 리터럴

let arr = [1, "2", true, null, {}, []];
```

#### 배열 내장함수

- map() - 원본 배열에 모든요소를 순회하면서 연산된 return 값을 반환해준다.

```javascript
const arr = [1, 2, 3, 4];
const newArr = arr.map((element) => {
  return element * 2;
});

console.log(newArr); // 2,4,6,8
```

- inclides() - 주어진 배열에서 전달받은 인자와 일치하는 값이 있는지 불리언식으로 리턴해준다

```javascript
const arr = [1, 2, 3, 4];
let number = 3;
console.log(arr.includes(number)); // true
```

- indexOf() - 주어진 배열에서 전달받은 인자와 일치하는 값의 인덱스를 반환하는 함수 , 주어진 인자가 없으면 -1

```javascript
const arr = [1, 2, 3, 4];
let number = 3;
console.log(arr.indexOf(number)); // 2
```

- findIndex() - 콜백함수를 전달해서 해당 콜백함수가 true반환하는 첫번째true를 반환하는 index를 찾아준다 -> 일치하는 녀석이 2개잇으면 가장먼저 조건을 만족하는 index를 가져온다.

```javascript
const arr = [
  { color: "red" },
  { color: "black" },
  { color: "blue" },
  { color: "green" },
];

console.log(arr.findIndex((elm) => elm.color === "green")); //3
```

- find() - 만족하는 요소자체를 반환한다

```javascript
const arr = [
  { color: "red" },
  { color: "black" },
  { color: "blue" },
  { color: "green" },
];
const index = arr.find((elm) => elm.color === "blue");
console.log(index); // {color:'blue'} 가반환된다.
```

- fileter() - 전달한 콜백함수가 true 반환하는 모든요소를 배열로 반환

```javascript
const arr = [
  { num: 1, color: "red" },
  { num: 2, color: "black" },
  { num: 3, color: "blue" },
  { num: 4, color: "green" },
  { num: 5, color: "blue" },
];

console.log(arr.filter((elm) => elm.color === "blue"));
// {num:3, color:'blue'} {num:5, color:'blue'}
```

- slice() - slice(begin,end) 배열을 begin부터 end-1까지 반환한다.

```javascript
const arr = [
  { num: 1, color: "red" },
  { num: 2, color: "black" },
  { num: 3, color: "blue" },
  { num: 4, color: "green" },
  { num: 5, color: "blue" },
];

console.log(arr.slice(0, 2)); // 0번부터 1번배열이나옴
```

- concat() - arr1.concat(arr2) 를하면 arr1뒤에 arr2를 붙인다.

```javascript
const arr1 = [
  { num: 1, color: "red" },
  { num: 2, color: "black" },
  { num: 3, color: "blue" },
];
const arr2 = [
  { num: 4, color: "green" },
  { num: 5, color: "blue" },
];
console.log(arr1.concat(arr2)); // 배열이 합쳐짐
```

- sort() - 배열의 문자열 원소를 사전순으로 정렬

```javascript
let chars = ["나", "다", "가"];
chars.sort();
console.log(chars); // '가', '나', '다'
```

- sort() -숫자를 오름차순으로 정렬

```javascript
let numbers = [0, 1, 3, 2, 30, 10, 20];

const compare = (a, b) => {
  if (a > b) {
    //크다
    return 1;
  }
  if (a < b) {
    //작다
    return -1;
  }
  //같다
  return 0;
};
numbers.sort(compare);
console.log(numbers);
```

- join() - 배열요소를 합친다. join("-") 를하면 구분자 "-"를 포함해합쳐짐
  디폴트 구분자는 "," 이다

```javascript
const arr = ["1", "2", "3", "4"];
console.log(arr.join()); // 1,2,3,4
```

---

#### Truthy & Falsy

- true 로 분류하는 값 = Truthy = [], {}, number, String, "false", Infinity

- false 로 분류하는 값 = Falsy = null, undefined, 0 , -0, NaN, ""

#### 삼항연산자

- 조건 ? 참: 거짓 ex) a>0 ? true : false;

```javascript
let a = 3;
if (a >= 0) {
  console.log("양수");
} else {
  console.log("음수");
}
//밑에처럼 한줄로 줄일수 있다.
a >= 0 ? console.log("양수") : console.log("음수");
```

#### 단락회로 평가

```javascript
const getName = (person) => {
  const name = person && person.name;
  return name || "객체가 아닙니다";
};

let person = null;
const name = getName(person);
console.log(name);
```

---

#### 동기와 비동기

#### 동기

- 동기처리 방식의 문제 : 하나의작업이 너무 오래 걸리게 될 시, 모든작업이 하나의 작업이 종료되기 전 까지 올 스탑 되기 때문에, 전반적인 흐름이 느려진다.
- BUT 멀티스레드 방식으로 작동시키면 작업 분할 가능하다~~
- BUTBUT!!@ 자바스크립트는 싱글스레드......... ㅅㄱ바위
- 콜백함수 호출해서 작업종료를 알린다.

#### Promise - 자바스크립트의 비동기를 도와줌

- 비동기 작업이 가질 수 있는 3가지 상태
- Pending(대기상태) , Fulfilled(성공) , Rejected(실패)
- Pending -> Fulfilled (해결resolve)
- Pending -> Rejected (거부reject)

#### 콜백을 이용한 비동기처리

```javascript
function isPositive(number, resolve, reject) {
  setTimeout(() => {
    if (typeof number === "number") {
      //성공 -> resolve
      resolve(number >= 0 ? "양수" : "음수");
    } else {
      //실패 -> reject
      reject("주어진 값이 숫자형 값이 아닙니다");
    }
  }, 2000);
}

isPositive(
  [],
  (res) => {
    console.log("성공적으로 수행됨:", res);
  },
  (err) => {
    console.log("실패 하였음:", err);
  }
);
```

#### useReducer()

- 컴포넌트의 상태 업데이트 로직을 컴포넌트에서 분리하기위해 사용
- state 는 우리가 앞으로 컴포넌트에서 사용 할 수 있는 상태를 가르키게 되고, dispatch 는 액션을 발생시키는 함수라고 이해하면된다.
- initialState는 초기 상태값

```javascript
const [state, dispatch] = useReducer(reducer, initialState);
```

#### useCallback()

- 함수를 랜더를 계속안시키려고 쓴다고봄
- useCallback( e => {},[배열] ) , 배열의 상태가변할때에만 render된다!

```javascript
const onChange = useCallback(
  (e) => {
    const { name, value } = e.target;
    setInputs({
      ...inputs,
      [name]: value,
    });
  },
  [inputs]
);
```

#### Context API

- Context 를 만들 땐 다음과 같이 React.createContext() 라는 함수를
  사용한다 쿠크르삥뽕.
- createContext 의 파라미터에는 Context 의 기본값을 설정할 수 있다. 여기서 설정하는 값은 Context 를 쓸 때 값을 따로 지정하지 않을 경우 사용되는 기본 값 입니다.

```javascript
const UserDispatch = React.createContext(null);
```

- Context 안에 Provider 라는 컴포넌트가 들어있는데 이 컴포넌트를 통하여 Context 의 값을 정할 수 있따. 이 컴포넌트를 사용할 때, value 라는 값을 설정해주면 된다임마

```javascript
<UserDispatch.Provider value={dispatch}>...</UserDispatch.Provider>
```

- 이제사용할 컴포넌트로 이동해서 요런식으로 짜라란 하면 props안넘겨받아도전역적으로 사용가능하다라구라구라굴아

```javascript
 const dispatch = useContext(UserDispatch);

 onClick={() => {
          dispatch({ type: 'TOGGLE_USER', id: user.id });
        }}
```

---

#### 콜백지옥 Promise로 처리하기

- Promis 객체를 이용하면 비동기처리를 호출하는 코드와 결과를 처리하는코드를 분리 할 수있다.

```javascript
function taskA(a, b) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const res = a + b;
      resolve(res);
    }, 3000);
  });
}

function taskB(a) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const res = a * 2;
      resolve(res);
    }, 1000);
  });
}

function taskC(a) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const res = a * -1;
      resolve(res);
    }, 2000);
  });
}

const bPromiseResult = taskA(5, 1).then((a_res) => {
  console.log("a결과:", a_res);
  return taskB(a_res);
});

console.log("adasdasdasdasd"); //중간에 코드 껴넣을수 있다.

bPromiseResult
  .then((b_res) => {
    console.log("b결과:", b_res);
    return taskC(b_res);
  })
  .then((c_res) => {
    console.log("c결과:", c_res);
  });
```

---

#### Mount, Unmount

```javascript
const UnmountTest = () => {
  useEffect(() => {
    console.log("Mount!");

    return () => {
      //Unmount 시점에 실행되게됨
      console.log("Unmount!");
    };
  }, []);
  return <div>Unmount Testing Component</div>;
};
```

#### 동기 비동기 체크하기

#### Memoization , useMemo()

```javascript
// useMemo(() => {},[이곳이바뀌면  useMemo실행])
const getDiaryAnalysis = useMemo(() => {}, [data.length]);
```

#### React.memo 함수형 컴포넌트에게 업데이트 조건을 걸자.

- React.memo는 고차 컴포넌트(Higher Order Component)입니다.
- 고차 컴포넌트는 컴포넌트를 가져와 새 컴포넌트를 반환하는 함수입니다.
- React는 컴포넌트를 렌더링하지 않고 마지막으로 렌더링된 결과를 재사용합니다.

```javascript
const MyComponent = React.memo(function MyComponent(props) {
  /* props를 사용하여 렌더링 */
});

ex))
const User = React.memo(function User({ user, onRemove, onToggle }) {
  return (
    <div>
    </div>
  );
});
```

---

#### 페이지 라우팅 Page Routing

- ROUTER -> 데이터의 경로를 실시간으로 지정해주는 역할을 하는 무언가
- ROUTING -> 경로를 정해주는 행위 자체와 그런 과정들을 다 포함하여 일컫는 말
