# rest-api-project-template
Project template to be used as a starting point for development teams

In order to simplify the creation of new Mulesoft API Projects the DTC-Mulesoft team has created a project template for all developers to use.  This template project allows all the teams in VA to maintain a consistent project structure and meet development standards in accordance with the technical governance.

# Outlined below are the contents of the template project:

1. The Mule Configuration File Structure has five XML files.  Note that the rest-api-project-template will act as a placeholder.  This will need to be changed based on your new API name.
   
   
2. rest-api-project-template.xml
    - The entry point of your project
3. getHealthImpl.xml
    - The implementation layer, this is called by the interface. This resource is used to check  the health of the underlying systems accessed in the API. This would contain the business 
      logic and transformation specific method. 
4. scheduledHealthChecker.xml
    - The healthcheck scheduler layer, this implementation layer calls the getHealthImpl.xml to   check the health of the application.  The schedule is configured to call the healthcheck implementation layer to check on the status of the application and log the result to splunk.
5. common.xml
    - Here we consolidate all error handling in this file and later in reference within your flow
6. global.xml
    - Global configs are common configurations such as HTTP listener and request, autodiscovery ID, Jason Logger config, Error Handler config, etc. For our custom base project, we will set the basic configurations
7. Modify the pom.xml to add common dependencies that will be needed to build project
6. Log4j has been configured with Splunk appender in order to push the logs