# Vue 시작하기

> CDN 추가 
> `<script src="https://unpkg.com/vue"></script>`

## vue instance
```javascript
//app.js
new Vue({
    el : '#app' ,
    data:{
        msg : 'hello vue'
    }
})
```
* data의 변수가 바뀌면 화면이 자동으로 렌더링된다. 
* el에 바인딩할 장소를 지정할 수 있다. 위의 코드에서는 id가 app인 요소 내에서 사용할 수 있게 지정했다. 

### 예시코드
```html
<!--index.html-->
<body>
    {{msg}}<!--{{msg}}-->
        <div class="col-md-4" id="app"> 
        {{msg}}<!--hello vue-->
        </div>
</body>
```
 위 코드에서 첫번째는 문자열 `{{msg}}`이 그대로 화면에 표시되지만, 두번째는 `hello vue`가 표시된다.

> 관련 공식 문서 : https://vuejs.org/v2/guide/instance.html
