# BookStore
BookStore Management System
Spring-Boot-REST-JPA-MySQL (BookStore)
Import project into eclipse
File -> Import -> Maven -> Existing Maven Projects -> Browse Project from cloned location

Right click on project in eclipse and then Maven -> Update Projects

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
  ![PUT postman](https://user-images.githubusercontent.com/88793028/131861467-9d561d84-a3ba-49db-83a4-ada97c47220e.PNG)
11.To delete a particular Book from database, use following url with DELETE request type in postman

 http://localhost:8080/bookservice/books/<id>
  DELETE in POSTMAN
  ![DELETE postman](https://user-images.githubusercontent.com/88793028/131862059-e969e215-366d-4861-b56d-49bb39c79ec5.PNG)
  
  DELETE in sql
  ![DELETE sql](https://user-images.githubusercontent.com/88793028/131862117-39b10c2d-fdd4-44bc-b2f9-45e7ca92c1aa.PNG)

 * Note - Replace <id> with actual id
