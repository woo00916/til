# @Autowired
#### 1. Bean으로 등록된 멤버 변수에 붙는 경우.
```java
@Service 
public class ItemService {
    public Item get(final String id){
        return new Item.builder().title("connect to db...").build();
    }
}
```
```java
@RestController
@RequestMapping("/todo")
public class ItemController {
    @Autowired 
    private ItemService itemService;
    ...
}
```
이 경우 스프링에선 ItemController가 생성될 때, Autowired 부분을 찾아서 ItemService injection을 실시한다.
#### 2. Setter에 붙는 경우
#### 3. Constructor에 붙는 경우
: 위에 경우에도 비슷하게, 해당 오브젝트가 생성될 때, Setter,Constructor를 사용하지 않아도 자동으로 매칭된다. 

> https://www.baeldung.com/spring-autowire
