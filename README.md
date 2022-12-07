# gitignore_practice
gitignore 연습 및 push 연습

<hr/>
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
<hr/>
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
<hr/>
# 산술 연산자

```jsx
// 산술 연산자(arithmetic operator)

console.log(1 + 2); //3
console.log(5 - 7); //-2
console.log(10 * 10); // 100
console.log(10 / 5); //2
console.log(7 % 5); //2 나머지 값
```
<hr/>
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
<hr/>
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
<hr/>
# 같지 않다 ! ==

```jsx
// 비교 연산자(comparison operator)

const a = 1;
const b = 3;

console.log(a !== b); // true , 불일치 연산자
```
<hr/>
# 작다 <

```jsx
// 비교 연산자(comparison operator)

const a = 1;
const b = 1;

console.log(a < b); // false
```
<hr/>
# 작거나 or 크거나 같다

```jsx
// 비교 연산자(comparison operator)

const a = 7;
const b = 7;

console.log(a >= b); //true 
```

# ❗️ 꺽쇠 갈호는 앞에 배치되야 한다

만약 =<  ⇒ 이런식으로 적으면 오류가 난다 왜? 이런 문법은 없으니깐 ㅎㅎ
<hr/>
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
<hr/>
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
<hr/>
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
<hr/>
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
<hr/>
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
<hr/>
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
# 생성자 함수(prototype)

### this는?

실행되는 객체 데이터를 말하는 것 

즉 밑에 const ryu를 this 로 본다

```jsx
// 기본적인 객체 데이터의 구조
// 중괄호
// firstName lastName 속성 property, prop
// getFullName = method 메소드  function으로 실행되는 속성값

// 속성과 메소드를 통틀어서 멤버(Member)라고도 볼린다

const ryu = {
  firstName: 'ryu',
  lastName: 'seunghwan',
  getFullName: function () {
    return `${this.firstName} ${this.lastName}`;
  },
};

console.log(ryu.getFullName()); // ryu seunghwan
```

### Javascript Class 방식

```jsx
//우리가 기본적으로 알고 있는 것으로 일일히 만들어 줘야하는데 
//현재 이러한 로직은 효율이 많이 떨어지는 로직
// 객체 데이터를 만들때 마다 메모리에 할당되면서 만들어지는데 
// javascript의 클래스를 쓰게 된다면?

const ryu = {
  firstName: 'ryu',
  lastName: 'seunghwan',
  getFullName: function () {
    return `${this.firstName} ${this.lastName}`;
  },
};

console.log(ryu.getFullName());

const Do = {
  firstName: 'do',
  lastName: 'heasun',
  getFullName: function () {
    return `${this.firstName} ${this.lastName}`;
  },
};

console.log(Do.getFullName());

const Kim = {
  firstName: 'kim',
  lastName: 'minser',
  getFullName: function () {
    return `${this.firstName} ${this.lastName}`;
  },
};

console.log(Kim.getFullName());
```

### user.prototype.getFullName = function 메소드

