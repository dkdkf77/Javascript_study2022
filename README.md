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

