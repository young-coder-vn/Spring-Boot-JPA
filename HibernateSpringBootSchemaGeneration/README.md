**[How To Use In Spring Boot JPA 2.1 Schema Generation And Data Loading](https://github.com/andreipall/Spring-Boot-JPA/tree/master/HibernateSpringBootSchemaGeneration)**
 
**Description:** JPA 2.1 come with schema generation features. This feature can setup the database or export the generated commands to a file. The parameters that we should set are:

- `spring.jpa.properties.javax.persistence.schema-generation.database.action`: Instructs the persistence provider how to setup the database. Possible values include: `none`, `create`, `drop-and-create`, `drop`

- `javax.persistence.schema-generation.scripts.action`: Instruct the persistence provider which scripts to create. Possible values include: `none`, `create`, `drop-and-create`, `drop`.

- `javax.persistence.schema-generation.scripts.create-target`: Indicate the target location of the create script generated by the persistence provider. This can be as a file URL or a `java.IO.Writer`.

- `javax.persistence.schema-generation.scripts.drop-target`: Indicate the target location of the drop script generated by the persistence provider. This can be as a file URL or a `java.IO.Writer`.

Moreover, we can instruct the persistence provider to load data from a file into the database via: `spring.jpa.properties.javax.persistence.sql-load-script-source`. The value of this property represents the file location and it can be a file URL or a `java.IO.Writer`.

**Key points:**
- the settings are available in `application.properties`
