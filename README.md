# gitignore_practice
gitignore 연습 및 push 연습


# javascript 필수 

```jsx
// typeof = type을 알려준다 

console.log(typeof 'gel'); //string
console.log(typeof 123); //number
console.log(typeof true); // boolean
console.log(typeof undefined) // undefined 의도하지 않은 비워놓은 값 
console.log(typeof null) // object 의도된 비워놓은 값
console.log(typeof {}); // 객체 데이터  [{}] object
console.log(typeof []); // 배열 데이터  object

// null , {} , [] function 으로 type 속까내기

function getType(data) {
  return Object.prototype.toString.call(data);
}

console.log(getType(null)); // [object Null]
console.log(getType({})); // [object Object]
console.log(getType([])); // [object Array]
```

```jsx
function getType(data) {
  return Object.prototype.toString.call(data).slice(7, -1);
}

console.log(getType(123)); // Number
console.log(getType(null)); // Null

// 원래는 [object Number]로 출력되는데 slice(7, -1)을 붙임으로써 짤라버린다
//[object Number]
//       v
//01234567890-1-2-3
```

# import 와 export 사용법

# 다른 파일에 function 파일 내보내기

## ❗️ (중요)getType.js 파일을 따로 만들고 내보내기 중 오류 발생

```jsx
export default function getType(data) {
  return Object.prototype.toString.call(data).slice(7, -1);
}

//export default 를 해줘서 function을 내보내 준다
// 다른 파일에서는 import로 받으면 되나 
// 이때 버전 때문인지는 모르겠지만 오류가 떴다 

```

<aside>
💡 ⭐️ **해결 방법** 
 index.js 안에 모든 <script src = ''  > 에 type = 'module'을 추가해준다

</aside>

```jsx
import getType from './getType';
// import 를 해주어 getType 가져오기

console.log(typeof 'gel');
console.log(typeof 123);
console.log(typeof true);
console.log(typeof undefined);
console.log(typeof null);
console.log(typeof {});
console.log(typeof []);

console.log(getType(123));
console.log(getType(null));
```

# 산술 연산자

```jsx
// 산술 연산자(arithmetic operator)

console.log(1 + 2); //3
console.log(5 - 7); //-2
console.log(10 * 10); // 100
console.log(10 / 5); //2
console.log(7 % 5); //2 나머지 값
```

# 할당 연산자

```jsx
// 할당 연산자

let a = 2;

console.log(a); //2
```

```jsx
let a = 2;
a = a + 1; // 재 할당

console.log(a); //3
```

### 위 명령어 간략화

```jsx
// 할당 연산자

let a = 2;
// a = a + 1;
a += 1; // 산술연산자가 다 가능 -,*,/ 등

console.log(a);
```

```jsx
// 비교 연산자(comparison operator)

const a = 1;
const b = 1;

console.log(a === b); // true , === 일치 연산자 , a와 b의 데이터는 type과  값이 똑같아야 true가 나옴
```

```jsx
// 비교 연산자(comparison operator)

const a = 1;
const b = 3;

console.log(a === b); //false , 값이 다름

```

```jsx
// 비교 연산자(comparison operator)

const a = 1;
const b = '123';

console.log(a === b); // false , type이 다름 
```

# 매개 변수는?

```jsx

// 비교 연산자(comparison operator)

const a = 1;
const b = 3;

console.log(a === b);

function isEqual(x, y) {
  return x === y;
}
// isEqual(x,y) isEqual 함수를 작동시 매개변수로 x,y 값을 받을 것인데 
console.log(isEqual(1, 1)); //true 출력
// 그 매개변수의 값은 x=1 , y=1

console.log(isEqual(2, '2')); // false 출력
```

# 같지 않다 ! ==

```jsx
// 비교 연산자(comparison operator)

const a = 1;
const b = 3;

console.log(a !== b); // true , 불일치 연산자
```

# 작다 <

```jsx
// 비교 연산자(comparison operator)

const a = 1;
const b = 1;

console.log(a < b); // false
```

# 작거나 or 크거나 같다

```jsx
// 비교 연산자(comparison operator)

const a = 7;
const b = 7;

console.log(a >= b); //true 
```

# ❗️ 꺽쇠 갈호는 앞에 배치되야 한다

만약 =<  ⇒ 이런식으로 적으면 오류가 난다 왜? 이런 문법은 없으니깐 ㅎㅎ

# 논리 연산자

```jsx
// 논리 연산자(logical operator)

const a = 1 === 1; // true
const b = 'AB' === 'AB'; //true
const c = true; //true

console.log(a);
console.log(b);
console.log(c);
console.log('&&: ', a && b && c);//and 연산자 &&: true엔퍼센트 모두가 참일때 true를 표시 
```

