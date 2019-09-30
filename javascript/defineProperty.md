# defineProperty
property의 값을 설정하거나, getter, setter를 설정할 수 있다. 

## syntax
> Object.defineProperty(obj, prop, descriptor)

## example code
```javascript
const viewModel={};
let model=''
Object.defineProperty(viewModel,model,{
  get(){return model;},
  set(val){
    model=val;
    h1.innerHTML=model;
  }
});

viewModel.model='hello vue';//execute set()
```
