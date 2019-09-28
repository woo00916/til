# Promise
: javascript 비동기 처리에 이용되는 객체. 

## promise states
처음 객체를 생성하면, 객체는 `Pending` 상태를 갖는다. 아직 선(先)로직이 처리되지 않은 상태
Promise 객체 내에서 `resolve()`나 `reject()` 메소드 실행을 통해 각각 `Fulfilled`, `Rejected` 상태로 전환된다. 

## 사용 예
### 

## promise api
자바스크립트에서는 몇가지 API를 제공한다. 

## 사용 예 
```javascript
  list() {
    return Promise.resolve(this.data)
  },
```
