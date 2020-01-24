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


## 1.4. H2 Database; What is it?((link)[http://www.h2database.com/html/main.html])

## 1.5 Spring MVC vs Spring Boot ([link](https://www.quora.com/What-is-difference-between-spring-MVC-and-spring-boot#div.w6bUHPNt8))

* Spring MVC: Traditional framework for building web applications

* Spring Boot: Framework that bundles all dependencies (Spring MVC, Spring Data, Hibernate etc)
> Spring Boot 쓰면 XML로 설정 안해도 됨

# 2. Gradle ([link](https://docs.gradle.org/current/userguide/userguide.html))

[Gradle with Kotlin DSL](https://github.com/puroong/gradle-tutorial)