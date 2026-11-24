# 📦 Products — Spring Data JPA

**Premier pas avec le mapping objet-relationnel : une entité `Product`, un repository Spring Data et des opérations CRUD.**

![Java](https://img.shields.io/badge/Java-17-ED8B00?logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.5-6DB33F?logo=springboot&logoColor=white)
![Hibernate](https://img.shields.io/badge/JPA-Hibernate-59666C?logo=hibernate&logoColor=white)
![H2](https://img.shields.io/badge/H2-in--memory-1F6FEB)

Travail pratique du module **Java / Spring** — Génie informatique, Université Mundiapolis.

---

## ⚙️ Ce que fait l'application

Au démarrage (`CommandLineRunner`) :

1. **Create** : insère trois produits
2. **Read** : `findAll()`, puis `findById(1)`
3. **Requête dérivée** : `findByNameContaining("C")`, générée automatiquement par Spring Data à partir du nom de la méthode

```java
@Entity
public class Product {
    @Id @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
    private double price;
    private int quantity;
}

public interface ProductRepository extends JpaRepository<Product, Long> {
    List<Product> findByNameContaining(String mc);
}
```

## 🚀 Lancer le projet

```bash
./mvnw spring-boot:run
```

Console H2 : http://localhost:8085/h2-console (JDBC URL : `jdbc:h2:mem:product-db`)

> Pour utiliser **MySQL** à la place, voir les instructions en commentaire dans `src/main/resources/application.properties`.

## 📸 Captures

| Entité | Repository | Tests CRUD |
|---|---|---|
| ![](captures/capture1.png) | ![](captures/capture2.png) | ![](captures/capture3.png) |

---

👤 **Saad Sabir Idrissi** — Élève ingénieur Data & IA · [Portfolio](https://saad-sabir-idrissi.vercel.app) · [LinkedIn](https://www.linkedin.com/in/saad-sabir-idrissi)
