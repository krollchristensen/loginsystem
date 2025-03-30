# Øvelse 7: Brugerspecifik profilside

## Mål
Vis information om den aktuelle bruger.

## Controller

```java
@GetMapping("/profile")
public String showProfile(HttpSession session, Model model) {
    User user = (User) session.getAttribute("currentUser");
    if (user == null) return "redirect:/login";
    model.addAttribute("user", user);
    return "profile";
}
```

## profile.html

```html
<h2>Din profil</h2>
<p><strong>Brugernavn:</strong> <span th:text="${user.username}"></span></p>
<p><strong>Navn:</strong> <span th:text="${user.name}"></span></p>
<p><strong>Email:</strong> <span th:text="${user.email}"></span></p>
<p><strong>Rolle:</strong> <span th:text="${user.role}"></span></p>
```
