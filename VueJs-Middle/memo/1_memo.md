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
