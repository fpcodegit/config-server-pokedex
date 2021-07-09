###Simple config server that will provide centralize configurations for apps

All the needed configuration are in:

1. ConfigServerConfiguration class
1. application.properties
1. build.gradle

This will point to another Git repository where the properties are for the apps and profiles 
in the format "app name"-"profile".properties o .yml according to your needs

https://github.com/fpcodegit/config-server-repo

In the previous Url we provided the specific location from where the UI will consume the API in the heroku environment