# DEZSYS GK81 Warehouse ORM

## GKü

### Questions
- What is ORM and how is JPA used?
  - ORM stands for Object-Relational Mapping and maps table based databases into Objects in many programming languages and the other way around. THe benefit is one doesn#t have to manually write SQL-statements.
  - JPA stands for Java Persistence API is a specification for Java. I used Hibernate which is the most common.
  - It is used with the Annotations that mark objects, Attributes or Methods for the interpreter. Like @Entity for persistence objects
- What is application.properties used for and where must it be stored?
  - There are configurations for the Spring Boot application in my project I use it for specifying my database.
  - It has to be stored in src/main/resources
- Which Annotations are frequently used for Entity types? Which key points must be observed?
  - @Entity
    - Marks a class that gets mapped to the database table.
  - @Id
    - Marks the primary key of the entity
  - GeneratedValue
    - specifies the strategy for generating primary key
  - @Column
    - Specifies the column name of an attribute
  - @Table
    - Specifies the name of the table for the entity
  - @ManyToOne, @OneToMany, @OneToOne, @ManyToMany
    - Define relationships between entities.
  - @JoinColumn
    - Specifies the column that is used to join the related entities.
  - @Transient
    - Marks a field that should not be persisted in the database.
- What methods do you need for CRUD operations?
  - Create I can use save(entity) to add a entity to the database
  - Read I can either use findById(id) to get a single row or findAll() for every row in the table.
  - Update again save(entity) when the entity already exists, it updates it instead.
  - Delete here again I can either use deleteById(id) or delete(entity) or even deleteAll()

### Documentation

**First Step**

Pulling the Project from the teacher https://github.com/ThomasMicheler/DEZSYS_GK862_DATAWAREHOUSE_ORM.git

**Second Step**

```docker compose up``` to a MySQL ``compose.yaml`` file that I copied form the internet.

**Third Step**

Updating the ``aplication.properties`` for the Username and Password for my Docker-Container

**Fourth Step (unnecessary)**

Creating a Service Class for the beauty of the Model View Controller

This code snippet is the most important and equals to ``SELECT * FROM user;``
```
public Iterable<User> getAllUsers() {
    return userRepository.findAll();
}
```

### Additional Information

The curl command in windows which adds a User over POST to my Webserver

``curl.exe -X POST http://localhost:8082/demo/add -d "name=John Doe" -d "email=john.doe@example.com"``

## Quellen

ORM: https://docs.spring.io/spring-framework/reference/data-access/orm/introduction.html

Annotations and JPA: https://docs.oracle.com/javaee/7/tutorial/persistence-intro001.htm

application.properties: https://docs.spring.io/spring-boot/appendix/application-properties/index.html

CRUD: https://www.baeldung.com/spring-data-repositories
