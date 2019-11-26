---
title: "Scheduling a Java Service"
id: ""
---
---

Learn how to schedule a Java Service to trigger at certain intervals. 

The steps include: 

- How to schedule a Java service and trigger it.
- The scheduler will be a Spring scheduler which will schedule the java service and trigger it at certain intervals.

## Java Service Method 

We will be using the following Java Service Method:

```
package com.testschedulterandemail.simplejavaservice;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

//import com.testschedulerandemail.simplejavaservice.model.\*;
import com.wavemaker.runtime.service.annotations.ExposeToClient;

/**
 * This is a singleton class with all of its public methods exposed to the client via controller.
 * Their return values and parameters will be passed to the client or taken
 * from the client respectively.
 */
@ExposeToClient
public class SimpleJavaService {
    private static final Logger logger=LoggerFactory.getLogger(SimpleJavaService.class);
    public String sampleJavaOperation() {
        String result = null;
        try {
            logger.warn("Starting sample operation");
            result = "HELLO SERVICE!";
            logger.warn("Returning {}", result);
            return result;
        } catch (Exception e) {
            logger.error("Sample java service operation has failed", e);
            throw e;
        }}}
```

open `javaservice_name.spring.xml` file to get the `id` for Java service. For example, `simpleJavaService`.

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:security="http://www.springframework.org/schema/security" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd http://www.springframework.org/schema/mvc http://www.springframework.org/schema/mvc/spring-mvc.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx.xsd http://www.springframework.org/schema/security http://www.springframework.org/schema/security/spring-security.xsd">
    <bean class="com.testschedulerandemail.simplejavaservice.SimpleJavaService" scope="singleton" lazy-init="true" id="simpleJavaService"/>
    <bean class="com.testschedulerandemail.simplejavaservice.controller.SimpleJavaController" id="simpleJavaController"/>
</beans>
```

The task details include:

- `cron` referring to the time interval string we used corresponds to: _\*/10 \* \* \* \* ?_.  

The time interval specified is in the UNIX cron format ([refer here](https://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/scheduling/support/CronSequenceGenerator.html)). 

[![](/learn/assets/cronformat.png?v=10)](/learn/assets/cronformat.png)

- _`method`_ refers to the Java method to be invoked at the above-mentioned time intervals
- _`id`_ refers to the id given to the bean class for the Java controller

The following annotation should be added in _project-user-spring.xml_ file, including the id `simpleJavaService` from the `javaservice_name.spring.xml` file. 

```xml
  <beans xmlns="http://www.springframework.org/schema/beans"
		xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
		xmlns:task="http://www.springframework.org/schema/task" 
		xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd
		http://www.springframework.org/schema/task http://www.springframework.org/schema/task/spring-task-4.0.xsd">
        <task:annotation-driven scheduler="taskScheduler" />
        <task:scheduler id="taskScheduler" pool-size="5" />
        <task:scheduled-tasks>
            <task:scheduled cron="*/10 * * * * ?" method="sampleJavaOperation" ref="simpleJavaService"/>
        </task:scheduled-tasks>
</beans>
```

<iframe width="708" height="560" src="https://docs.google.com/presentation/d/e/2PACX-1vRyRnyxwtJeQye7djWn32axB7krcI7l8v52snl8k9whVxm4Zt4ILILc0mprQW0Mor-gFQU7n9iLV1e0/embed?start=false&amp;loop=false&amp;delayms=3000" frameborder="0" allowfullscreen="allowfullscreen" mozallowfullscreen="mozallowfullscreen" webkitallowfullscreen="webkitallowfullscreen"></iframe>

## See Also

[How to send emails using Java Service](/learn/how-tos/sending-email-using-java-service/)  
[How to implement forgot password feature using Java Service](/learn/how-tos/implementing-forgot-password-feature-using-java-service/)  
[How to access REST APIs from Java Service](/learn/how-tos/accessing-rest-apis-java-service/)  
[How to accomplish Pre-Post Processing for a DB Service APIs](/learn/how-tos/pre-post-processing-db-service-apis/)  
