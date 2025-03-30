# Øvelse 2: Adgangskontrol på /welcome

## Mål
Gør så man ikke kan tilgå `/welcome` uden at være logget ind.

## Trin: Opdater controller

```java
@GetMapping("/welcome")
public String showWelcome(HttpSession session, Model model) {
    User user = (User) session.getAttribute("currentUser");
    if (user == null) {
        return "redirect:/login";
    }
    model.addAttribute("username", user.getUsername());
    return "welcome";
}
```
