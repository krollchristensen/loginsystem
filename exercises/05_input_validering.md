# Øvelse 5: Inputvalidering

## Mål
Undgå at brugeren indtaster tomme eller for korte felter.

## Trin 1: Dependency i pom.xml

```xml
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-validation</artifactId>
</dependency>
```

## Trin 2: Tilføj validering i `User.java`

```java
@NotEmpty
@Size(min = 3)
private String username;

@NotEmpty
@Size(min = 6)
private String password;
```

## Trin 3: Opdater controller

```java
@PostMapping("/register")
public String register(@Valid @ModelAttribute User user, BindingResult result, Model model) {
    if (result.hasErrors()) return "register";
    ...
}
```
