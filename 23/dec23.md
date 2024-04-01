TIL
===
12월
---
## 2023년 12월 22일

### ***JavaScript***

## 구동원리

JavaScript + CSS + HTML

JavaScript 와 CSS를 HTML이 불러와서 브라우저에서 실행
   
## const 변수 선언

    재선언 X, 재할당 X

정해진 상수를 이용할떄 사용  

예시)
```javascript
const a = b;
const a = c;
//재선언 금지

const a = b;
a = c;
//재할당 금지
```

## 길이가 긴 변수를 선언시 *Camelcase* 이용하기

    ex. VeryLongVariableName

    cf. Python에서는 very_long_variable_name 을 이용


## **let** 변수 선언

    재선언 X, 재할당 O

디폴트로 const 사용하고, let은 Variable 을 업데이트를 할때 사용

예시)  
```javascript
let a = b;
let a = c;
//재선언 금지

let a = b;
a = c;
//재할당은 가능
```

## Var 변수 선언
    재선언 O, 재할당 O 

왠만하면 사용하지 않고 let과 const로 나누어 쓰기(옛날언어)  

예시)  
```javascript
var a = b;
var a = c;
a = d;
//재선언, 재할당 가능
```

## Boolean ( true or false )
 - `null` - nothing
 - `undefined` - 값이 없음
 - `true`
 - `false`

## Array
- `[]` : Array 생성
```javascript
const daysOfWeek = ["mon","tue","wen","thu","fri","sat","sun"];

console.log(daysOfWeek);
```

`" "` 안에 표현하면, 따로 `const` 정의 하지 않아도 됨.

만약 Array 안의 하나의 Variable을 원한다면 `[ ]` 안에 입력하면 됨  

***cf) Array는 0 부터 시작 유의 할것***

```javascript
//[4] 같은 숫자로 Array 출력
console.log(daysofWeek[4]);
```

- Array에 하나 집어 넣고 싶을때  `.push` 이용하기

```javascript
const daysOfWeek = ["mon","tue","wen","thu","fri","sat"];

console.log(daysOfWeek);

daysOfWeek.push("sun");

console.log(daysOfWeek);
```

## Objects

Array 안에 객체를 만들어서 더 직관적으로 만들 수 있음  
다음은 `player` 라는 Object 를 만들어 각 변수를 저장함

```javascript
const player = {
    name: "Someding",
    points: 10,
    fat: true,
};

console.log(player); //player object 출력
```

`player.fat` 처럼 `const` 에 포함된 변수들도 하나의 `object`를 변경한 것은 아니기 때문에 가능함

`player.lastName` 과 같이 `player.` 뒤에 정의하지 않은 변수를 적어 `const`에 추가 할 수도 있음

```javascript
player.fat = false; //여기의 constant는 boolean 처리 되기 때문에 const 여도 수정 가능
player.lastName = "kim"; //object에 새로운 것을 추가 할 수 있음
console.log(player.name);
```

다음 코드를 이용하면 `player.points` 의 변수를 체크 할 수도 있음
```javascript
player.points = player.points + 15;
console.log(player.points);
```

## Functions

function 을 제작해서 과정을 줄일 수 있다.

function을 통해 argument를 보낼때는 `()` 안에 집어 넣으면 된다.

```javascript
function sayHello() {
    console.log("Hello my name is C");
}

sayHello("someding");
//argument 
```

function을 통해서 값을 집어넣을때는 function을 정의할 떄 값으로 할 단어를 적고 argument를 보낼때 괄호 안에 넣는다.

다음 코드로 사람의 이름과 나이를 각각 저장 할 수 있다.

```javascript
function sayHello(nameOfPerson, age) {
    console.log("Hello my name is " + nameOfPerson + "  and I am" + age);
}

sayHello("Someding", 22);
sayHello("dal", 20);
sayHello("Flynn", 21);
```

function값은 function안에서만 존재한다


function을 이용해서 `otherPersonsName`을 정의후
`console.log()`와 같은 형태의 `player.sayHello`를 만들었다.  

```javascript
const player = {
    name: "someding",
    sayHello: function(otherPersonsName) {
        console.log("hello" + otherPersonsName + " nice to meet you");
    },
};

console.log(player.name);
player.sayHello("lynn");
```

## Return
`return` 을 통해 function 값의 결과값을 정의 할 수 있다.

