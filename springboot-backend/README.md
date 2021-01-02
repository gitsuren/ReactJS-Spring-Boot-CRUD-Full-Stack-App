# ReactJS-Spring-Boot-CRUD-Full-Stack-App - MYSQL instance on DOCKER SetUp

`$ docker run --name=mysqlDB -e MYSQL_ROOT_PASSWORD=root -p 127.0.0.1:3307:3306 mysql/mysql-server:latest`

`shell> docker logs mysql1 2>&1 | grep GENERATED`
GENERATED ROOT PASSWORD: Axegh3kAJyDLaRuBemecis&EShOs

`$ docker exec -t mysqlDB bash`

`shell> mysql -u root -p`
Enter Password: Axegh3kAJyDLaRuBemecis&EShOs

CREATE USER 'username'@'localhost' IDENTIFIED BY 'password'; 
GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' WITH GRANT OPTION; 
CREATE USER 'username'@'%' IDENTIFIED BY 'password'; 
GRANT ALL PRIVILEGES ON *.* TO 'username'@'%' WITH GRANT OPTION; FLUSH PRIVILEGES;


In SpringBoot app:
>> application.properties:
	spring.datasource.url=jdbc:mysql://localhost:3307/employee_management_system?useSSL=false
spring.datasource.username=username
spring.datasource.password=password
