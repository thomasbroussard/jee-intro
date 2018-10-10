# JEE : Web Services

---
### Web Services : Why ?
Web services are really useful to : 
- reuse some code that run on an other system
- make two different technologies inter-operable
- open your system to external consumers

---
### Web Services : How ?

There are two kinds of web services :
- SOAP (Simple Object Access Protocol) --> XML based messages  
- REST (Representational State Transfer) -->  HTTP based messages

---
### SOAP services in java
- SOAP services development and deployments are available built-in since Java 6
- The SOAP Services are implemented using annotations
- Those annotations avoid to define a WSDL file, as it is based on class structure

---
### Java SOAP annotations : defining contract

```
package fr.epita.quiz.services.web;

import java.util.List;

import javax.jws.WebMethod;
import javax.jws.WebService;

import fr.epita.quiz.services.web.transport.QuestionMessage;

@WebService
public interface QuizWS {

	
	@WebMethod
	public void saveQuestion(QuestionMessage questionMessage);
	
	@WebMethod
	public List<QuestionMessage> listQuestions(QuestionMessage questionMessageCriteria);
	
}

```

---

### Java SOAP execution : defining implementation





