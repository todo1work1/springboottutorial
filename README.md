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
### Use of ENUM
```
UserRoles.java
public enum UserRoles {
    OFFICER,
    CAPTAIN,
    ADMIN
}
```
```
User.java
@Entity
@Table (name="copsboot_user")
public class User {
  @Id
  private UUID id;
  private String email;
  private String password;
  @ElementCollection(fetch=FetchType.EAGER)
  @Enumerated(EnumType.STRING)
  @NotNull
  private Set<UserRole> roles;
}
```
- Use of enum to support set of UserRoles => **enum UserRole {OFFICER, CAPTAIN, ADMIN}**
- **@Entity** annotation to suggest that **persistable entity for JPA**
- **@Id** annotation to suggest the primary key, using **java.util.UUID**
- **@Table** optional annotation if you want the table name to be different from class name
- **@Enumerated(EnumType.STRING)** annotation to suggest that `enum values will be stored as string`
