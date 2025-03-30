# Øvelse 1: "Husk mig" – Vis loginstatus i navbar

## Mål
Vis login-status i toppen af alle sider (fx “Logget ind som Emil” eller “Ikke logget ind”)

## Trin 1: Opret Thymeleaf fragment

**Fil:** `templates/fragments/navbar.html`

```html
<div style="background: #3498db; padding: 10px; color: white;">
    <span th:if="${session.currentUser != null}">
        Logget ind som <strong th:text="${session.currentUser.username}"></strong> |
        <a href="/logout" style="color:white;">Log ud</a>
    </span>
    <span th:if="${session.currentUser == null}">
        Du er ikke logget ind |
        <a href="/login" style="color:white;">Log ind</a>
    </span>
</div>
```

## Trin 2: Indsæt i dine HTML-sider

```html
<div th:replace="fragments/navbar :: *"></div>
```