```jsx
// 논리 연산자(logical operator)

const a = 1 === 1; // true
const b = 'AB' === 'AB'; //true
const c = false; //false

console.log(a); //true
console.log(b); //true
console.log(c); //false

console.log('&&: ', a && b && c); //and 연산자 false
console.log('||: ', a || b); // or 연산자 true , 둘중 하나라도 true면 true
console.log('!: ', !a); // not 연산자 a= true 인데, !a = false 출력
```

```jsx
// 삼항 연산자(ternary operator)

const a = 1 < 2;

if (a) {
  console.log('참');
} else {
  console.log('거짓');
}

// 참 출력
```

## 삼항 연산자 코드의 단순화

```jsx
const a = 1 < 2;

if (a) {
  console.log('참');
} else {
  console.log('거짓');
}

console.log(a ? '참' : '거짓'); 
//참 ? 기준으로 앞부분이 즉 a가 참이면 : 앞부분 실행 그것이 아니면 뒷부분인 '거짓' 출력
```

### getRandom file

```jsx
export default function random() {
  return Math.floor(Math.random() * 10);
}
```

### Main.js

```jsx
// 조건문(If statement)
import random from './getRandom';

const a = random();

if (a === 0) {
  console.log('a is 0');
} else {
  console.log('rest...');
}
// 만약 a 가 0이랑 일치 하면 a is 0 을 출력 그게 아니면 rest...을 출력
// 현재 import 받아온 값은 getRandom에서 받아와 Math.floor(Math.random() * 10);
// floor는 소수점 밑에 자리는 짤라버린다 결국 Math.random()의 명령어는 랜덤한 숫자를 출력하는데 * 10을 해줘서
// 소수점 달린 정수로 출력하게 되고 floor에 의해 소수점은 짤리게 된다
```

 

```jsx
// 조건문(If statement)
import random from './getRandom';

const a = random();

if (a === 0) {
  console.log('a is 0');
} else if (a === 2) {
  //추가 조건
  console.log('a is 2');
} else {
  console.log('rest...');
}
// 만약 a 가 0이랑 일치 하면 a is 0 을 출력 그게 아니면 rest...을 출력
// 현재 import 받아온 값은 getRandom에서 받아와 Math.floor(Math.random() * 10);
// floor는 소수점 밑에 자리는 짤라버린다 결국 Math.random()의 명령어는 랜덤한 숫자를 출력하는데 * 10을 해줘서
// 소수점 달린 정수로 출력하게 되고 floor에 의해 소수점은 짤리게 된다
```

# 조건문에 Swich 문

### 위에 조건문을 swich로 바꿈

```jsx
// 조건문(If statement)
import random from './getRandom';

const a = random();

switch (a) {
  case 0:
    console.log('a is 0');
    break
  case 2:
    console.log('a is 2');
    break
  case 4:
    console.log('a is 4');
    break
	default:
		console.log('rest...');

	// else 대신 default를 써주는데 case와 같이 값을 적을 필요도 break를 걸어줄 필요도 없다
	// 물론 값을 써줘도 상관은 없다
}

// case 0이 맞으면 console.log('a is 0')을 출력하는데 break를 안걸어주면 계속 밑으로 내려가서
// 실행되게 된다고 하니 하니씩 break를 걸어주는 것이 좋다
```

```jsx
// 반복문 (For statement)
// for (시작조건; 종료조건; 변화조건) {}

for (let i = 0; i < 3; i += 1) {
  console.log(i); // 0 1 2
//let 변수를 선언하는데 재할당 가능한 변수
}
```

```jsx
// 반복문 (For statement)
// for (시작조건; 종료조건; 변화조건) {}

const ulEl = document.querySelector('ul');
console.log(ulEl);

for (let i = 0; i < 3; i++) {
  const li = document.createElement('li');

  li.textContent = `list-${i + 1}`;
  ulEl.appendChild(li);
  // 로직은, 1. 변수 li를 만들고 그 안에 li의 변수를 만들어 준다
  // 2. li라는 변수에 textContent로 `list-${i + 1}`를 넣어 주는데
  // 3. i = 0, 1, 2라는 값으로 +1을 해줘 1, 2, 3으로 만들어 준다 
  // 4. 다음 ulEl의 변수를 불러와 그 안에 appenChild로 윗쪽 li 변수를 해준다
  // 5. 변수를 선언하는데 재할당 가능한 변수
}
```

