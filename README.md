###Simple config server that will provide centralize configurations for apps

All the needed configuration are in:

1. ConfigServerConfiguration class
1. application.properties
1. build.gradle

This will point to another Git repository where the properties are for the apps and profiles 
in the format "app name"-"profile".properties o .yml according to your needs

https://github.com/fpcodegit/config-server-repo

In the previous Url we provided the specific location from where the UI will consume the API in the heroku environment

#####Deploy instructions
######Heroku:
1. As the project is gradle based, it required some extra configuration in the build.gradle, the task stage was add
 to work with the Heroku deployment steps.
    ```
    task stage(dependsOn: ['bootJar']) {
        doLast {
            'bootJar'
        }
    }
    ```
1. As the platform requirements we need to specify that we have a web type project, so we create a ***Procfile*** 
with the information. The format is ```<type>: command to run the application```
1. In Heroku website:
    1. Access your account.
    1. Create a new app.
    1. Connect the app to Github repository.
    1. Use manual deploy to deploy the current state of the master branch 
    (remember to have this branch in a running state)

Adding the gradle task and creating the Procfile is one time task only.
