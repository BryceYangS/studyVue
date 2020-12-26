### viewport

- html의 메타 태그
- 반응형 웹이라는 것을 명시하는 메타 태그

### scoped

- 해당 component에 한정 적용되도록 함

```html
<style scoped>
  h1 {
    color: #2f3b52;
    font-weight: 900;
    margin: 2.5rem 0 1.5rem;
  }
</style>
```

### localStorage

```js
localStorage.setItem(key, value);
```

- JSON.stringfy() : JSON 객체를 string 변환
- 객체를 바로 넣을 경우 개발자 도구에서 [object Object]로 출력되기 때문에 값을 확인할 수 없음

- `window.localStorage` 를 통해 저장된 값을 볼 수 있음
- 또는, 크롬 개발자 도구의 Application 탭의 Local Storage를 통해 확인 가능

### ul>li\*3

```html
ul>li*3
```

- `<ul>` 태그 하위 `<li></li>`태그 3개 자동 완성

### JSON.stringify(obj)

```js
var obj = { competed: false, item: this.newTodoItem };
localStorage.setItem(this.newTodoItem, JSON.stringify(obj));
```

- JSON.stringfy() : JSON 객체를 string 변환
- 객체를 바로 넣을 경우 개발자 도구에서 [object Object]로 출력되기 때문에 값을 확인할 수 없음

### v-bind

```
v-bind:내려보낼 프롭스 속성이름="현재 위치의 컴포넌트 데이터 속성"
```

### v-on

```
v-on:하위 컴포넌트에서 발생시킨 이벤트 이름 검색="현재 컴포넌트의 메서드 명"
```

### emit

```
this.$emit('이벤트이름', 인자1, 인자2, ...);
```

### slot

> 특정 컴포넌트의 일부 UI를 재사용할 수 있는 기능

### @click

- `v-on:click` 과 동일

## ES6

- ECMAScript 2015
- Babel
  - ES6를 지원하지 않는 브라우저를 위해 transpiling 지원
  - ES6의 문법을 각 브라우저 호환 가능한 ES5로 변환

## ES5

1. 변수의 Scope

- `{ }`에 상관 없이 스코프가 설정됨

```js
var sum = 0;
for (var i = 0; i <= 5; i++) {
  sum += i;
}
console.log(sum); // 15
console.log(i); // 6
```

2. 호이스팅

- 선언한 함수와 변수를 해석기가 가장 상단에 있는 것처럼 인식
- js 해석기는 코드의 라인 순서와 관계없이 함수선언식과 변수를 위한 메모리 공간을 먼저 확보
- `function a()`와 `var`는 코드의 최상단으로 끌어 올려진 것처럼 보임

```js
function willBeOveridden() {
  return 10;
}
willBeOveridden(); //5
function willBeOveridden() {
  return 5;
}
```

### ES6

- `{ }` 범위 정해짐

```js
let sum = 0;
for (let i = 0; i <= 5; i++) {
  sum += i;
}
console.log(sum); // 15
console.log(i); // 에러 발생
```

- `const`로 지정한 값 변경 불가능
  - But, 객체나 배열의 내부는 변경 가능

```js
const a = 10;
a = 20; //에러
```

```js
const a = {};
a.num = 10;
console.log(a); // {num: 10}

const a = [];
a.push(20);
console.log(a); // [20]
```

#### Arrow Function - 화살표 함수

- 함수를 정의할 때 `function` 키워드 대신 `=>`로 대체
- 콜백 함수의 문법을 간결과

```js
// ES 5
var sum = function (a, b) {
  return a + b;
};

// ES 6
var sum = (a, b) => {
  return a + b;
};
```

#### Enhanced Object Literals

- 객체의 속성을 메서드로 사용할 때 `function` 예약어를 생략하고 생성 가능

```js
var dictionary = {
  words: 100,
  // ES 5
  lookup: function () {
    console.log("find words");
  },
  //ES 6
  lookup() {
    console.log("find words");
  },
};
```

- 객체의 속성명과 값 명이 동일할 때 아래와 같이 축약 가능

```js
var figures = 10;
var dictionary = {
  // figures: figures;
  figures;
}
```

#### Modules - 자바스크립트 모듈화 방법

- 자바스크립트 모듈 로더 라이브러리(AMD, Commons JS)기능을 ES6부터는 js언어 자체에서 지원
- 호출되기 전까지는 코드 실행과 동작을 하지 않는 특징이 있음

```js
// libs/maths.js
export function sum(x, y) {
  return x + y;
}
export var pi = 3.141593;

// main.js
import { sum } from "libs/math.js";
sum(1, 2);
```

- Vue.js 에서 `default` export 자주 사용
  - default : 한 개의 파일에서 하나만 export 가능

```js
// util.js
export default function (x) {
  return console.log(x);
}

// main.js
import util from "util.js";
console.log(util); // function(x) {return console.log(x);}
util("hi");

// app.js
import log from "util.js";
console.log(log);
log("Hi");
```
