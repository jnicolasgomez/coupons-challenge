# coupons-challenge
Rest API made in Java that returns list of items a person can get that doesn´t exceed the coupon maximum amount.

# Nivel 1 
### Getting Started
1. Clonar el repositorio
2. Para ejecutar con maven, en la carpeta del repositorio ingresar los siguientes comandos 

  `mvn compile`
  
  `mvn spring-boot:run`
  
 El servicio queda corriendo en el puerto 8080
 
 **Nota:** el nivel 1 del challenge se encuentra en la clase coupons-challenge/src/main/java/com/challenge/coupons/services/CouponServiceStub.java

# Nivel 2 
### Endpoints
**POST /coupon/**

Body:

`{
    "items_ids": ["MLA811601010","MLA816019440","MLA810645375"],
    "amount":150000
}`
# Arquitectura

Se usa un servicio de cache con Redis para mejorar el performance, guardando como llave valor el id del item y el precio.

![alt text](https://github.com/JuanNicolasGomez/coupons-challenge/blob/master/architecture_diagram.jpg)

# Nivel 3 
### URL api
http://ec2-100-25-29-239.compute-1.amazonaws.com:8080/coupon/

# Pruebas de carga
Con 100000 peticiones:

Se logro un throuput promedio de 2259 peticiones por segundo en **maquina local**

![alt text](https://github.com/JuanNicolasGomez/coupons-challenge/blob/master/load_test.png)

En instancia **t2.micro** se logro un throuput de 181 peticiones por segundo

![alt text](https://github.com/JuanNicolasGomez/coupons-challenge/blob/master/load_testAws.png)



