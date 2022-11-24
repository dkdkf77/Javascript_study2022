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
