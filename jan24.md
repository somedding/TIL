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

