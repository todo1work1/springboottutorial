# springboottutorial
My Spring boot learnings

### Spring Profiles
- Use of @Profile("name-of-Profile")
- Purpose => Selectively enable or disable parts of the application
- Spring profiles "provide a way to segregate parts of your application configuration and make it only available in certain environments"
- active profile when running your application => 
  - In application.properties => **spring.profiles.active**= profile-name
  - When running from commnand line => --spring.profiles.active=profile-name
- If you want to set **specific settings** only for when a certain profile is active, you can use the naming convention application-profileName.properties
- 
