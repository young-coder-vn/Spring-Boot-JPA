**[Fetching All Entity Attributes As Spring Projection (DTO)](https://github.com/andreipall/Spring-Boot-JPA/tree/master/HibernateSpringBootJoinDtoAllFields)**
 
**Description:** This application is a sample of fetching all attributes of an entity (`Author`) as a Spring projection (DTO). Commonly, a DTO contains a subset of attributes, but, sometimes we need to fetch the whole entity as a DTO. In such cases, we have to pay attention to the chosen approach. Choosing wisely can spare us from performance penalties.

**Key points:** 
- fetching the result set as a `List<Object[]>` or `List<AuthorDto>` via a JPQL of type `SELECT a FROM Author a` **WILL** fetch the result set as entities in Persistent Context as well - avoid this approach
- fetching the result set as a `List<Object[]>` or `List<AuthorDto>` via a JPQL of type `SELECT a.id AS id, a.name AS name, ... FROM Author a` will **NOT** fetch the result set in Persistent Context - this is efficient
- fetching the result set as a `List<Object[]>` or `List<AuthorDto>` via a native SQL of type `SELECT id, name, age, ... FROM author` will **NOT** fetch the result set in Persistent Context - but, this approach is pretty slow
- fetching the result set as a `List<Object[]>` via Spring Data query builder mechanism **WILL** fetch the result set in Persistent Context - avoid this approach
- fetching the result set as a `List<AuthorDto>` via Spring Data query builder mechanism will **NOT** fetch the result set in Persistent Context
- fetching the result set as *read-only* entitites (e.g., via the built-in `findAll()` method) should be considered after JPQL with explicit list of columns to be fetched and query builder mechanism
