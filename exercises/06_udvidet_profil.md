# Øvelse 6: Udvidet brugerprofil

## Mål
Gem og vis navn og e-mail.

## Database

```sql
ALTER TABLE users ADD COLUMN name VARCHAR(100);
ALTER TABLE users ADD COLUMN email VARCHAR(100);
```

## User.java

```java
private String name;
private String email;
```

## register.html

```html
<label>Navn:</label>
<input type="text" th:field="*{name}">
<label>Email:</label>
<input type="email" th:field="*{email}">
```
