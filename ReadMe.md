# Agar aap **Swagger UI** ko **ekdum basic se Spring Boot mein** shuru karna chahte ho (zero se), to main aapko **step-by-step bilkul beginner friendly** way mein bata raha hoon.

---

## ✅ What is Swagger?

**Swagger UI** ek tool hai jo aapke REST APIs ko browser mein documentation form mein dikhata hai aur test karne ka interface bhi deta hai.

---

## 🔧 Step-by-Step Setup From Scratch:

---

### 🧱 1. Spring Boot Project Create karo

Aap **[https://start.spring.io](https://start.spring.io)** se create kar sakte ho:

* **Project**: Maven
* **Language**: Java
* **Spring Boot version**: Latest (e.g., 3.x)
* **Dependencies**:

  * Spring Web
  * Spring Boot DevTools
  * Spring Data JPA
  * H2 Database
  * Lombok
  * ✅ **Springdoc OpenAPI UI** (ye Swagger ke liye h)

> ⚠️ Optional: Agar "Springdoc OpenAPI UI" option nahi dikh raha ho, to aap baad mein `pom.xml` mein manually add kar sakte ho.

---

### 📦 2. pom.xml mein Swagger ka dependency add karo

```xml
<!-- Swagger (springdoc-openapi) -->
<dependency>
    <groupId>org.springdoc</groupId>
    <artifactId>springdoc-openapi-starter-webmvc-ui</artifactId>
    <version>2.2.0</version>
</dependency>
```

---

### 📄 3. Basic Controller banao

```java
package com.example.demo.controller;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class HelloController {

    @GetMapping("/hello")
    public String sayHello() {
        return "Hello from Swagger!";
    }
}
```

---

### ⚙️ 4. application.properties file

```properties
# Swagger ke liye koi special config nahi chahiye
# H2 console optional
spring.h2.console.enabled=true
```

---

### 🚀 5. Run the Spring Boot app

App run karne ke baad, browser mein ye URL open karo:

```
http://localhost:8080/swagger-ui/index.html
```

Yahan aapko:

✅ `/hello` endpoint dikhai dega
✅ Test button bhi hoga to API ko run kar ke result dekh sakte ho

---

### ✅ Final Output:

* ✅ Ek simple `/hello` API create ho gayi
* ✅ Swagger UI ke through test bhi kar sakte ho
* ✅ Beginner-friendly setup ready hai

---

### 📁 Optional: Folder Structure Overview

```
src
└── main
    ├── java
    │   └── com.example.demo
    │       ├── DemoApplication.java
    │       └── controller
    │           └── HelloController.java
    └── resources
        └── application.properties
```

---

Agar chaho to main ye **complete ZIP project** bhi bana ke de sakta hoon. Batana!
