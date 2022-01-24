# Udemy-react

유데미 한입크기로 잘라 먹는 리엑트 강의

#### 1일차

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
