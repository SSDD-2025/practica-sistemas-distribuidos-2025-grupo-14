Este grupo está formado por alumnos del doble grado de Ingeniería Informática e Ingeniería del Software:

ALBERTO MAYORAL GOMEZ  /  ICÍAR MORENO LÓPEZ  / JORGE RAMIREZ GAYO

# Noir & Blanc

Enlace al repositorio de github: https://github.com/CodeURJC-DAW-2024-25/webapp14.git

# PHASE 3

## 🐳 DOCKER

## 🚀 Deployment Instructions

### 🏭 **Production**

Remove the existing production compose file if needed

```
rm docker-compose.prod.yml
```

Download the latest production docker-compose file from GitHub

```
wget https://raw.githubusercontent.com/CodeURJC-DAW-2024-25/webapp14/refs/heads/main/docker/docker-compose.prod.yml
```

Deploy the application in production mode by pulling images and starting containers

```
docker compose -f docker-compose.prod.yml up
```

Now you have access by this links:

- [https://193.147.60.54:8443/index](https://193.147.60.54:8443/index)
- [https://sidi14-1.sidi.etsii.urjc.es:8443/index](https://sidi14-1.sidi.etsii.urjc.es:8443/index)

### 🛠️ **Development**

Delete docker volumes if needed

```
docker-compose down -v
```

Start the application in development mode, building the image locally

```
docker compose -f docker-compose.local.yml up
```

Now you have access by this link:

- [https://localhost:8443/index](https://localhost:8443/index)


## 📦 Building and Publishing the Image

You can build and publish the application Docker image using either Maven or Dockerfile approaches

### 📄 **Dockerfile**

If you prefer to use a Dockerfile, make sure it's present in your project

```
# Create the image
./create_image.sh

# Post the image
./publish_image.sh
```

### 🔨 **Maven Commands**

Build the project (without running tests)

```
mvn clean package -DskipTests
```

Build the Docker image using Buildpacks

```
mvn spring-boot:build-image -Dspring-boot.build-image.imageName=iciar04/webapp14:latest
```


## 🌐 Deployment Instructions with Docker

This command removes the Docker container. If the container is running, it will be stopped first and then deleted

```
docker rm -f <container-name>
```

### **Launching the Application (Server 1)**

This command runs the Spring Boot application container on Server 1, exposing it on port 8443. It connects to the MySQL database hosted on Server 2 at IP 192.168.110.35

```
docker run -d \
  --name springboot-app \
  -p 8443:8443 \
  -e SPRING_DATASOURCE_URL=jdbc:mysql://192.168.110.35:3306/shop \
  -e SPRING_DATASOURCE_USERNAME=root \
  -e SPRING_DATASOURCE_PASSWORD=password \
  iciar04/webapp14:latest
```

### **Launching the MySQL Database (Server 2)**

This command runs a MySQL 9.2 container on Server 2, exposing it on port 3306 and persisting data in the mysql_data volume

```
docker run -d \
  --name mysql-db \
  -p 3306:3306 \
  -e MYSQL_ROOT_PASSWORD=password \
  -e MYSQL_DATABASE=shop \
  -v mysql_data:/var/lib/mysql \
  mysql:9.2
```

Now you have access by this links:

- [https://193.147.60.54:8443/index](https://193.147.60.54:8443/index)
- [https://sidi14-1.sidi.etsii.urjc.es:8443/index](https://sidi14-1.sidi.etsii.urjc.es:8443/index)


## 📤 Publishing docker-compose.prod.yml as an OCI Artifact

Make sure you have oras installed.

Run the provided script

```
./docker/publish_compose.sh
```

Install oras on the remote machine

```
curl -s https://api.github.com/repos/oras-project/oras/releases/latest \
| grep "browser_download_url.*oras_.*_linux_amd64\.tar\.gz" \
| cut -d '"' -f 4 \
| wget -qi - -O oras.tar.gz && \
tar -xzf oras.tar.gz oras && \
sudo mv oras /usr/local/bin/
```

Download the artifact

```
oras pull docker.io/iciar04/spring-webapp-compose:0.1.0
```

Execute the new docker compose (check the filename)

```
docker compose -f docker-compose.prod.yml up -d
```

## 👥​ USER CREDENTIALS
    
**Admin**:
- username: laura1@gmail.com
- password: Laura.53
  
**User**:
- username: pacoG@gmail.com
- password: 12345

    
# PHASE 2

## 🤝 PARTICIPATION

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
|5|[Spring security part 4 (fixed problem with admin views)](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/0842fface070c28dc311cd83ccf8e549dd749f53)|[AdminOrdersRestController.java](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/b77f8d363120496d1f991a2b7f36eb6d01ba62af#diff-cba66e455b92c6fdec05056aeedf36f68a0c30189fb5ea605319b4e74ed4366c)

### **Jorge Ramírez Gayo**
I have worked on adapting some services and repositories for the REST API and creating their corresponding DTOs and mappers. I have also implemented the endpoints for graphs, index, searches, and images. Finally, I've helped in some security aspects like implementing the login for the REST API and improved the project.

| Nº    | Commits      | Files      |
|:------------: |:------------:| :------------:|
|1|[Updated repositories and services](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/07d0d51d97edd8585815f56401ca1c5a3ef6d13a)|[OrderService.java](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/07d0d51d97edd8585815f56401ca1c5a3ef6d13a#diff-8ba26ea880e76446fe5c0773c01c1fe78e3a5cf71c93f61f6a65ee31720ebbfb)|
|2|[Updated charts endpoint](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/3e5ca6faa0d1c460332d623af313cb26cf444ea3)|[AdminChartsRestController.java](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/3e5ca6faa0d1c460332d623af313cb26cf444ea3#diff-b28d98d2b1f5c72304ba55953e94f01d9134cbcd4b5dcfb60362c648c4541214)|
|3|[Implemented REST Login](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/3297986bfa7e305f8fb5dadf1b53f2ba12fea9f6)|[SecurityConfig.java](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/3297986bfa7e305f8fb5dadf1b53f2ba12fea9f6#diff-bacc3bb41e7e9a9f1bcdda7101702ea1209dddb58581998162859917405d312e)|
|4|[Updated index endpoint](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/b4dc47940c9dd5eddb5bef42672f7096f6e677b9)|[IndexRestController.java](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/b4dc47940c9dd5eddb5bef42672f7096f6e677b9#diff-31ba910cf314c0efcc869a689bf4308639b1d449b9550b917975658543d41f2d)|
|5|[Implemented search endpoint](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/97021bf9b27b1819bcb2263eea9d4b24b89f721f)|[SearchRestController.java](https://github.com/CodeURJC-DAW-2024-25/webapp14/commit/97021bf9b27b1819bcb2263eea9d4b24b89f721f#diff-fce8d4f9566b1df790e4fbf59051779236f35c060e708361c2241d353a5b8fcf)|
