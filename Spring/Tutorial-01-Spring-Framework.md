# Spring Framework.

```
Developer name - Rod Johnson
Organization - Spring organization , pivotel
Intial name - Interface 21 then -> Spring

Spring came as a alternative for EJBs. 

```
## Feature of spring

```
1. Platforms Dependency

Comparing EJBs are heavy weight and tightly couples whereas Spring make application light weight and lossely coupled. why ? 


EJBs are using OS dependencies.
Spring are not having OS dependenices , it just uses JDKs.

EJB - application server dependency.
Spring - No application server dependency. [simple JDKs library]

2. Loosley coupled
TWo classes are tightly coupled means one class object is created in other clss. 
In order to make it loosely coupled , we can create interface and implemented their methods in a class. In another class create object through interface will make them loosely coupled. 

eg. 

View | Controller | model 
                      1. Services
                      2. Business  - web txs , web sec or jboss txs , jboss sec.
                      3. DAOs  - JDBC , HIBERNATE , JPA , IBATIS [ORM TOOL]

If I implement all DAOs by a interface then if there is any needs to be implemented [change in service from jdbc to hibernate ] then business need to much change adn it is flexible to implement => loosley coupled. 

=> loosely coupled implemented by polymorphism.

3. POJO - plain old java objects.

In case of ejb in order create class we need to implement somthing but incase of sping we can do it by pojo classes.


All layers can be implementes by pojo class.

We can use is-a or has-a relationship and implement pojo classes. In order to achieve loose coupling just We need to implement interfaces instead of extending class.

** Spring recommending has-a replationship instead of extending class is-a .


By using runtime and association (has-a)  - complete spring is implemented spring

** To manage this pojo classes - we want to have container support.

4. IOC - INVERSION OF CONTROL  - possibe because of containers.

IOC - Read xml -> POJO classes providing has-a - possible by IOC
Runtime polmorphism and HAS-A , make our layer light weight. 

IOC 

container --> core  - bean factory  I  -- XMLBeanFacotry C
          --> J2EE  - ApplicationContext   I  
                            | 
                      configurableApplicationContext - I
                            |
                      ClassPathXMLApplicationContext - C      

By using IOC, MVC is build.

MVC
----> WEB - WebApplicationContext   I
                     | 
            WebApplicationContextUtils
                factory class          
            
   How to start this class
   1. To start any app - main method required
   2. main method - create obj of core container 
        new XMLBeanFacotry();
        new ClassPathXMLApplicationContext();
        
   Tomcat class - driver class - servlet application.
    under init method ()
    
container task
---------------
Read XML file
Instance of your bean
manage life cycle of bean
dynamic parameter pass to servlet class, init and context parameters.  [ Dependency Injection ]

==============================================================================
Main asset of IOC = dependency injection [ pass from xml file to pojo classes ].
==============================================================================
Implemented by Runtime polymorphism - implementes DI.

Tomcat comes up with servlet container then they will do the task.

```
## Example

```
Hello world
1. pojo class -------- class test { public void hello(){ sop("hello")}}
2. xml class  -------- SPRING xml FILE
3. driver class ------ main method containing class

```

