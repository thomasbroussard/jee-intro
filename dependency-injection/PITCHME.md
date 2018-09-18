# JEE : Dependency Injection

---

### Dependency Injection : Why?
Dependency Injection (DI) has been proposed to improve the following situations:
- Creation of instances that need heavy configuration (Builder pattern)
- Cases where the instantiation details need to be hidden (Factory pattern)
- Protection of instance creation (Singleton)

---

### Dependency Injection : How ?
The principle on what the Dependency Injection is made in Java (but not only!) relies on :
- Construction of a context that will contains all the instances to inject
- Flags in the code indicating what and where to inject

---

### Dependency Injection : How ? (2)

<iframe frameborder="0" style="width:100%;height:600px;" src="https://www.draw.io/?lightbox=1&highlight=0000ff&edit=_blank&layers=1&nav=1&title=dependency-injection.html#R7VpLk9o4EP41VCWHmbJsY%2BPjQCaPqk1tqjjs5qjBwjgRliPLPPLr07LkFzIsD5PJDsMF1Gq1Wt3qr1tdDJzJcvOB43TxmYWEDmwr3AycdwPbRo7nwpekbBXF9x1FiHgcaqaaMI1%2FEk20NDWPQ5K1GAVjVMRpmzhjSUJmokXDnLN1m23OaHvXFEfEIExnmJrUf%2BJQLBR1ZPs1%2FSOJo0W5M%2FICNfOEZ98jzvJE7zewnXnxUdNLXMrSB80WOGTrBsl5HDgTzphQv5abCaHStqXZ1Lr3e2YrvTlJxFELtB4rTHNSquxRWDt%2BkuqJrTaJ9yOXOo3nLBF3WeGwB2BAQbqpJ%2BFXpL%2BVCP4q4yXL%2BD9SntN2E4qzDHBNi4KwfOpXRbu12C6AiMhQt2B6vYgFmaZ4JmfXANxAW4glhRGCn5ng7DuZMMp4sdoJPN%2FBXjVTAqGt1dGojQI9bqy0io%2Bkx5Q26ASFQ%2BJXmq4IF2SzF7lQhYeQZwhbEsG3wKIXuK6GLp1iAITVeF0DNmiiaIsGWLsjTcQ6SUSV7Boo4YfGyj24iQxjkxBSiB4yLhYsYgmmjzV1PMv5qvCGNHfbNw0%2FkE0s%2FpXk%2BwCV46%2FF2EVDPf5CeAw6E66Xg834Vi0alsOveu4bEWKrnYVzwYBUq%2FcXY6ne91ifqoPL0x72HBiH5XymuWydxTGPiOYKuv3LCcUiXrWlX%2BIr20hxn5JvUDXELAHyBI5JNuKM%2BCsCbycE33wmS8a3b3sSZ14ySqEGkpcJKodUEmeU5eGx0X0ohnuISdtvx6RnGSGJgo6QRE4PIekYbu6I0cp8%2F2EunKWqrpzHGxmkO%2FZzuvDSsjxPod5u5DTopcW9cqyVQ31AYtv6TjA0zD%2FssP6wB%2BN7vwEOS%2FC7BNjsLvdcBGzuhSiml35hMWxSR9LIafkSIbstQgGpXlX76YFzvG2wpZIh278Psoed%2B9RuVxLrS1Cd8ah74R7E3p5QsmcIn0JyxRQYw6vBeAnecLcwpYSyiOMlMKaNvN6aayT8k%2Bu46oKfX8f1D072yAQn5HegU8l3CTr5xi20byw1IKtt%2FsDMzNdKDYFh%2FDKqwnjVGVYymO8gAqNExRUlcwlZxT20TnqsZSlOenjynS9iJl98MPsw8CtxXc8%2BoCldDXJhpDb1Buy2%2Fw3%2Far0jRLiWSrM3Y7Sp4HESFXvyJX6xxzwYFi%2FomP67E8%2B1p75KmDgio9dN%2B79zQeOE%2FOGV1GinlHLNzhfqyubI66PzZbZTnBsrpoZe2wHVI%2Bo3VFPIbHO4N2Z%2Bf6eWdS3z%2Fl%2FN%2FEPD%2FHnR0b9S96Pv5i3FT4SOK7wrWRImQe%2FMDgjSF%2FCI3q72oHVvOU67wXHnasue2zgpWdh8nhFh%2BPS0tgUy%2Bxbn5c7D%2BdEo%2BNqPhvHzPRpOKjyutlvzdJIbF8UIiLMSspavqjdvn9cczf3wPdz%2B90X5%2BSep9Swl41GKvRZ5JxR5rnfFIg%2BG9V9OFFzW%2F%2BtxHn8B"></iframe>

---

### DI : How to implement ?
To implement DI, several frameworks exist :
- CDI
- Spring
- Guice
- Dagger

Spring is among the most used, this is why the examples will be shown with Spring

---

### Using Spring for Dependency Injection

- Spring is a framework having lots of aspects, it has first been proposed to address the DI implementation.
- The library we use is named **spring-core**

---

### Warnings before you start

- Dependency Injection has nothing to do with Maven dependencies!
- Spring is a provider of Dependency Injection, so it is preferable to keep with the specs apis and let Spring doing its job behind the scenes, it will allow to change provider if needed.

---
### How to define what we inject : Injection/Application Context

Spring relies on two ways to define the dependencies to be injected:
- A File-based application context : an xml file that defines all the instances and their internal values
- A Bean Based application context : an Java class containing all the configuration for the project

---
### How to define what we inject (2) : Beans

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xmlns:context="http://www.springframework.org/schema/context" xmlns:mvc="http://www.springframework.org/schema/mvc"
	xsi:schemaLocation="http://www.springframework.org/schema/beans
        http://www.springframework.org/schema/beans/spring-beans.xsd
		http://www.springframework.org/schema/context
		http://www.springframework.org/schema/context/spring-context.xsd
        http://www.springframework.org/schema/mvc
    	http://www.springframework.org/schema/mvc/spring-mvc.xsd">

	<bean id="firstQuery" class="java.lang.String">
		<constructor-arg><value>select * from Questions</value></constructor-arg>
	</bean>


</beans>
```
@[1,15](the tag that will contain all the beans definitions)
@[2-8](namespaces definitions)
@[10-12](the "Bean" definition, here a string to initialize an SQL query)
@[11] Notice the "constructor-arg" tag which allows to describe how the instance is constructed.

---
### How to Inject a dependency : Inject vs Autowired

If you want now to inject the bean in your program, then you have to use an injection flag:
- @Autowired annotation comes from Spring
- @Inject annotation comes from the standard specification

---
### How to Inject a dependency 2 : Named vs Qualifier

If you want now to prepare more than one bean of the same type, you are forced to precise the id of this bean.
- using @Qualifier (from Spring)
- using @Named (from standard)

---
### How to compose beans using Spring


---
### Spring Sterotypes


---
### Automatic scan and injection

---
### Using Spring with JUnit

---
### Exercise : Inject a simple DataSource using Spring
 




 