```javascript
const age = 96;

function calculateKrAge(ageOfForeigner){
  return ageOfForeigner + 2;
}

const krAge = calculateKrAge(age);

console.log(krAge);
```
여기에서는 결과 값으로 96 + 2 인 98을 출력한다.  
만약 `return` 에 `"Hello"` 가 입력되면, 그대로 `"Hello" 를 출력한다.

- `console.log`를 이용하지 않고, 간단한 계산기 만들기

```javascript
 const calculator = {
    plus: function (a, b) {
        return a + b;
    },
    us: function (a, b) {
        return a - b;
    },
    times: function (a, b) {
        return a * b;
    },
    divide: function (a, b) {
        return a / b;
    },
    power: function (a, b) {
        return a ** b;
    },
};

const plusResult = calculator.plus(2, 3);
const minusResult = calculator.minus(2, 3);
const timesResult = calculator.times(2, 3);
const divideResult = calculator.divide(2, 3);
const powerResult = calculator.power(2, 3);

console.log(plusResult);
```

## 2023년 12월 23일

## `prompt` 와 `parseInt`로 타입을 바꾸기

- `prompt` : 팝업창을 띄울 수 있음. 단, 예전 언어 임으로 거의 사용하지 않음

    `prompt` 에서 뭔가를 적으면 `string` 형태로 저장됨

    타입을 변경하는 방법을 알아보자.  

- `parseInt` : `"15"` 라는 string을 `15` 라는 `number` 로 저장 할 수 있다.

    ```javascript
    const age = prompt("How old are you");

    console.log(age, parsInt(age)); //prompt 에 입력한 숫자 string, number 출력
    ```

## 값의 type를 T/F 로 파악하기
  - `isNaN()` : Number 의 유무를 `Boolean` 출력 

## Conditionals (조건문)

- `if` 문을 이용하여 조건문 표현
```javascript
if(condition){
 // condition 이 true
} else {
// condition 이 false
}
```

- 예시 : 나이를 입력 받고 숫자가 아니면 `if` 안을 실행하고, 숫자라면 나이가 18세 이상인지 이하인지 체크하는 코드

```javascript
const age = parseInt(prompt("How old are you?"));