![스크린샷 2022-11-26 오후 5 54 07](https://user-images.githubusercontent.com/88579497/204081719-142c48b1-5c30-4cef-9528-bb92c74814cf.png)
![스크린샷 2022-11-26 오후 5 54 02](https://user-images.githubusercontent.com/88579497/204081722-c495dca9-c52e-48d7-90d0-2f60cfbfd2ea.png)


```jsx
// 반복문 (For statement)
// for (시작조건; 종료조건; 변화조건) {}

const ulEl = document.querySelector('ul');
console.log(ulEl);

for (let i = 0; i < 10; i++) {
  const li = document.createElement('li');

  li.textContent = `list-${i + 1}`;
  if ((i + 1) % 2 === 0) {
    li.addEventListener('click', function () {
      console.log((li.textContent = '류승환 웹 개자이너'));
    });
  } else {
    li.addEventListener('click', function () {
      console.log((li.textContent = '류승환 최고!'));
    });
  }
  ulEl.appendChild(li);

// if문 클릭한게 만약 i + 1의 %2가 === 0 즉 홀수면 '류승환 웹 개자이너' 출력 ! , 그게 아니면 '류승환 최고!'출력!
// 
}
```
![스크린샷 2022-11-26 오후 6 11 42](https://user-images.githubusercontent.com/88579497/204081726-7e0dcddf-0e9c-4a55-b210-30abfa92e890.png)
```jsx
//변수 유효범위(Varialble Scope)
//var, let, const

function scope() {
  if (true) {
    const a = 123;
    console.log(a);
  }
}

scope();
```

```jsx
//변수 유효범위(Varialble Scope)
//var, let, const

function scope() {
  if (true) {
    const a = 123;
    console.log(a);
  }
  console.log(a); // 선언되지 않았다
	// 유효 범위가 있는데 a라는 변수는 중괄호 안에서만 가능
}

scope();

//var 는 사용이 권장되지 않는데
```

```jsx
//변수 유효범위(Varialble Scope)
//var, let, const

function scope() {
  if (true) {
		console.log(a); // undefined
    const a = 123;
  }
  console.log(a); // 선언되지 않았다
	// 유효 범위가 있는데 a라는 변수는 중괄호 안에서만 가능
}

scope();

//var 는 사용이 권장되지 않는데

//let과 const는 블록(중괄호 부분) 레벨의 유효범위를 가진다

// var를 사용하면 var a =123 => 함수 레벨에 적용이 되어 함수 안에서는 어디서든 쓸수 있다
// 우리가 의도하지 않은 곳에서 사용할 수도 있고 메모리 누수로 이어질 수 있다 
```

```jsx
// 형 변환(Type conversion)

//데이터의type은 문자, 숫자, 객체가 있다

const a = 1;
const b = '1';

console.log(a === b); // false "타입이 다름"

// === 일치 연산자 , == 동등 연산자 type은 달라도 true가 나옴
// 동등 연산자는 되도록이면 안쓰는것을 추천 , 의도하지 않게 서로 다른 값이 같다라고 나와 오류를 생성할수 있다

```

```jsx
// 형 변환(Type conversion)

// Truthy(참 같은 값)
// true, {}, [], 1, 2, 'false', -12, '3.14' ...

// Falsy(거짓 같은 값)
// false,'', null, undefined, 0, -0, NaN => Not a Number
// falsy 값은 외워 주면 좋다 

if ('false') {
  console.log(123);
}
```	

# 화살표 함수	
	
```jsx
//화살표 함수
// ()=> {} vs function(){}

const double = function (x) {
  return x * 2;
};

console.log('double =', double(7));
// 'double ='이라는 문자열과, double()로 함수 실행

// 화살표 함수 = 기본적인 로직을 축약형으로 만들수 있다
const doubleArrow = (x) => {
  return x * 2;
};

console.log('doubleArrow=', doubleArrow(7));
```

# 화살표 함수 축약 하는 방법

```jsx
//화살표 함수 축약
// 매개 변수가 1개 일시 소괄호도 생략할 수 있다 

const doubleArrow = x => x * 2;

console.log('doubleArrow=', doubleArrow(7)); // 14 
```

```jsx
// 매개 변수가 2개 일때 축약형

const doubleArrow = (x, y) => (x * 2) / y;

console.log('doubleArrow=', doubleArrow(7, 10));
```

## 만약 축약할 때 객체 데이터와 중괄호가 겹칠때

```jsx
// 만약 객체 데이터를 만들 때는 중괄호{}를 사용하는데 겹쳐서 블록으로 해석된다
// 축약형에서는 객체 데이터{}와 기본 화살표 함수 로직에 들어가는 중괄호와 {}
// 겹치게 되는데 겹침 없이 객체 데이터를 만들고 싶으면 ({객체 데이터}) 로 만들어 주면 된다
const doubleArrow = (x) => {

};

console.log(doubleArrow);
```

```jsx
// 만약 객체 데이터를 만들 때는 중괄호{}를 사용하는데
// 축약형에서는 객체 데이터{}와 기본 화살표 함수 로직에 들어가는 중괄호와 {}
// 겹치게 되는데 겹침 없이 객체 데이터를 만들고 싶으면 ({객체 데이터}) 로 만들어 주면 된다

const doubleArrow = (x) => ({
  name: '류승환',
});

console.log(doubleArrow(name.text));
```

# IIFE

### 즉시 실행 함수

IIFE , Immediately-Invoked Function Expression

```jsx
const a = 7;
function double() {
  console.log(a * 2); //14
}

double();

// 만약 함수를 만들었는데 기본적으로 만들어서 한번 실행되고
// 쓸일이 없다면? 함수의 이름을 따로 만들어서 쓸 필요가 없다
// 이때 즉시 실행 함수를 쓰게 되는데
// 소괄호를 묶이게 되는데 뒤에 소괄호를 열고 닫아준다
(function () {
  console.log(a * 2);
})(); // 14
```

# 호이스팅(Hoisting)

### 호이스팅 이란?

hoist - 감아 올리다 라는 뜻을 가지고 있다

```jsx
//호이스팅(Hoisting)
//함수 선언부가 유효범위(scope) 최상단으로 끌어올려지는 현상

const a = 7;
double();// 오류 더블이라는 함수가 만들어지지 않아 함수가 아니라는 뜻의 오류가 나오는 당연한 결과
// 읽는 방향은 위에서 아래이니 당연한 결과이다 

// 함수 표현 부분을 함수 선언 부분으로 바꾸면?
const double = function () {
  console.log(a * 2);
};
```

### 함수 표현 부분을 함수 선언 부분으로 바꾸면?

```jsx
//호이스팅(Hoisting)
//함수 선언부가 유효범위(scope) 최상단으로 끌어올려지는 현상

const a = 7;
double(); // 14 라는 결과 값이 나온다

function double() {
  console.log(a * 2); // 호이스팅이 되서 결과 값이 나온다 함수 선언은 밑에 선언을 해도 윗쪽에서 호출 가능
}

// 함수 안에는 복잡한 로직이 많이 나올건데 함수 이름만 보고도 대략적인 결과물을 유추 가능하다
```

# 타이머 함수

### setTimeout 설정

```jsx
//타이머 함수
//setTimeout(함수, 시간): 일정 시간 후 함수 실행
//setInterval(함수, 시간): 시간 간격마다 함수 실행
//clearTimeout(): 설정된 Timeout 함수를 종료
//clearInterval(): 설정된 Interval 함수를 종료

setTimeout(function () {
  console.log('류승환!');
}, 3000); // 3000 ms 3초

// 3초 후 류승환 출력 
```

### clearTimeout

```jsx
//타이머 함수
//setTimeout(함수, 시간): 일정 시간 후 함수 실행
//setInterval(함수, 시간): 시간 간격마다 함수 실행
//clearTimeout(): 설정된 Timeout 함수를 종료
//clearInterval(): 설정된 Interval 함수를 종료

const timer = setTimeout(function () {
  console.log('류승환!');
}, 3000); // 3000 ms 3초

const a = document.querySelector('h1');

//index.html 에 있는 h1 tag를 불러와서 a 변수에 넣어 준다 

a.addEventListener('click', () => {
  clearTimeout(timer);
}); 

//다음 a 변수에 이벤트를 추가하여 클릭 시 clearTimeout이 실행 되며 실행되는 변수는 timer로 정함
```

### setInterval 설정 및 종료

```jsx
//타이머 함수
//setTimeout(함수, 시간): 일정 시간 후 함수 실행
//setInterval(함수, 시간): 시간 간격마다 함수 실행
//clearTimeout(): 설정된 Timeout 함수를 종료
//clearInterval(): 설정된 Interval 함수를 종료

const timer = setInterval(function () {
  console.log('류승환!');
}, 3000); // 3000 ms 3초

const a = document.querySelector('h1');

a.addEventListener('click', () => {
  clearInterval(timer);
});
```

# 콜백(Callback)

함수의 인수로 사용되는 함수

```jsx
//콜백(Callback)
//함수의 인수로 사용되는 함수

//setTimeout(함수, 시간)

// 뭔말?
// 셋 타임아웃 호출하려면 첫번째 인수로는 실행하고 싶은 함수
// 두번째 인수로는 시간
// 여기서 사용된 첫번째 인수 함수가 콜백이라고 한다

// 왜 콜백인지 그리고 어디에서 사용되는지?

function timeout(callback) {
  setTimeout(() => {
    console.log('류승환!');
    callback();
  }, 3000);
}

timeout(() => {
  console.log('Done!'); // 콜백함수
});

// 3초 다음 done이라는 출력을 보장 받고 싶을때
// timeout() 호출에 콜백을 넣어 준다음 timeout(인수 선언) 및 호출
// () => {console.log('Done!'); = callback
// 특별한 실행 위치를 보장하기 위해 콜백함수를 사용한다고 한다
```
