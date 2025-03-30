# loginsystem
Disse øvelser bygger videre på jeres eksisterende login-system. De hjælper jer med at tilføje UI-visning, adgangsbeskyttelse, roller, validering, brugerliste og profilside – uden at bruge JPA.

##  Målgruppe
- Studerende, der har arbejdet med:
  - Spring Boot
  - Thymeleaf
  - JdbcTemplate (ingen JPA)
  - Session og controller-flow

##  Øvelser
| Nr | Titel                                      | Beskrivelse |
|----|--------------------------------------------|-------------|
| 1  | [Navbar med session](01_navbar_session.md) | Vis loginstatus øverst på alle sider |
| 2  | [Adgangskontrol](02_adgangskontrol.md)      | Beskyt `/welcome` for ikke-loggede brugere |
| 3  | [Rollefelt](03_rollefelt.md)                | Tilføj brugerroller og UI-styring |
| 4  | [Brugerliste for admin](04_admin_brugerliste.md) | Kun admin kan se alle brugere |
| 5  | [Inputvalidering](05_input_validering.md)   | Kræv korrekte felter ved registrering |
| 6  | [Udvidet profil](06_udvidet_profil.md)       | Gem navn og e-mail sammen med bruger |
| 7  | [Profilside](07_profilside.md)              | Vis personlig side med brugerdata |



##  Klar til brug
```bash
git clone https://github.com/krollchristensen/loginsystem.git
cd loginsystem/exercises
```