if (isNaN(age)) {
    console.log("Please write a number");
} else if (age < 18) {
    console.log("You are too young");
} else (age > 18) {
    console.log("You can drink");
}
```

## 논리 연산자

    true || true === true
    false || true === true
    true || false === true
    false || false === false


    true && true === true
    false && true === false
    true && false === false
    false && false === false


## The Document Object

- console에 `document`를 입력하면, 작성한 HTML을 가져올 수 있다.

-  document 가 HTML을 보여준다.
- JavaScript에서 HTML document 객체로부터 항목을 가지고 올 수 있다. (JavaScript는 HTML 읽을 수 있다. ) 읽고, 변경도 가능


```javascript
document.title = "//이름"
```

으로 `document`의 `title`을 javascript 에서 변경 할 수 있다
Javascript 는 HTML을 이용할 수 있다


## HTML in JavaScript

1. document 라는 객체는 JS에서 HTML파일을 불러올 수 있도록 도와준다
2. document의 함수 중에는 getElementById 라는 함수가 있는데, 이 함수가 HTML에서 id를 통해 element를 찾아준다  

ex)
```javascript
document.getElementedById("idname")
```

## Searching For Elements

- `getElementsByClassName()` : 많은 element를 가져올때 씀(array를 반환)

```javascript
const helos = document.getElementsByClassName("Hello")
```

- `getElementsByTagName()` : name을 할당할 수 있음(array를 반환)

```javascript
const title = document.getElementsByTagName("h1");
```
- `querySelector` : element를 CSS selector 방식으로 검색할 수 있음 (ex. h1:first-child)
단 하나의 element를 return해줌
⇒ hello란 class 내부에 있는 h1을 가지고 올 수 있다(id도 가능함)
- `querySelector`는 첫번째 element만 가져옴
- 조건에 맞는 세개 다 가져오고 싶으면 `querySelectorAll`
⇒ 세개의 h1이 들어있는 array를 가져다 줌
- `querySelector("#hello);` 와 `getElementById("hello");` 는 같은 일을 하는 것임

```javascript
const title = document.querySelector("#hello"); //#을 통해 Id 임을 명시해야함
const title = document.getElementById("hello");

//둘은 같은 코드이다.
```
하지만 후자는 하위요소 가져오는 것을 못하므로 전자만 쓴다.

## Events pt.1

 - 지금 js파일이 있기 때문에 js를 통해 html의 내용을 가져올 수 있는 거임
- document가 html이 js파일을 load하기 때문에 존재 → 그 다음에 browser가 우리가 document에 접근할 수 있게 해줌
- element의 내부를 보고 싶으면 `console.dir()`
기본적으로 object로 표시한 element를 보여줌(전부 js object임)
그 element 중 앞에 on이 붙은 것들은 event임
- `event` : 어떤 행위를 하는 것
모든 event는 js가 listen할 수 있음
- `eventListener` : event를 listen함 → js에게 무슨 event를 listen하고 싶은 지 알려줘야 함
- `title.addEventListener("click")` : 누군가가 title을 click하는 것을 listen할 거임 → 무언가를 해줘야함  
  

클릭하면 검정색 글자가 파란색 글자로 바뀌는 프로그램

```javascript
const title = document.querySelector("div.hello:first-child h1");

function handleTitleClick(){
title.style.color = "blue";
}
title.addEventListener("click",handleTitleClick);
//click하면 handleTitleClick이라는 function이 동작하길 원함
//그래서 handle~ 함수에 () 를 안넣은 것임
//즉, js가 대신 실행시켜주길 바라는 것임!
```

- function이 js에게 넘겨주고 유저가 title을 click할 경우에 js가 실행버튼을 대신 눌러주길 바라는 것이다.
- 함수에서 ( ) 이 두 괄호를 추가함으로써 실행버튼을 누를 수 있다.

## Events pt.2

`function` 뒤에 입력하기  

```javascript
const title = document.querySelector("div.hello:first-child h1");

console.dir(title);
function handleTitleClick() {
    title.style.color = "blue";
} //눌렀을떄

function handleMouseEnter() {
    title.innerText = "Mouse is here!"
} //입장했을때

function handleMouseLeave(){
    title.innerText = "Mouse is gone!"
} //떠났을때

title.addEventListener("click", handleTitleClick);
title.addEventListener("mouseenter", handleMouseEnter);
title.addEventListener("mouseleave", handleMouseLeave);
```  

- `handleTitleClick()` : 클릭 했을 떄 ~
- `handleMouseEnter()` : 글자에 가져다 댔을 때 ~
- `handleMouseLeave()` : 글자에서 떠났을때 ~
- `addEventListener()` : 리스너를 추가 ~


- 방법1 : `title.addEventListener("click", handleTitleClick);`

- 방법2 : `title.onclick = handleTitleClick`

방법1을 선호하는 이유는 나중에 `.removeEventListener`을 할 수 있기 때문  

## ✓ Window Events

* `resize` :  resize 를 통해서 창이 줄어들거나 느는 것을 감지 할 수 있음

```javascript
function handleWindowResize(){
    //Resize 됐을때
}

window.addEventListener("resize", handleWindowResize);
```

- `copy` : copy를 통해서 복사 된 것을 감지 할 수 있음

```javascript
function handleWindowCopy() {
    //Copy 됐을때
}

window.addEventListener("copy", handleWindowCopy);
```

- `online` & `offline` : wifi 연결의 유무를 감지 할 수 있음

```javascript
function handleWIndowOffline() {
    //Offline 일때
}

window.addEventListener("offline", handleWindowOffline);
```

그외에도 많은 기능이 있음   
[👍 기능체크링크](https://developer.mozilla.org/ko/docs/Web/API/HTMLElement)

## CSS in JavaScript

클릭 할 때 마다 파란색과 토마토색을 왔다갔다 하게 하는 코드
```javascript
function handleTitleClick() {
    if(h1.style.color === "blue") {
        h1.style.color = "tomato";
    } else {
        h1.style.color = "blue";
    }
}

h1.addEventListener("click", handleTitleClick);
```

이 코드 보다 더 짧게 코딩 하기 위해서는 `currentColor` 를 이용한다

`currentColor` : 현재 색깔을 저장 할 수 있음
```javascript
const h1 = document.querySelector("div.hello:first-child h1");

console.dir(h1);
function handleTitleClick() {
    const currentColor = h1.style.color;
    let newColor;
    if(currentColor === "blue") {
        newColor = "tomato";
    } else {
        newColor = "blue";
    }
    h1.style.color = newColor;
}

h1.addEventListener("click", handleTitleClick);
```

보통 CSS 를 JavaScript 코드에 섞어 쓰는 걸 선호 하지 않음 따로 분리 하는 것 중요함.

## 🎅2023년 12월 25일

css)
```css
transition: color 0.5s ease-in-out;
```

을 통해 자연스럽게 변하게 할 수 있음

JS)
```js
if (h1.className === "active") {
        h1.className = "";
    } else {
        h1.className = "active"
    }
```

을 통해 `body` 안의 `class` 이름을 변경 할 수 있다.

```js
//JS 작성시 오타 방지

const clickedClass = "clicked"
```

