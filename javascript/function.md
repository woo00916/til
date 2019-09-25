## hoisting
* javascript 에서는 함수 선언과 변수 선언을 미리 읽어서 끌어올림(hoisting)
* 선언과 할당이 동시에 된 코드의 경우, 분리해서 선언만 호이스팅
예)
```javascript
var a=1;
somefunction()
function f(){
 f2(a);
 var a = 3;
}
```
```javascript
var a = 1;
어딘가 있을 somefunction의 선언문
function f(){
  var a;
  f2(a);
  a=3;
}
```
> hoising은 컨택스트 단위로 실행됨
>> 컨택스트는 함수가 실행될 때 생성되고 끝날 때 사라짐 

## 함수를 표현하는 방법
1. `function f1() {...}` // 선호되지 않음
2. `var fv = function f2(){...}`
3. `var fv2 = function(){...}`

> hoising 부분은 좀더 자세하게 정리하기
