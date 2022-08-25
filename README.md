
# Goals

 - Explain what needs to be done to achieve the Level 2 on a RESTFUL API
   on the Richardson Maturity Model.
 - Implement a Level 2 Users RESTFUL API Microservice.
 - Implement a Level 2 Tasks RESTFUL API Microservice.
 - User dependencies injections to create a decoupled architecture.

# MaIn Topics

 - Microservices.
 - RESTFUL API.
 - Richardson Maturity Model.
 - Dependencies Injection.

# Codelab 🤹🏽
## Part 1: Implementing the Users Microservice RESTFUL API

 1. Create a new project using the Spring Initializr .
 2. Use either **Java** or **Kotlin** as programming language.
 3. Use **Gradle** as project option.
 4. Add Spring Web dependency.
 5. Use latest Spring Boot version (make sure your selection doesn't
    contain SNAPSHOT or M1 (those are not as stable as the rest).
 6. Click on generate.
 8. Create a new public repo, name it as you like.
 9. Commit/push the files generated.
 10. Open the project on favorite editor (IntelliJ IDEA is highly
     recommended throughout this course).
 11. Create a new package called ***dto*** and inside define your ***UserDto***
     object with at least the following fields:

       - id
       - name
       - email
       - lastName
       - createdAt

12. Create a new package called ***model*** and inside define your ***User*** model object with at least the following fields (Types don't matter yet, just be sure both DTO classes and Data classes types are consistent enough): 

	- name
	- email
	- lastName
	
13. Create a new package called ***service*** and inside create the following interface:

    ```java
     public interface UserService
     {
         UserDto create( User user );

         UserDto findById( String id );
         
         List<UserDto> getAll();

         void deleteById( String id );

         UserDto update( User user, String userId );
     }  
14. Create an implementation of the ***UserService*** using a HashMap data structure inside.
15. Make your service implementation ***UserServiceHashMap*** injectable using the ***@Service*** annotation.
16. Create a new package called ***controller*** and create a new class ***UserController*** inside.
17. Annotate your ***UserController*** so it becomes a ***REST*** Controller:
18. Inject your ***UserService*** implementation inside the ***UserController*** via the constructor:
19.  Implement all the endpoints needed to interact with you  _UserService_. Use the following method signatures to help you achieve the Level 2 RESTFUL Maturity:
   ```java
    private final UserService userService;


    @GetMapping
    public ResponseEntity<List<UserDto>> getAll() {
        //TODO implement this method using UserService
        return null;
    }
   
    @GetMapping( "/{id}" )
    public ResponseEntity<UserDto> findById( @PathVariable String id ) {
       //TODO implement this method using UserService
       return null;
    }
   
   
    @PostMapping
    public ResponseEntity<UserDto> create( @RequestBody UserDto userDto ) {
         //TODO implement this method using UserService
         return null;
    }
   
    @PutMapping( "/{id}" )
    public ResponseEntity<UserDto> update( @RequestBody User user, @PathVariable String id ) {
         //TODO implement this method using UserService
         return null;
    }

    @DeleteMapping( "/{id}" )
    public ResponseEntity<Boolean> delete( @PathVariable String id ) {
         //TODO implement this method using UserService
        return null;      
    }
  }
 ```

20. Build / Run your project.
21. Download and install [Insomnia](https://insomnia.rest/download) and test ALL the endpoints of your API.

## Part 2: Implementing the Tasks Microservice RESTFUL API

1. Follow the previous part steps
2. Create a new package called ***dto*** and inside define your ***TaskDto*** object with at least the following fields:
        - id
	- name
	- description
	- status ( TODO, DOING, REVIEW and DONE )
	- assignedTo
	- dueDate
	- createdAt
3. Create a new package called ***model*** and inside define your ***Task*** model object with at least the following fields:
	- name
	- description
	- status ( TODO, DOING, REVIEW and DONE )
	- assignedTo
	- dueDate
4. Create a new package called ***service*** and inside create the following interface:
	```java
	public interface TaskService
    {
        TaskDto create( Task task );

        TaskDto findById( String id );
        
        List<TaskDto> getAll();

        boolean deleteById( String id );

        TaskDto update( Task task, String id );
    }
    ```
5. Create an implementation of the ***TaskService*** using a ***HashMap*** data structure inside.
6. Make sure your service implementation ***TaskServiceHashMap*** is injectable using the ***@Service*** annotation.
7. Implement your ***TaskController*** (Try to avoid copy paste, use the **User Microservice** as a reference but try doing it conciously).
8. Test ALL the endpoints of your API using **Insomnia**.

## 

Remember to add your both **Github** repos url into the **Ada** input box to deliver correctly your codelab.
