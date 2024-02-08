# 2024 1월 Javascript css html

## Intervals
```js
setInterval(sayHello, 5000); //sayHello 함수를 5초에 한번 실행하라
```

`setInterval` 을 이용하면 계속 확인 해야하는 프로그램을 짤 수 있다 ("주식 등등")

## Timeouts
```js
setTimeout(sayHello, 5000); //sayHello 함수를 5초에 한번 실행하라
```

## Date( )
`date( )` : 이미 정의 되어있는 함수 이다.

`date.getDate()` :   
`date.getDay()` : 요일  
`date.getHours()` : 시  
`date.getMinutes()` : 분  
`date.getSeconds()` : 초  

더 많은 기능은 사이트에서 확인 가능

```js
//clock.js
const clock = document.querySelector("h2#clock");

function getClock() {
    const date = new Date();
    console.log(`${date.getHours()}:${date.getMinutes()}:${date.getSeconds()}`)
}

getClock() //시작하자마자 1초를 기달리지 않고 출력하는 것
setInterval(getClock, 1000);
```
이 코드를 이용하면 시간을 받을 수 있다.
직관 적으로 창에서 시간을 받기 위해서 코드를 수정하면 

```js
const clock = document.querySelector("h2#clock");

function getClock() {
    const date = new Date();
    clock.innerText = `${date.getHours()}:${date.getMinutes()}:${date.getSeconds()}`;
}

getClock()
setInterval(getClock, 1000);
```
## padStart( )

```js
"1".padStart(2,"0")
```
길이가 2가 아니라면 0을 추가 한다

이를 이용하여 위의 코드에서 0초 가 00초 로 보이게 만들 수 있다.

```js
const clock = document.querySelector("h2#clock");

function getClock() {
    const date = new Date();
    const hours = String(date.getHours()).padStart(2, "0");
    const minutes = String(date.getMinutes()).padStart(2, "0");
    const seconds = String(date.getSeconds()).padStart(2, "0");
    clock.innerText = `${hours}:${minutes}:${seconds}`;
}

getClock()
setInterval(getClock, 1000);
```

## Math

`Math.pi` : pi 값을 출력

`Math.random()` : 랜덤한 값을 출력  
`Math.random() * 10` : 10까지의 랜덤한 값을 출력

`Math.round()` : 소수점 뒤 자리를 다 지워버림  
`Math.ceil()` : 소수점 뒤 자리를 모두 올림  
`Math.floor()` : 소수점 뒤 자리를 모두 내림  

```js
const quote = document.querySelector("#quote span:first-child");
const author = document.querySelector("#quote span:last-child");
const todaysQuote = quotes[Math.floor(Math.random() * quotes.length)];

quote.innerText = todaysQuote.quote;
author.innerText = todaysQuote.author;
```

다음 을 이용해서 랜덤한 quotes 를 출력하는 코드를 작성 할 수 있다.

    두번 이상 이용되면 따로 const 만들기

## 백그라운드 이미지 만들기

```js
const bgImage = document.createElement("img"); 

bgImage.src = `img/${chosenImage}`;
```

이 코드를 이용해서  자바스크립트 로 html에 img 요소를 추가 할 수 있다.

## TO-Do List 만들기

 html
1) Todo-list 를 만들기를 원하니 html 에 form 태그로 구조를 만들어 준다. 나중에 JavaScript에서 만지기 쉽게 id는 todo-form으로 설정
2) form 자체는 submit이라는 기본 기능을 내장하는 하나의 묶음 밖에 되지 않는다. 우리는 이용자가 todo-list 에 무언가 기입하는 것을 원하기 때문에 form 태그 안에 input 태그를 넣어 'text'를 타이핑할 수 있는 기능을 추가한다.
3) 그 밑에 ul 태그를 생성하여 todo-list에 작성 된 text가 저장 및 나열될 수 있게 한다.

 JavaScript
1) 앞에 html에서 만든 구조 3가지 ('todo-form', 'todo-form 안의 input', 'todo-list') 에 접속하기 위해 항상 길게 타이핑하는 것은 비효율적이므로 단축을 위해 각각 변수로 설정한다.
2) 이전 greeting 강의에서 form 태그에서의 event는 submit를 발생시키고, 브라우저는 기본값으로 설정되어 있는 새로고침을 하게 된다. 우리는 todo-list를 작성한다고 새로고침 되는 것을 원치 않기 때문에(todo-list를 1,000번 작성한다고 가정한다면 불필요한 새로고침이 1,000번 발생하고 1,000번의 랜덤한 이미지가 로드될 것이다. -> 데이터적으로 비효율적, 시각적으로 불편)
event.preventDefault() 로 기본값을 없애준다.
3) text 상자 안에 글을 작성하고 enter를 눌렀을 때 그 글이 초기화 되게 만들기 위해 toDoInput.value = ""; 을 통해 value를 빈 텍스트로 한다.
4) text 상자를 비게 하는 것은 좋은데 그 전에 이용자가 입력한 텍스트를 저장해야 나중에 ul태그 안에 사용할 수 있기 때문에 toDoInput.value = ""; 로 기입한 텍스트가 사라지기 이전에
const newTodo = toDoInput.value; 를 정의하여 기입한 텍스트가 newTodo라는 값에 저장되게 한다.
5) 앞의 세 가지 동작(기본값방지, 텍스트 저장, text상자비우기)는 한번에 이루어지는 세트이기때문에 효율성 및 편의를 위해 함수로 묶어준다.
function handleTodoSubmit() {
event.preventDefault();
const newTodo = toDoInput.value;
toDoInput.value = "";
}
6) todo-form 안에서 submit이 발생하는 특정 상황에서 함수handleTodoSubmmit을 실행 시키기 위해
toDoform.addEventListner("submit", handleTodoSubmit); 을 기입한다.
(함수 handleTodoSubmit이 항상 실행되고 있는 상태라면 text 창은 항상 비어있는 상태 일 것이기 때문에)