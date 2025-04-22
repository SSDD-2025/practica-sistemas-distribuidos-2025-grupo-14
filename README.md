Este grupo está formado por alumnos del doble grado de Ingeniería Informática e Ingeniería del Software:

ALBERTO MAYORAL GOMEZ  /  ICÍAR MORENO LÓPEZ  / JORGE RAMIREZ GAYO

# Noir & Blanc

Enlace al repositorio de github: https://github.com/CodeURJC-DAW-2024-25/webapp14.git

### 🤝 PARTICIPATION

### **Alberto Mayoral Gómez**

I have been responsible for adapting the files related to the Product entity when developing the REST API. This included creating the corresponding DTOs, adapting the ProductService, and modifying the involved Controllers. I also created the endpoints for these requests in the RestController files. Additionally, I took care of part of the security for the REST API and ensured the correct use of response codes. Lastly, I generated a Postman file to verify the correct implementation of the endpoints and the corresponding documentation (apidoc)

Additionally, I have collaborated on the security aspect regarding access to certain pages, providing error and authentication pages. Finally, I have also contributed to correcting and improving the website in general

| Nº    | Commits      | Files      |
|:------------: |:------------:| :------------:|
|1|[RestControllers Adapted and Added with new Endpoints](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/cb3aa89e3f4fbb59584e0237aca05a8e994c8e8c)|[ProductService.java](https://github.com/CodeURJC-DAW-2024-25/webapp14/blob/main/backend/src/main/java/es/codeurjc/webapp14/service/ProductService.java)|
|2|[Spring Security (csrf / roles / permissions)](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/a05b59a55c7a317f7c9ca3385f30b18d0bda5452)|[AdminProductsRestController.java](https://github.com/CodeURJC-DAW-2024-25/webapp14/blob/main/backend/src/main/java/es/codeurjc/webapp14/controller/rest/AdminProductsRestController.java)|
|3|[Product Service Adapted to DTO](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/05969bf675d92bc4a416897e5afd8ba0f66dae4f)|[ReviewRestController.java](https://github.com/CodeURJC-DAW-2024-25/webapp14/blob/main/backend/src/main/java/es/codeurjc/webapp14/controller/rest/ReviewRestController.java)|
|4|[REST Controller for Cart and Admin (users and products), and Refactoring](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/bc178f2b704bc0affb8bbb7eaeeba5f287a7ea04)|[SecurityConfig.java](https://github.com/CodeURJC-DAW-2024-25/webapp14/blob/main/backend/src/main/java/es/codeurjc/webapp14/security/SecurityConfig.java)|
|5|[Added handler for 401 and 403 status codes in Services and fixed Security](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/07de66f223028cec1fb2f65c3763aac2079b5e67)|[RegisterRestController.java](https://github.com/CodeURJC-DAW-2024-25/webapp14/blob/main/backend/src/main/java/es/codeurjc/webapp14/controller/rest/RegisterRestController.java)|

### **Icíar Moreno López**

I have been responsible for the user logic in the backend of the application. This included creating the respective DTOs and a mapper, adapting the controllers and services, and creating the REST controllers to manage user operations. In addition, I have contributed to the security implementation of the application, reviewed code for potential vulnerabilities, and fixed bugs to improve the overall quality of the application

| Nº    | Commits      | Files      |
|:------------: |:------------:| :------------:|
|1|[Added UserRestController and UserOrdersRestController](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/7b48ef4dd892d30895db5d5f6a338f34be198e36)|[UserService.java](https://github.com/CodeURJC-DAW-2024-25/webapp14/blob/main/backend/src/main/java/es/codeurjc/webapp14/service/UserService.java)
|2|[Added UserController and UserService](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/f072286cf775ffecad41c6afd2a5b8af78b8fabe)|[UserRestController.java](https://github.com/CodeURJC-DAW-2024-25/webapp14/blob/main/backend/src/main/java/es/codeurjc/webapp14/controller/rest/UserRestController.java)
|3|[Added user DTOs and implemented mapper](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/034cd6af63a7e4ab48f4a3e5fc916befebd6308e)|[UserController.java](https://github.com/CodeURJC-DAW-2024-25/webapp14/blob/main/backend/src/main/java/es/codeurjc/webapp14/controller/web/UserController.java)
|4|[Spring security (part 3) and general fixes](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/e34150d927fa909010e8e7e56e95a85a9ed18185)|[UserOrdersRestController.java](https://github.com/CodeURJC-DAW-2024-25/webapp14/blob/main/backend/src/main/java/es/codeurjc/webapp14/controller/rest/UserOrdersRestController.java)
|5|[Spring security part 4 (fixed problem with admin views)](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/0842fface070c28dc311cd83ccf8e549dd749f53)|[AdminOrdersRestController](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/b77f8d363120496d1f991a2b7f36eb6d01ba62af#diff-cba66e455b92c6fdec05056aeedf36f68a0c30189fb5ea605319b4e74ed4366c)
