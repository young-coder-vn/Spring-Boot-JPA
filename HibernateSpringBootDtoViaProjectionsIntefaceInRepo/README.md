**[DTO Via Spring Data Projections (Projection Interface In Repository Interface)](https://github.com/andreipall/Spring-Boot-JPA/tree/master/HibernateSpringBootDtoViaProjectionsIntefaceInRepo)** 

**Note:** You may also like to read the recipe, ["How To Enrich DTO With Virtual Properties Via Spring Projections"](https://github.com/andreipall/Spring-Boot-JPA/blob/master/HibernateSpringBootDtoViaProjectionsAndVirtualProperties)

**Description:** Fetch only the needed data from the database via Spring Data Projections (DTO). The projection interface is defined as a `static` interface (can be non-`static` as well) in the repository interface.

**Key points:**
- write an interface (projection) containing getters only for the columns that should be fetched from the database
- write the proper query returning a `List<projection>`
- if is applicable, limit the number of returned rows (e.g., via `LIMIT`) - here, we can use query builder mechanism built into Spring Data repository infrastructure
     
**Note:** Using projections is not limited to use query builder mechanism built into Spring Data repository infrastructure. We can fetch projections via JPQL or native queries as well. For example, in this [application](https://github.com/andreipall/Spring-Boot-JPA/tree/master/HibernateSpringBootDtoViaProjectionsAndJpql) we use a JPQL.
     
**Output example (select first 2 rows; select only "name" and "age"):**
<a href="#"><img src="https://github.com/andreipall/Spring-Boot-JPA/blob/master/HibernateSpringBootDtoViaProjections/DTOs%20via%20Spring%20projections.png" align="center" height="251" width="658" ></a>
