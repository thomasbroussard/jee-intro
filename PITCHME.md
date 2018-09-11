# JEE

A practical introduction to Java Enterprise Environment

---

### What is JEE?

JEE is :
- a bundle of specifications
- meant to be implemented by some vendors

JEE is not :
- a framework
- usable as it is
- necessarily completely used

---

### Why JEE ?

JEE helps to normalize the answers given to certain problems.
- The developer is "guided" through the solution
- The solution is standard, so should not depend on the implementation
- The solution is standard (bis), so every other developer can know what was attempted

--- 


### JEE : Range of applications

JEE applies to a wide range of software needs:
- Configuration management thanks to **Dependency Injection**
- Persistence thanks to **JPA**
- Interoperability thanks to **JAX-RS** / **JAX-WS**
- MOM messaging with **JMS**
- Software presentation thanks to **JSP** / **JSF**

And many other specs that will not be covered by this course

---

### How to practice ?

In order to practice JEE, one have to setup some environment to quick test implementations of those JEE specs.

**Maven** and **Junit** will be the beginning of that test platform.


---

### Why Using Maven?

Maven is a Java tool composed of 3 main features:
- Project structuration
- Project construction
- Project dependencies resolution

---

### How is maven working ?

<iframe frameborder="0" style="width:100%;height:813px;" src="https://www.draw.io/?lightbox=1&highlight=0000ff&edit=_blank&layers=1&nav=1&title=maven.html#R7VzLdqM4EP0aL8Ph%2FVjm1TOL7nP6dBbTs1RAxkpjRAuI7fn6kUAyD8mx0xZ2nCSLGAqBxK1bpZKq7Jlzu1z%2FRUCx%2BIYTmM1sM1nPnLuZbVuu7dMPJtm0kiBwWkFKUMIbdYIH9B%2FkQpNLa5TActCwwjirUDEUxjjPYVwNZIAQvBo2m%2BNs2GsBUigJHmKQydJ%2FUFItWmloB538b4jShejZ8qP2yiOIf6UE1znvb2Y78%2BavvbwE4ln8RcsFSPCqJ3LuZ84twbhqj5brW5gxbAVs7X1fdlzdjpvAvDrkBv5CzyCroRhxM65qI7Bo3gay9ubMuVktUAUfChCzqyuqfSpbVMuMnln0kD8Okgqudw7J2r4oJRDES1iRDW3Cb%2FA5NJw6ET9ddXqIXC5b9HQQCEgB1326fXL3%2FvSAQ7ADP%2Fft4eHtB2RLJ%2F2AOG8PkP14eNZUeNgKOPyM9nDzSA9SdvCd4Cfmk7icPnF7aduWfEo%2BJZcnOcbw5yjLbnGGSXOvkwAYzmMqLyuCf8HeFT8O4eNcj6sIhq7CMhW%2BUzmZmBp8hcp1jnxFgZfGmkL0wX3FmSeUcMQS78AZ1tbBEjnieKpzRHu4Fp%2BuYR056Y5sbz6Hfqy0vSSIHk1TD6qRN0Q1jCRUrUiBqqsBVG%2Bn6ZUFyAXxMEkNQEFbQCPDaYrylH26TxTz5tO%2BijGh91%2FbhmUZVs9K%2B0%2B5fNVsIT%2BFanxJNUwNZUEo%2FHMClnCFyS%2BKeSsRGvAM04jeAdKKYHUypEMJ6a%2BYLnGp6AcscIkqzJ731uaCM0QmOK8e%2BL2WBp0746hDZV6BQulWqEHrkaT1W7yk7mrzqfeJ9e5F9n69%2B1PpXSx5%2B4qnAyfvwuDfkppDK9ivZi%2BcSM1i%2FuyhAZMUihfEpFrgFOcgu%2B%2BkN0O8etjANap%2BcjE7%2FpcdGx47o9TZ%2FBTN2El37QlW1YZv2oK6wk0oJfr9inHBb4tr8tz02sXpbKwv405fDdckFq3E7i8gKRRzo1o9BGagQs%2FDx6ugbm69JgRseg0KjPKq7D35OxP0nLo3dOquH%2FbVtre9bUYjNbcj6JS%2BfZXDeBD8AQ8GCjkTKfTxwDsLDxzndTwYtRe7l9p4EH54Hvhn4YH1Sn8wai%2FOtfFAXh1p50Gre8GEs%2Bg6PIeuXc97SXevbX%2B0rh1zcl1bks2fXtfRkbo%2BeJ%2FW%2BhBwWuaJ8BSd91Yi38AzzCWUj8ofeDBM3Jli%2Bya0Hx3f30J33FJ%2BtDXsOny67cf6qq1hX8eKTt4qkxIIP2CJM0ZE27yDBaRw5jGC5bnXa5crGaZgjiGsBvqN2RfI7FMnJnxfg1ucLqI41Pm9FGeqoxLNLjM4lcuU63Ca7M8Vy%2F0YT4Do9Z0nyb2Otr49kQ89xda3O12EdDHcPTZUPpi7cp6hlz27anNn74TDgXVCDk8Xll4Mh0%2B1BLDkrAnnMCjQVBSGFg1iAxWFIz9wgKYQdkRh3z4lhe3JKNzRj%2B3HDwmoY3uKPe87JIi%2BMyS8e33Etk%2B1FrPlrFAvsX7VpNXfh2%2F2T%2BmbxWjfX9WOEw3XHFakKNtxpoLVlmA9sG6H3vQxSnd8nkfq8kqK7KNKPzp2JBQlje%2B5eCe0xzk8VaZ3qjqpl5cwOc7hYfPjeNN%2BOzuahun2J0jLMGkcxAXjuQ%2FmyTX7Yk3XNZV8QWz4r0oFJKBcHJkTFtV9g1zgsUmgg01ALi1UxOlZhooS7qc1KIv260tztGaocD6L7xzZKoabpu83DNdet2SNitVM2fWriqW1FGw6e%2FyD1k31fWTuTGQYQNqeHgY7roLBWsoapFyUN5rPPdsxqMrcMAoiL7JCZ%2FjAdkT8GSP1vTJJJRc2K1YDF2ko3mhecBVVnVMZiv%2FykurQaaFvO4MlEyd5R%2Fq35fsdhe%2F3d2hLf6JQ9v2y27pMSrujciXPk1MNk%2Fl%2B1Zcu23i9GGDr%2F67Z92Jv6GtWVyBDaU6DSxb5w3nVXRXBPc85Uho0KbKSjZJUaA5ilus3cXvzdl1QjDNBdTaWZOiI4Yja6xgvi5rFVV3X7Lkae%2BrqfYlU9jlBb9si0wN7o8I%2BtCPzYZ0O7URhBOxPtShovmhNLasd811Mh8YC2BtmGojCf80vLFGSZLtMdOg7FT7ruPWbNVy%2FqdMiiurRINBgabszyjosLUNlY1oE%2Fq4RaZLSySApbYKcCQvKFAqYsM26Qjgv1aZ4SewoxJKJ3UKXv7xN2Z59ZdA5d24n%2BcGV62nauXHsIbMswzsdtXx5R0wntRK8yjMMkrEX54SqWcSLmn%2BsdbVg5IozUFKo6auzX4Ag3PciFhRg1or2AZZMp%2B1%2FRsc6%2F6ThsZFENCx49cVvKkzAQnra%2FVRGu0bpfo%2FEuf8f"></iframe>

---
### POM file : example

```
<project xmlns="http://maven.apache.org/POM/4.0.0" 
xmlns:xsi=http://www.w3.org/2001/XMLSchema-instance
xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<groupId>fr.epita.quiz</groupId>
	<artifactId>quiz-core</artifactId>
	<packaging>jar</packaging>
	<version>0.0.1-SNAPSHOT</version>
</project>

```
@[1-3,9](This is the project root)
@[4](identifies the project model version)
@[5](groupId: group of projects the artifact belongs to)
@[6](artifactId: name of the project)
@[7](type of binary)
@[8](version)

---

### First exercise create a maven project

In this exercise, you have to define a list of dependencies




