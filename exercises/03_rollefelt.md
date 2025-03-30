# Øvelse 3: Tilføj brugerroller

## Mål
Giv brugere roller som `user` eller `admin` og vis forskelligt indhold.

## Trin 1: Opdater database

```sql
ALTER TABLE users ADD COLUMN role VARCHAR(20) DEFAULT 'user';
```

## Trin 2: Tilføj felt i `User.java`

```java
private String role;
public String getRole() { return role; }
public void setRole(String role) { this.role = role; }
```

## Trin 3: Udvid Thymeleaf (fx navbar)

```html
<span th:if="${session.currentUser.role == 'admin'}">
    | <a href="/admin">Adminpanel</a>
</span>
```
