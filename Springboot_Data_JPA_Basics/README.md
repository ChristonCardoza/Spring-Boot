# Spring Data JPA(Java Persistance API)
 1. Its a JPA(Java Persistance API) based ORM (Object Relational Mapping ) mainly used with Databases
 2. Annotation:
   
    1. @Entity: Tells that given class is structe of the database
        ```java
            @Entity
            public class Topic{
                -----------------
            }
        ```
    2. @Id: Helps for specifying the Key(primary key)
        ```java
            @Entity
            public class Topic{
            @Id
            private String id;
            private String name;
            private String description;
            }
        ```
            To make use of all crude operation avilable for that entity(database) create a interface which extends the CrudRepository from Data JPA

        ```java
            public interface TopicRepository extends CrudRepository<Topic, String>{
            }
        ```
            Here we are using 2 Generics ie
                Topic : This is Entity or database structure
                String : Datatype of the key ie primary key.

            we no need to write new crude operaion, the instance of TopicRepository has some crude method

            if we are interested in declare any method in CrudRepository

        ```java
            
            public interface TopicRepository extends CrudRepository<Topic, String>{
                
                public List<Course> findByTopicId(String topicId)
            }
        ```

      3. @ManyToOne: Helps for specifying the foreign Key
    ```java
        @Entity
        public class Topic{
            @Id
            private String id;
            private String name;
            private String description;
            @ManyToOne
            private Topic topic
        }
    ```


   






