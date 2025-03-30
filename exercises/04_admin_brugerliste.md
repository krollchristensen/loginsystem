# Øvelse 4: Admin ser brugerliste

## Mål
Vis en liste over alle brugere – kun for admin.

## Repository

```java
public List<User> findAllUsers() {
    String sql = "SELECT * FROM users";
    return jdbcTemplate.query(sql, (rs, rowNum) -> {
        User user = new User();
        user.setId(rs.getInt("id"));
        user.setUsername(rs.getString("username"));
        user.setRole(rs.getString("role"));
        return user;
    });
}
```

## Controller

```java
@GetMapping("/admin")
public String showAdminPanel(HttpSession session, Model model) {
    User currentUser = (User) session.getAttribute("currentUser");
    if (currentUser == null || !"admin".equals(currentUser.getRole())) {
        return "redirect:/login";
    }
    List<User> users = userService.getAllUsers();
    model.addAttribute("users", users);
    return "admin";
}
```

## Thymeleaf

```html
<ul>
  <li th:each="user : ${users}" th:text="${user.username}"></li>
</ul>
```
