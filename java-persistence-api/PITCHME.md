# JEE : Java Persistence API

---

### Java Persistence API : Why?

Java Persistence API means to be an ORM solution to manage data from a relational Data Base.

---

### Object Relational Mapping : how does it work?


- The concept of ORM is to bind properties from a class to some columns in a Relation Data Base.

- This binding allows to persist automatically instances from bound classes.

---

### JPA implementations

It exists several JPA implementations :
- Hibernate
- JDO
- Eclipse Link

We'll choose Hibernate because it's the most present (and most active) framework for JPA.

---

### Hibernate : how-to configure
There are two phases to configure Hibernate :
- Framework configuration
- Datamodel annotation

---

### Minimal annotations for JPA

``` 
@Entity
public class Question {

	@Id
	@GeneratedValue(strategy = GenerationType.AUTO)
	private Integer id;
	
	// rest of properties	
	
	}

```

---

### JPA Column binding
- If you specify nothing on the properties of a class, then a column with the same name is created 
- You can override this behavior by specifying a `@Column` annotation


--- 
### Hibernate default configuration
Hibernate needs a configuration to specify several aspects :
- The several properties that configures the translation between Object domain and Relational DB
- The connections information related to the database connection
- Those two configurations allow to configure the session factory

--- 
### Hibernate configuration with Spring
```
<bean id="datasource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
 		<property name="url" value="jdbc:h2:mem:test"></property>
 		<property name="username" value="test"></property>
 		<property name="password" value="test"></property>
 		<property name="driverClassName" value="org.h2.Driver"></property>
</bean>

<bean class="org.springframework.beans.factory.config.PropertiesFactoryBean" id="hibernateProperties">
		<property name="properties">
			<props>
				<prop key="hibernate.dialect">org.hibernate.dialect.H2Dialect</prop>
				<prop key="hibernate.show_sql">true</prop>
				<prop key="hibernate.hbm2ddl.auto">update</prop>
				<prop key="hibernate.connection.autocommit">false</prop>
			</props>
		</property>
</bean>

<bean id="sessionFactory" class="org.springframework.orm.hibernate5.LocalSessionFactoryBean">
	<property name="dataSource" ref="dataSource" />
	<property name="hibernateProperties" ref="hibernateProperties" />
	<property name="packagesToScan">
		<list>
			<value>fr.epita.quiz.datamodel</value>
		</list>
	</property>
</bean>

```
@[1-6](the datasource from which we can establish the connection)
@[8-18](the properties to configure the hibernate framework)
@[20-28](the session factory allowing to create Hibernate Sessions)

---
### Usage in the code
use @Inject to reference the session factory, as follows :

```
public abstract class GenericDAO<T> {

	private static final Logger LOGGER = LogManager.getLogger(GenericDAO.class);
	
	@Inject
	private SessionFactory sf;
	
	//rest of the code
	
}
```
@[5-6](the way to inject the session factory in a service class)

---

### session : opening sessions

- In order to manage data through Hibernate, it is necessary to open a `Session`. 
- This is one common code to handle the session: 

```
	protected final Session getSession() {
		Session session = null;
		try {
			session = this.sf.getCurrentSession();
		} catch (Exception e) {
			LOGGER.error(e);
		}
		if (session == null) {
			session = sf.openSession();
		}
		return session;
	}

```
---

### saving data : commits and transactions
- When you use the `Session` APIs, data modifications are triggered automatically
- to force the session to commit changes, you have two choices :
  - either disable autocommit option and call session.flush() every time it is needed
  - either wrapping code within a `Transaction`
- Be sure that you don't nest transactions, it is not allowed by many databases.

---
### Handling transactions 
In order to avoid the nested transactions problem, you can test if there is an open transaction before to create a new one:

```
	protected final Transaction getTransaction(Session session) {
		
		
		Transaction tx = session.getTransaction();
		if (!TransactionStatus.ACTIVE.equals(tx.getStatus())) {
			tx = session.beginTransaction();
		}
		return tx;
	}

```

---

### Common patterns associated to Data Persistence
To handle data operations properly, it is recommended to use some design patterns :
- DAO pattern : The DAO class centralizes all the methods (CRUD) allowing to perform data operations for one Class.
- Data Service pattern (DS) : This service gathers high level methods that redirects to unit DAO methods.

---

### Exercise : create a QuestionDAO and a QuizzDataService
Specifications : 
- **DAO** : contains 5 methods (create, getById, search, update, delete), that forward on the `Session` respective methods
- **DS** : contains high level methods including one method to create a `Question` and some linked `MCQChoice`s  
- Create test cases allowing to test 
### Problem : adherence to the hibernate framework

---
### Solution to adherence : using an entity manager

---






 