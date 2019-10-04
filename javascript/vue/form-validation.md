# form validation
vue에서도 폼 검증을 간단하게 하기 위해 다양한 기능을 제공한다. 아래의 예제 코드를 베이스로 폼 검증 방법을 공부하였다. 
## before
```html
         <form>
                <input type="email" class="form-control" id="email" aria-describedby="emailHelp" placeholder="Enter email">
                <small id="emailHelp" class="form-text text-muted">We'll never share your email with anyone else.</small>
         
           ...
        </form>
```
## 순서
### 1. html input tag와 vue instance 바인딩
: html에 v-model 속성으로 Vue 인스턴스의 data와 바인딩.
> v-model </br>
> v-model은 양방향바인딩을 지원한다. 즉, vue 인스턴스에 값이 지정되면, 자동으로 뷰에 표시되고, 뷰에서 값이 변동된다면, vue 인스턴스에도 반영되는 형식.
```html
      ...
      <input type="email" class="form-control" v-model="email" id="email" aria-describedby="emailHelp" placeholder="Enter email">
      ...
```
```javascript
new Vue({
    el : '#signupform' ,
    data:{
        email : '',
        emailerr:'',
        ...
    }
})
```
### 2. v-show 속성으로 조건지정 해서 에러메시지 표시
```html
  <form v-on:submit="checkForm" id="signupform">
      ...
      <input type="email" class="form-control" v-model="email" id="email" aria-describedby="emailHelp" placeholder="Enter email">
      <small id="emailHelp" class="form-text text-muted" v-show="emailerr">the e-mail field is required.</small>
      ...
  </form>
```
### 3. 에러가 있을 시 submit 되지 않도록 지정
```javascript
new Vue({
    el : '#signupform' ,
    data:{
        email : '',
        emailerr:'',
        ...
    },
     methods:{
        checkForm : function (e){
            if(validation pass의 경우){
              return true;
            }
            e.preventDefault();
        }
    }
})

```

> preventDefault는 디폴트 행동을 막는 javascript 메소드

---
새로고침을 하다보면 에러메시지부분이 잠깐 보였다 사라지는데 이걸 해결할 방법이 있을까
