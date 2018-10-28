
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

```
package fr.epita.quiz.services.web;

import java.util.List;

import javax.inject.Inject;

import org.apache.logging.log4j.LogManager;
import org.apache.logging.log4j.Logger;

import fr.epita.quiz.services.data.QuestionDS;
import fr.epita.quiz.services.web.transport.QuestionMessage;

public class QuizWSImpl implements QuizWS{

	private static final Logger LOGGER = LogManager.getLogger(QuizWSImpl.class);
	
	@Inject
	private QuestionDS ds;
	
	@Override
	public void saveQuestion(QuestionMessage questionMessage) {
		LOGGER.info("questionMessage {}", questionMessage);
		//ds.createQuestionWithChoices(questionMessage, questionMessage.getMcqChoiceLabel());
	}

	@Override
	public List<QuestionMessage> listQuestions(QuestionMessage questionMessageCriteria) {
		// TODO Auto-generated method stub
		return null;
	}
	

}
```
---
### Java SOAP execution : defining configuration 
the configuration has to be made in 2 places :

- the web.xml part to configure the cxf servlet (web deployment descriptor)
- the applicationContext.xml (if you use spring)


---
### Java SOAP execution : web.xml configuration












