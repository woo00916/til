# Auto configuation
## 1. @SpringBootApplication
: @Configuration + @ComponentScan + @EnableAutoConfiguration

### 1.1 @Configuration (optional)
: @Bean Annotation이 선언된 method를 하나 이상 가지고 있을 때 선언
> **@Bean**
> : 스프링에서 관리하는 오브젝트를 Bean 이라고 한다. 주로 xml에 선언해 사용하지만, 기존 라이브러리 등을 Bean으로 설정하고 싶을 때 해당 어노테이션을 사용.

#### @SpringBootApplication 에 @Configuration 가 왜 추가되어 있을까
검색해봤더니 `SpringApplication.run()`method에 파라미터로 Bean 등록되어 있지 않은 오브젝트가 있을 것을 대비해 추가한 듯 하다. 
> https://stackoverflow.com/questions/39247487/why-spring-boot-application-class-needs-to-have-configuration-annotation
```java
//@Configuration
@ComponentScan
@EnableAutoConfiguration
public class Application {
    public static void main(String[] args) {
        SpringApplication.run(Application.class,args);
    }
}
```
@Configuration 이 필요한 지 확인하기 위해, 위의 코드를 실행시켰을 때도 문제없이 작동하는 것을 확인했다.
 
### 1.2 @ComponentScan
: 해당 패키지 포함 하위 패키지까지의 클래스를 Bean으로 등록한다.

### 1.3 @EnableAutoConfiguration (optional)
: @ComponentScan으로 Bean을 등록한 후, 추가적인 기본설정(@Configuration)+조건부설정을 읽어서 등록
