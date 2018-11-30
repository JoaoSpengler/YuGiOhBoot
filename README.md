# YuGiOh Boot
### Definição da conexão
````java
spring.datasource.driver-class-name=com.mysql.jdbc.Driver
spring.datasource.url=jdbc:mysql://localhost:3306/ygodb?useUnicode=true&useJDBCCompliantTimezoneShift=true&useLegacyDatetimeCode=false&serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=superabc
server.port=8080
````
### Definições do JPA
````java
spring.jpa.database = MYSQL
spring.jpa.show-sql = true
````
### Configurações do Hibernate
````java
spring.jpa.hibernate.ddl-auto=create
spring.jpa.properties.hibernate.dialect = org.hibernate.dialect.MySQL5Dialect
````
### Característica de cada carta
##### As cartas possuem cinco atributos:

* Id;
* Nome;
* Efeito;
* Tipo da Carta:
    * Monster;
    * Spell;
    * Trap;
* Atributo:
    * Water;
    * Fire;
    * Earth;
    * Wind;
    * Dark;
    * Light

# Métodos

### GET ``/card/all`` - pegando a lista de cartas
Output
```json
[  
   {  
      "id" : 1,
      "name" : "Dark Magician",
      "effect" : "",
      "type" : "",
      "attr" : ""
   },
   {  
      "id" : 2,
      "name" : "Caribou",
      "effect" : "",
      "type" : "",
      "attr" : ""
   }
]
```
### POST ``/card`` - criando um novo registro
Input
```json
{  
      "name" : "Time mage",
      "effect" : "time warp",
      "type" : 1,
      "attr" : 6
}
```
Output
```json
[
    {  
      "id" : 3,
      "name" : "Time mage",
      "effect" : "Time warp",
      "type" : "Monster",
      "attr" : "Light"
    }
]
```
### GET ``/card/{id}`` - pegando uma carta específica por Id
Output
```json
[
    {  
      "id" : 3,
      "name" : "Time mage",
      "effect" : "Time warp",
      "type" : "Monster",
      "attr" : "Light"
    }
]
```
### PUT ``/card/id``- Atualiza o registro de uma carta através do Id
Input
```json
[
    {  
      "id" : 3,
      "name" : "Time mage",
      "effect" : "Time warp",
      "type" : 3,
      "attr" : 2
    }
]
```
Output
```json
[  
    {  
      "id" : 3,
      "name" : "Time mage",
      "effect" : "Time warp",
      "type" : "Trap",
      "attr" : "Fire"
    }
]
```
### DELETE ``/card/{id}`` - Deletando uma carta através do Id
Output
````json
200 (OK)
````
