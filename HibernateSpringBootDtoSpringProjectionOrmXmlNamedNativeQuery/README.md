**[How To Use JPA Named Native Queries Via `orm.xml` File And Spring Projection (DTO)](https://github.com/AnghelLeonard/Hibernate-SpringBoot/tree/master/HibernateSpringBootDtoSpringProjectionOrmXmlNamedNativeQuery)**
 
**Description:** This application is an example of combining JPA named native queries listed in `orm.xml` file and Spring projections (DTO). For queries names we use the `{EntityName}.{RepositoryMethodName}` naming convention. This convention allows us to create in the repository interface methods with the same name as of named native query.
  
**Key points:**
- define the named native queries in `orm.xml` file in a folder named `META-INF` the application classpath 
- define the proper Spring projection
