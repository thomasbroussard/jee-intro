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
With Spring, you can inject the different components of the Hibernate configuration

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
 


 