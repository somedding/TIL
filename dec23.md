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

dec 23

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