![스크린샷 2022-12-05 오후 5 09 10](https://user-images.githubusercontent.com/88579497/205588203-a025d8f9-d509-4ad3-8038-f5a181d1a9ed.png)

이렇게 user() 함수에 초기 값으로 getFullName 메소드를 넣어주는 명령어 인것 같다

```jsx
// 메모리에 한번만 만들어져 있는 값을 참조한다
// 효율적인 메모리 관리
user.prototype.getFullName = function () {
  return `${this.firstName} ${this.lastName}`;
};
```

## 생성자 함수는 파스칼 케이스로 User 대문자를 사용하여

```jsx
// 생성자 함수는 파스칼 케이스를 사용하여 
// function User 만 보더라도 생성자 함수라는 것을 알아 볼수 있게 
// 파스칼 케이스를 사용한다
// 관행적으로 사용되는 것

function User(first, last) {
  this.firstName = first;
  this.lastName = last;
}
// 메모리에 한번만 만들어져 있는 값을 참조한다
// 효율적인 메모리 관리
User.prototype.getFullName = function () {
  return `${this.firstName} ${this.lastName}`;
};

// new 라는 키워드로 user() 함수를 실행하게 되었고
// new는 생성자 함수 => 하나의 객체데이터를 생성
// const ryu = {} 리터럴 방식으로 간단하게 {} 객체데이터를 생성
// new 라는 키워드로 할당된 ryu, Do, Kim 은 인스턴스라고 한다

const ryu = new User('ryu', 'seunghwan');
const Do = new User('do', 'heasun');
const Kim = new User('Kim', 'minser');

console.log(ryu.getFullName());
console.log(Do);
console.log(Kim.getFullName());
```

<hr/>
# This

```jsx
//this
//일반(Normal)함수는 호출 위치에서 따라 this 정의!
//화살표(Arrow) 함수는 자신이 선언된 함수 범위에서 this 정의!

//함수 범위라는게 중요한 키워드
// 일반 함수는 호출 위치, 화살표 함수는 함수 범위를 이해해야 한다

//

const ryu = {
  name: 'ryu',
  nick: 'chichi',
  normal: function () {
    // 메소드
    console.log(this.name); //메소드 안 로직
  },
  arrow: () => {
    console.log(this.nick);
  },
};

ryu.normal();
// ryu normal 메소드는 ryu의 객체데이터 내부에서 실행 된다
// 호출 위치 name -> 앞에 ryu가 this
ryu.arrow();
// undefined
// 화살표 함수 같은 경우는 자신이 선언된 어떠한 범위가 존재하고
// 화살표의 this는 현재 객체 데이터 코드 안에서 this가 정확하게 무엇을 표현한지 알수 없고
// 알수 없는 속성에서 nick을 찾으니 undefined가 뜨는 이유

const Do = {
  name: 'Do',
  normal: ryu.normal,
  arrow: ryu.arrow,
};

Do.normal(); //Do
// Do.normal() = function(){console.log(this.name)}; 을 normal에 넣어줌
// 호출 위치에서 노말 fucntion 같은 경우 호출되는 위치 즉 Do.normal()이 실행되는 바로
// Do가 this가 되므로 name = Do가 잘 출력이 되는 것을 확인 할 수 있다
Do.arrow(); //undefined
```

### 생성자 User 사용시 function 과 화살표 함수의 실행

```jsx
function User(name) {
  this.name = name;
}
//User라는 생성자 밖에서 들어오는 인수는 name으로 받아서 this.name 안에 넣어줌
const ryu = new User('ryu');
// 생성자 인수로 ryu를 변수 ryu로 넣어줌

User.prototype.normal = function () {
  console.log(this.name); // ryu
};

//User 생성자 안 프로토타입에 normal을 생성하는데 그 노멀의 로직은 console.log(this.name)

User.prototype.arrow = () => {
  console.log(this.name); // undefined 이 화살표 함수가 선언된 이 함수 범위 내부에서 this가
  // 실행되므로 undefined가 뜬다
};

ryu.normal();
ryu.arrow();
```

### setTimeout 함수은 콜백함수로 에로우 함수를 사용하는 것을 추천

```
const timer = {
  name: 'ryu',
  timeout: function () {
    setTimeout(() => {
      console.log(this.name);
    }, 2000);
    // setTimeout 이라는 내부 로직의 인수로 콜백되어 사용되므로 undefined가 뜸
    // 다르게 console.log(timer.name)을 주면 ryu가 잘 출력 된다
    // 그럼 이러한 경우 화살표 함수를 쓰면 ? ryu가 잘 출력 되는 것을 볼 수 있다
    // 화살표 함수를 감싸고 있는 함수가 timeout: function(){} 인것을 볼수 잇고
    // 결국 화살표 함수를 감싸고 있는 추가적인 함수 범위가 있기 때문에
    // 그 함수 범위에서 this는 곧 일반 함수가 정의된 timer가 this가 된다

    // function 함수는 선언된게 명확하고 arrow함수는 명확하지 않다?
    // 이것을 쉽게 이해할수 있는 방법이 없을까?
    // setTimeout 이라는 인터벌을 사용할때는 콜백으로 일반 함수보다 화살표 함수를 쓰는 것을
    // 추천한다 그이유는 setTimeout의 자바스크립트 어딘가에서 정의되는 것이 아닌 우리가 작성한
    // 특정한 범위 내에서 this가 정의 될 수 있도록 만들어 줄 수 있어서
  },
};

timer.timeout();
```

<hr/>
# ES6 Classes

```jsx
//ES6 Classes

const ryu = {
  name: 'ryu',
  normal: function () {
    console.log(this.name);
  },
  arrow: () => {
    console.log(this.name);
  },
};

ryu.normal();
ryu.arrow();
```

### 일반 function(){} 축약

```jsx
normal~~: function~~ () {
    console.log(this.name);
  }, //ryu

normal() {
    console.log(this.name);
  }, 
//ryu function 함수와 동일하다고 생각할 것

```

# 상속(확장)
```jsx
class Vehicle {
  constructor(name, wheel) {
    this.name = name;
    this.wheel = wheel;
  }
}

const myVehicle = new Vehicle('운송수단', 2);
console.log(myVehicle);
// name = 운송수단 wheel = 2 인 객체 데이터를 출력
// Vehicle {name : '운송수단', wheel: 2}

// 상속
class Bicycle extends Vehicle {
  constructor(name, wheel) {
    super(name, wheel);
  }
}

const myBicycle = new Bicycle('삼천리', 2);
const daughtersBicycle = new Bicycle('세발', 3);
console.log(myBicycle);
console.log(daughtersBicycle);

//extends = 확장, 상속 Vehicle을  Bicycle에 상속하여 내부에서 사용하겠다
// super라는 함수 = Vehicle을 의미
//곧
//super(name,wheel) =
//constructor(name,wheel){
//   this.name = name
//   this.wheel = wheel
//} 이것을 상속하여 쓴다는 것

//확장
class Car extends Vehicle {
  constructor(name, wheel, license) {
    super(name, wheel);
    this.license = license;
  }
}
const Mycar = new Car('운송', 4, 'true');
console.log(Mycar); //Car {name:'운송', whell:4, license: 'true'}
// 윗쪽 처럼 상속을 받아 this.license = license로 확장을 시켜준다
// 만약 라이센스 부분에 공백이면 Car {name: '운송', wheel: 4, license: undefined}
```

<hr/>
# 문자

## 자바스크립트 데이터를 다룰수 있는 명령문을 배운다

### String

```jsx
// JS 데이터

// String : '', "" , ``
// Number
// Boolean: true, false
// undefined
// null
// Array : []
// object: {}

// 이렇게 배웠는데 그래서 자바스크립트로 어떻게 웹 사이트를 만드느냐?
// ??

// 그것이 중요한게 아니라 자바스크립트를 통해서 데이터를 처리하는 것 자체가 웹사이트를 만드는데 무조껀 필요하다

//리터럴 방식이란?
//=> 간략화 시켜 객체데이터 {} , 배열데이터 [] , 등 기호를 통해서 데이터를 손쉽게 만들어내는 방식

// String

//String.prototype.indexOf()
//indexOf() 메서드는 호출한 String 객체에서 주어진 값과 일치하는 첫 번째 인덱스를 반환합니다. 일치하는 값이 없으면 -1을 반환합니다.

const result = 'Hi Ryu world'.indexOf('world');

console.log(result); //7

// String.prototype.indexOf()
```

### Sring.length

```jsx
// 변수 안에는 문자, 숫자, 불린, 객체, 배열 데이터를
// 넣을 수 있다

// String.length
const str = '0123';
console.log(str.length);

// 띄어쓰기도 공백 문자에 속한다
```

### Sring.indexOf() method

```jsx
const str = 'hi ryu';

console.log(str.indexOf('ryu')); //3

//만약 찾지 못하면 -1 결과값을 출력
```

```jsx
const str = 'hi ryu';

console.log(str.indexOf('Ryu') !== -1); //false

// str.indexOf('ryu') 값이 있으면 true 출력, 없으면 false
// 해석 str.indexOf('Ryu') = -1 
// -1 == -1   true
// 하지만 !== 이니깐 false 출력
```

### String.slice() method

```jsx
const str = 'hi ryu';

console.log(str.slice(0, 3)); // hi

// 두번째 인수 3으로 하면 0~2 번까지 slice로 추출함
console.log(str.slice(3, 6)); // ryu
```

### String.replace() method

```jsx
const str = 'hi ryu';

console.log(str.replace('hi', 'seunghwan')); //seunghwan ryu

// 첫번째 인수에 대체될 대상, 두번째 인수에 대체될 텍스트

// replace로 제거
console.log(str.replace('hi ', '')); //ryu
```

### String.match() method

```jsx
const str = 'dkdkf312@gmail.com';

//정규 표현식
console.log(str.match(/.+(?=@)/));
//['dkdkf312', index: 0, input: 'dkdkf312@gmail.com', groups: undefined]

console.log(str.match(/.+(?=@)/)[0]);
// dkdkf312
```

### String.trim() method

```jsx
const str = '       dkdkf312@gmail.com     ';
//앞뒤로 공백 문자가 들어가 있을때

console.log(str.trim()); //dkdkf312@gmail.com
// 아이디를 입력할때 실수로 띄어쓰기를 하면 문자로 인식되는 문제가 있을때 사용
```