JS 작성시에 `const`를 선언하고 선언한 `const` `clickedClass`를 삽입하는 형태로 오타 및 오류를 방지 할 수 있다.

- `classList`  

`className`은 과거 `class`를 신경 쓰지 않고 교체 해버리지만, `classList`는 class들의 목록으로 작업 할 수 있게함

```js
if (h1.classList.contains(clickedClass)) {
        h1.classList.remove(clickedClass);
    } else {
        h1.classList = add(clickedClass);
    }
```

`classList.remove()` : classList에서 ()안을 제거

`classList.contains()` : classList에서 ()을 가지고 있을때,

`classList.add()` : classList에 ()안을 추가

- `.toggle` function

`toggle`은 특정 class name이 존재하는지만 확인하는 역할을 한다.

```js
if (h1.classList.contains(clickedClass)) {
        h1.classList.remove(clickedClass);
    } else {
        h1.classList.add(clickedClass);
    }
```

이 코드를  `toggle` 을 이용해서 짧게 표현 할 수 있다.

```js
h1.classList.toggle("clicked")
```

해석 :  `classList`에 `clicked`가 존재하지 않으면 `clicked`를 `classList`에 추가한다.

## Input Value

HTML)

- 인풋 생성하기

```html
<input type="text" placeholed="what is your name?"/>
```

- 버튼 생성하기
```html
<button>Log In</button>
```

JS)

```js
const loginInput = document.querySelector("#login-form input");
const loginButton = document.querySelector("#login-form button");

function onLoginBtnClick() {
    console.dir(loginInput); //loginInput 을 확인 할 수 있다
    console.log("click"); //클릭 표시
}
loginButton.addEventListener("click", onLoginBtnClick);
```

-`.value`

`value` function를 이용해서 `input value`를 저장 할 수 있다

```js
function onLoginBtnClick() {
    console.log("hello", loginInput.value); // 입력받은 loginInput value 앞에 hello 를 추가 하는 코드
}

loginButton.addEventListener("click", onLoginBtnClick);
```

다음 코드를 이용해서 login에 입력한 value를 알 수 있다.

## Input 값의 유효성을 검사하기

`logInValue` 에 공백을 입력 할 경우,
```js
const value = loginInput.value;
if(value === "") {
        alert("이름을 입력해주세요"); //공백을 입력하면 alert 출력
    }
```

를 `function` 안에 넣어서 공백을 입력하면 `alert` 를 출력하도록 할 수 있다.

```js
const loginInput = document.querySelector("#login-form input");
const loginButton = document.querySelector("#login-form button");

function onLoginBtnClick() {
    const value = loginInput.value;
    if(value === "") {
        alert("이름을 입력해주세요"); //공백을 입력하면 alert 출력
    } else if(value.length > 15) {
        alert("이름이 너무 깁니다. 15글자 이상입니다");//15글자 이상이면 alert 출력
    }
}
loginButton.addEventListener("click", onLoginBtnClick);
```

입력받은 value 값이 15글자 이상이거나 공백일때 `alert`를 출력하는 코드 이다.

위의 코드를 이용하여 JS에서 글자수를 제한하고, 공백일떄 제한하는 방법도 있지만,

HTML 의 `form` 을 이용해 브라우저의 기본 기능을 이용하는 것이 더 안전하고, 좋은 코드 이다. 이를 이용하려면 HTML 의 `body` 안에 `form`을 입력하면 된다.  

HTML)
```html
<form id="login-form">
        <input
        required
        maxlength="15" 
        type="text" 
        placeholed="what is your name?"
        />
        <button>Log In</button>
      </form>
```

`form`이 `submit` 됐는지 여부만 파악하는게 중요하다.

모든 eventListener function 의 첫번째 argument는 항상 지금 막 벌어진 일에 대한 정보를 준다.

eon7500님의 정리

    function onLoginSubmit(event){
    event.preventDefault(); // 브라우저가 기본 동작을 실행하지 못하게 막기 // event object는 preventDefault함수를 기본적으로 갖고 있음
    console.log(event);
    }
    loginForm.addEventListener("submit", onLoginSubmit); // submit 이벤트가 발생한다면, onLoginSubmit함수를 실행시킨다는 의미 // JS는 onLoginSubmit함수 호출시 인자를 담아서 호출함. 해당 인자는 event object를 담은 정보들

    ★ 중요 ★
    form을 submit하면 브라우저는 기본적으로 페이지를 새로고침 하도록 되어있다. << 우리가 원하는 것이 아님!
    preventDefault() 함수를 추가함으로써 브라우저의 기본 동작을 막을 수 있다!!

    이 preventDefault 함수는 EventListener 함수의 '첫 번째 argument' 안에 있는 함수이다. 첫 arument는 지금 막 벌어진 event들에 대한 정보를 갖고 있다.
    JS는(기본적으로)argument를 담아서 함수를 호출하는데, 이 argument가 기본 정보들을 제공하고 있다. ex) 누가 submit주체인지, 몇 시에 submit을 했는지 등등 콘솔에 출력해보면 알 수 있음


