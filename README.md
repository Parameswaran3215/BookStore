# BookStore
BookStore Management System
Spring-Boot-REST-JPA-MySQL (BookStore)
Import project into eclipse
File -> Import -> Maven -> Existing Maven Projects -> Browse Project from cloned location

Right click on project in eclipse and then Maven -> Update Projects![Eclipse output](https://user-images.githubusercontent.com/88793028/131848170-86d5e9e7-720e-40a1-835b-d591bd45f42c.PNG)

Import src/main/java/resources/book.sql into MySQL database

Update database credential and other configuration into application.properties available in src/main/java/resources

spring.datasource.url=jdbc:mysql://localhost:3306/bookstore spring.datasource.username=root spring.datasource.password=***** spring.datasource.tomcat.max-wait=20000 spring.datasource.tomcat.max-active=50 spring.datasource.tomcat.max-idle=20 spring.datasource.tomcat.min-idle=15

spring.jpa.properties.hibernate.dialect = org.hibernate.dialect.MySQLDialect spring.jpa.properties.hibernate.id.new_generator_mappings = false spring.jpa.properties.hibernate.format_sql = true

logging.level.org.hibernate.SQL=DEBUG logging.level.org.hibernate.type.descriptor.sql.BasicBinder=TRACE

Right click on Application.java file and run as Java Application

Once Sprint Boot Application will be started successfully then we can call following Endpoints by using POSTMAN

To get list of books call following endpoint with GET Request

http://localhost:8080/bookservice/books

8.To Create New Book use following url with POST Request

  http://localhost:8080/bookservice/books

* set content type as in header as `application/json`
* set request body as raw with JSON payload

  {
    "name": "JAVA",
    "author": "Parameswaran",
    "publication": "Ravuthar Publication",
    "category": "Java Programming",
    "pages": 1000,
    "price": 1500
  } 
  POST in POSTMAN tool
  ![POST Method](https://user-images.githubusercontent.com/88793028/131860156-4e633a9e-08f4-4569-91b8-69e27cb8c232.PNG)
  POST in URL
  ![POST url](https://user-images.githubusercontent.com/88793028/131860239-2f1572b0-2d4e-4424-a7d6-1766f3a87443.PNG)
  
9.To get a particular book, use following url with GET request type in postman

 http://localhost:8080/bookservice/books/<id>
10.To update Book in database, use following url with PUT request type in postman

 http://localhost:8080/bookservice/books/<id>

 * set content type as in header as `application/json`
 * set request body as raw with JSON payload

   {
     "name": "JAVA",
     "author": "Parameswaran",
     "publication": "Ravuthar Publication",
     "category": "Java Programming",
     "pages": 1000,
     "price": 1500
   }
11.To delete a particular Book from database, use following url with DELETE request type in postman

 http://localhost:8080/bookservice/books/<id>

 * Note - Replace <id> with actual id
