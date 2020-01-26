# kotlin-spring-boot-starter-project

# 1. Init Project

* Spring Web: Build web, including RESTful applications using Spring MVC
* Mustache: Template Engine
* Spring Data JPA: Persist data in SQL stores with Java Persistance API using Spring Data and Hibernate
* H2 Database: Provides fast in-memory database that supports JDBC API and R2DBC access with a small(2mb) footprint
* Spring Boot Devtools: Provides fast application restarts, LiveReload, and configurations

## 1.1 Spring Web Application Architecture ([link](https://www.petrikainulainen.net/software-development/design/understanding-spring-web-application-architecture-the-classic-way/))

![spring architect image](https://www.petrikainulainen.net/wp-content/uploads/spring-web-application-layers.png)


## 1.2. Java Persistence API; What is it? ([link](https://www.javaworld.com/article/3379043/what-is-jpa-introduction-to-the-java-persistence-api.html))

* Java Persistence specification lets you define which object should be persisted
> Persistence: Any mechanism by which Java objects outlive the application process that created them.
* Concepts that can be implemented by any tool or framework
* JPA and Hibernate are frequently conflated
> Hibernate: Java ORM library

![layer image](https://images.idgesg.net/images/article/2019/04/jw_java_persistence_series_1200x1600_diagram-100792564-large.jpg)

* Configuring the Java ORM Layer: After JPA is set up in your project, datastore and JPA provider should be configured.
> datastore: connector for database(SQL or NoSQL)
> JPA provider: ORM(Hibernate, EclipseLink etc...)

## 1.3. Spring Data; What is it??? ([link](https://www.infoq.com/articles/spring-data-intro/))

* Spring Data: High level SprinSource project whose purpose is to unify and ease to access to different kinds of persistence stores, both relational database systems and NoSQL data stores.

![spring data image](https://res.infoq.com/articles/spring-data-intro/en/resources/spring_data_overview_small.jpg)

> Hibernate(JPA provider)엔 update, save 같은 기본적인 메소드들만 있는데 Spring Data가 findByOne, findBy?? 같은 메소드들을 갖고 있는 Repository 인터페이스들을 제공 함으로써 코드 작성량을 줄여줌

### 1.3.1. Spring Data JPA and Hibernate([link](https://dzone.com/articles/what-is-the-difference-between-hibernate-and-sprin-1))


## 1.4. H2 Database; What is it?([link](http://www.h2database.com/html/main.html))

## 1.5 Spring MVC vs Spring Boot ([link](https://www.quora.com/What-is-difference-between-spring-MVC-and-spring-boot#div.w6bUHPNt8))

* Spring MVC: Traditional framework for building web applications

* Spring Boot: Framework that bundles all dependencies (Spring MVC, Spring Data, Hibernate etc)
> Spring Boot 쓰면 XML로 설정 안해도 됨

# 2. Gradle ([link](https://docs.gradle.org/current/userguide/userguide.html))

[Gradle with Kotlin DSL](https://github.com/puroong/gradle-tutorial)

# 3. Add Kotlin Controller

`src/main/kotlin/com/example/starterproj/HtmlController.kt`

```
package com.example.blog

import org.springframework.stereotype.Controller
import org.springframework.ui.Model
import org.springframework.ui.set
import org.springframework.web.bind.annotation.GetMapping

@Controller
class HtmlController {

  @GetMapping("/")
  fun blog(model: Model): String {
    model["title"] = "Blog"
    return "blog" // `src/main/resources/templates/blog.mustache`
  }

}
```

> model에 값을 추가하면 blog.mustache에서 그 값을 사용할 수 있음

```
{{> header}}

<h1>{{title}}</h1>

{{> footer}}
```

> {{> ??? }} => ???.mustache 삽입

* [Spring Boot Model](http://zetcode.com/springboot/model/)

# 4. Testing with JUnit5

## JUnit5 ([link](https://junit.org/junit5/docs/current/user-guide/#overview))

## Spring Testing ([link](https://docs.spring.io/spring/docs/current/spring-framework-reference/testing.html#testing-introduction))

# 5. Creating your own Extensions

# 6. Persistence with JPA

## 6.1. Kotlin AllOpen Plugin ([link](https://kotlinlang.org/docs/reference/compiler-plugins.html))

```
Kotlin has classes and their members final by default, which makes it inconvenient to use frameworks and libraries such as Spring AOP that require classes to be open. The all-open compiler plugin adapts Kotlin to the requirements of those frameworks and makes classes annotated with a specific annotation and their members open without the explicit open keyword.
```

* Kotlin all-open compiler plugin makes classes annotated with a specific annotation and their members open without hte explicit open keyword

* JPA is not designed to work with immutable classes or the methods generated automatically by data classes. So don't use data classes with val.

* User에 대한 Repository를 만들고 싶을 때 JPA Repository를 interface에 상속받고 구현하지 않는다면 User에 있는 property 이름들을 참고하여 자동으로 findBy??? 함수들을 선언할 수 있고 이를 구현하지 않아도 알아서 생성된다. (User에 없는 property 이름들을 사용하면 에러 뜸)

### 6.1.1. Spring AOP

* [link1](https://jojoldu.tistory.com/69?category=635883)
* [link2](https://jojoldu.tistory.com/70?category=635883)
* [link3](https://jojoldu.tistory.com/71?category=635883)
* [link4](https://jojoldu.tistory.com/72?category=635883)

### 6.1.2. Spring DI(Dependency Injection)([link](https://www.baeldung.com/inversion-control-and-dependency-injection-in-spring))

* Autowired([link](https://www.baeldung.com/spring-annotations-resource-inject-autowire))
### 6.1.3. Spring Bean([link](https://www.baeldung.com/spring-bean))

### 6.1.4. Spring IOC([link](https://www.baeldung.com/inversion-control-and-dependency-injection-in-spring))