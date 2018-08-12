IOC containers

1. core - BeanFactory
2. J2EE - ApplicationContext
            |
           ConfigurableApplicationContext.

containers will do

1. Create instance for pojo classes.
2. manage life cycle of pojo classes.
3. Dependency injection into pojo classes.

spring.xml
dtd
<beans xsd>      // validation you xmls
  <bean>
  </bean>
</beans>
  
  
IOC using SAX - wellformed and validation of xml file.  

Bean Factoy 
Singleton - loading time first instance creation.
prototype - create instance based on user request


AuthorizatonContext
Singleton - Only one instance by first user request then it will not create any object on subsquent request.
prototype - create instance based on user request. 

Pratical 
1. spring beans,core,context,common logging
 
Either constructor access is private or public, it can create access.
Reflection concept use inside it - IOC container to create classes.



1. POJO instantions
2. Life cycle management
3. DI
   Passing required parameters to pojo classess from XML
4. 2 types of DI 
  1. setter 
  2. constructor
  
  