HTML)
- `href` 를 이용하여 앵커 걸기
```html
<a href="https://github.com/somedding">Go to Github</a>
```

## 2023년 12월 28일

```js
onst loginForm = document.querySelector("#login-form");
const loginInput = document.querySelector("#login-form input");

const link = document.querySelector("a");
function onLoginSubmit(event) {
    const username = loginInput.value;
    console.log(username);
}

function handleLinkClick() {
    alert("clicked");
}

loginForm.addEventListener("submit", onLoginSubmit);
link.addEventListener("click", handleLinkClick); // 링크를 누르면 handleLinckClick을 실행한다.
```
- `preventDefault()` : 이 코드를 이용하면 링크를 하려는 브라우저를 막을 수 있다.

CSS
```css
.hidden {
    display: none;
}
```

HTML
```html
//html
<form id="login-form" class="hidden">
```

CSS에 `diplay: none;`을 추가하고, HTML에 `hidden` 클래스를 넣으면 Log IN 창을 HTML에서 삭제 하지 않고도, CSS 선에서 안보이게 할 수 있다.

이를 이용하여 사용자가 로그인 버튼을 클릭 했을때 로그인 창이 없어지게 만들 수 있다.

```js
function onLoginSubmit(event) {
    event.preventDefault();
    const username = loginInput.value;
    loginForm.classList.add("hidden"); //class 에 hidden class 추가
    console.log(username);
}
```

html
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link rel="stylesheet" href="style.css">
        <title>Momentum App</title>
    </head>
    <body>
      <form id="login-form">
        <input
            required
            maxlength="15"
            type="text"
            placeholder="What is your name?"
        />
        <input type="submit" value="Log In"/>
      </form>
      <h1 id="greeting" class="hidden"></h1>
      <script src="app.js"></script>
    </body>
</html>
```
css
```css
.hidden {
    display: none;
}
```
js
```js
const loginForm = document.querySelector("#login-form");
const loginInput = document.querySelector("#login-form input");
const greeting = document.querySelector("#greeting");

const HIDDEN_CLASSNAME = "hidden";

function onLoginSubmit(event) {
    event.preventDefault();
    loginForm.classList.add(HIDDEN_CLASSNAME);
    const username = loginInput.value;
    greeting.innerText = "Hello " + username; //더 직관적으로 표현 가능
    greeting.classList.remove(HIDDEN_CLASSNAME);
}

loginForm.addEventListener("submit", onLoginSubmit);
```
string을 두개로 합치는 과정에서 아래 두개의 코드 모두 같은 것을 의미한다

```js
greeting.innerText = "Hello " + username;
greeting.innerText = `Hello ${username}`;
```

두번째 방법을 이용할려면 `${}` 만 이용하면 된다. 주의 해야 할 점은 ` 이것을 이용하야 한다. ' 이 아닌 

## 2023년 12월 29일

## LOCALSTORAGE

LocalStorage는 브라우저에서 제공하는 기본 로컬 저장소이다.  


[👍 기능체크링크](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)

- `localStorage.setItem()` :

```js
localStorage.setItem("username", "someding")
```

을 이용하면 원하는 값을 Local Storage 에 저장 할 수 있다.

두번 이상 코드가 겹칠때는 function을 만들어주는 것도 방법이다.

```js
const loginForm = document.querySelector("#login-form");
const loginInput = document.querySelector("#login-form input");
const greeting = document.querySelector("#greeting");

const HIDDEN_CLASSNAME = "hidden";
const USERNAME_KEY = "username"

function onLoginSubmit(event) {
    event.preventDefault();
    loginForm.classList.add(HIDDEN_CLASSNAME);
    const username = loginInput.value;
    localStorage.setItem(USERNAME_KEY, username);
    greeting.innerText = `Hello ${username}`;
    greeting.classList.remove(HIDDEN_CLASSNAME);
}

const savedUsername = localStorage.getItem("username");

if (savedUsername === null) {
    loginForm.classList.remove(HIDDEN_CLASSNAME);
    loginForm.addEventListener("submit", onLoginSubmit);
} else {
    greeting.classList.remove(HIDDEN_CLASSNAME);
    greeting.innerText = `Hello ${savedUsername}`;
}
```