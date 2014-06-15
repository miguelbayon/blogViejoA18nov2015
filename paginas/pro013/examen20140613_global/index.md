---
layout: page
title:  "Examen: La batalla de las Termopilas"
---

<style>
h3 {
    margin-top: 25px;
}
</style>


### Enunciado

<div class="row">

    <div class="col-md-4" markdown="1">

En el 480 a.C. en el paso de las Termópilas, un gran ejército persa de 300.000 hombres se enfrentó a otro ejército formado por 7.300 ciudadanos griegos (incluyendo 300 espartanos). 

El final de la historia es bien conocido, sobretodo después de que fuera llevada al cine el la película "Los 300": los persas, con mucho más esfuerzo del que creían, acabaron derrotando a sus adversarios.

</div>
<div class="col-md-7 col-md-offset-1">
    <img src="/images/300.jpg" class="img-responsive">
</div>
</div>

Se pide que realices una aplicación que nos permita simular qué habría pasado en dicha batalla si el número de contendientes hubiera sido diferente. Para ello has de saber que:

1. Los guerreros espartanos eran ciudadanos griegos que vivían en Esparta. Al igual que sus compatriotas, dominaban la espada (unos más y otros menos) pero tenían una habilidad especial que no tenían el resto de griegos: tener escudos de bronce y saber manejarlos.

2. Los guerreros persas utilizaban el hacha para el combate, la cual, como los espartanos, manejaban unos mejor que otros.

3. Dentro del ejército de los persas destacaban los inmortales, guerreros de la guardia personal del rey, que tenían una habilidad máxima para el combate y que también utilizan hachas.

4. Los guerreros griegos dominaban la espada, como los espartanos y persas, unos mejor que otros.

Tu aplicación debe solicitar únicamente al usuario el número de espartanos, persas, inmortales y griegos que desea que intervengan en la batalla. A partir de ahi debe generar ambos ejércitos teniendo en cuenta que:

1. La vida de todos los contendientes se mide por su nivel de energía de 0 a 10. Todos los contendientes comienzan con el nivel máximo, excepto los espartanos que comienzan con el doble.

2. Todos los contendientes tienen una habilidad general para el combate de 0 a 10 que el programa debe establecer aleatoriamente excepto en el caso de los inmortales, que tienen habilidad máxima (10).

3. Cada combatiente tiene una habilidad para dominar su arma valorada de 0 a 10 si son espadas o de 0 a 5 si son hachas. Esta habilidad se genera de forma aleatoria.

4. Los espartanos tienen una habilidad para manejar su escudo valorada de 0 a 10 y generada de forma aleatoria,

5. Cada combatiente tiene una habilidad para esquivar, valorada de 0 a 10, excepto los espartanos que tienen habilidad máxima (10).

6. Los griegos y los espartanos tienen una cualidad que no tienen el resto de combatientes: conocen el terreno donde se desarrolla la batalla. Esta cualidad se valora de 0 a 10 y su valor debe ser generado aleatoriamente.

El combate se simula de la siguiente manera. Se calcula la fuerza de ataque global del ejército agresor, teniendo en cuenta que solo atacan aquellos guerreros que aun estan vivos, sumando la fuerza individual de ataque de cada contendiente. 

Esta fuerza de ataque individual se calcula sumando la habilidad general para el combate del guerrero con su habilidad para usar su arma. Si el guerrero es un inmortal, hay que sumar 10 puntos extras. Si los guerreros tienen conocimiento del terreno, debe sumarse también esa cantidad.

Luego se calcula la fuerza de defensa global del ejército agredido, teniendo en cuenta que solo se defienden los vivos, sumando la fuerza individual de defensa de cada contendiente. 

Esta fuerza individual de defensa se calcula sumando su energia con su habilidad para esquivar, excepto en el caso de los espartanos, que hay que sumar adicionalmente su capacidad para manejar el escudo.

Primero ataca el ejército persa. Si su fuerza de ataque global es superior a la fuerza de defensa global de los griegos, esta diferencia se divide entre los vivos del ejército griego y se les resta a cada uno de ellos la parte proporcional más 1 (por ejemplo, si la diferencia es 5 y hay 6 vivos, se le restaria a cada uno 1 punto ya que 5/6 es 0 y más 1 es 1; si la diferencia fuera 12 entonces se les restaría 3). Si la fuerza de ataque global es inferior a la fuerza de defensa global de los griegos, no se hace nada. 

Luego atacan los griegos de la misma forma. Cumplidos ambos ataques, vuelven a atacar los persas. El combate termina cuando ya no quedan guerreros vivos en uno de los bandos.

Por cada ataque, ya sea de persas o de griegos, el programa debe informar de todos los calculos que hace, indicando el numero de vivos y muertos en cada bando tras cada ataque y las características de los vivos.

Un ejemplo de ejecución (habiendo indicado 2 guerreros griegos, 1 espartano, 4 guerreros persas y 2 inmortales) sería:


	********************************************
	          EJERCITOS QUE PARTICIPAN
	********************************************

	PERSAS (numero de guerreros: 6) 
	Vivos (6):
	Persa      - ENERGIA: 10 - HC: 1 - HE: 4 - HA: 2 - [FIA]: 3 - [FID]: 14
	Persa      - ENERGIA: 10 - HC: 10 - HE: 3 - HA: 1 - [FIA]: 11 - [FID]: 13
	Persa      - ENERGIA: 10 - HC: 4 - HE: 6 - HA: 2 - [FIA]: 6 - [FID]: 16
	Persa      - ENERGIA: 10 - HC: 0 - HE: 7 - HA: 2 - [FIA]: 2 - [FID]: 17
	Inmortal   - ENERGIA: 10 - HC: 10 - HE: 4 - HA: 0 - [FIA]: 20 - [FID]: 14
	Inmortal   - ENERGIA: 10 - HC: 10 - HE: 6 - HA: 2 - [FIA]: 22 - [FID]: 16
	Muertos (0)

	GRIEGOS (numero de guerreros: 3) 
	Vivos (3):
	Griego     - ENERGIA: 5 - HC: 7 - HE: 0 - HA: 7 - [FIA]: 16 - [FID]: 5 - CT: 2
	Griego     - ENERGIA: 5 - HC: 2 - HE: 1 - HA: 1 - [FIA]: 7 - [FID]: 6 - CT: 4
	Espartano  - ENERGIA: 15 - HC: 7 - HE: 10 - HA: 7 - [FIA]: 14 - [FID]: 25 - CT: 0 - HEsc: 0
	Muertos (0)


	********************************************
	                ROUND 1
	********************************************

	Atacan los PERSAS con 64 (los GRIEGOS se defienden con 51)
	El ataque aventaja a la defensa en 13
	Restados 5 a cada guerrero vivo de los GRIEGOS. FIN DEL ATAQUE

	PERSAS (numero de guerreros: 6) 
	Vivos (6):
	Persa      - ENERGIA: 10 - HC: 1 - HE: 4 - HA: 2 - [FIA]: 3 - [FID]: 14
	Persa      - ENERGIA: 10 - HC: 10 - HE: 3 - HA: 1 - [FIA]: 11 - [FID]: 13
	Persa      - ENERGIA: 10 - HC: 4 - HE: 6 - HA: 2 - [FIA]: 6 - [FID]: 16
	Persa      - ENERGIA: 10 - HC: 0 - HE: 7 - HA: 2 - [FIA]: 2 - [FID]: 17
	Inmortal   - ENERGIA: 10 - HC: 10 - HE: 4 - HA: 0 - [FIA]: 20 - [FID]: 14
	Inmortal   - ENERGIA: 10 - HC: 10 - HE: 6 - HA: 2 - [FIA]: 22 - [FID]: 16
	Muertos (0)

	GRIEGOS (numero de guerreros: 3) 
	Vivos (3):
	Griego     - ENERGIA: 5 - HC: 7 - HE: 0 - HA: 7 - [FIA]: 16 - [FID]: 5 - CT: 2
	Griego     - ENERGIA: 5 - HC: 2 - HE: 1 - HA: 1 - [FIA]: 7 - [FID]: 6 - CT: 4
	Espartano  - ENERGIA: 15 - HC: 7 - HE: 10 - HA: 7 - [FIA]: 14 - [FID]: 25 - CT: 0 - HEsc: 0
	Muertos (0)

	Atacan los GRIEGOS con 37 (los PERSAS se defienden con 90)
	El ataque no supera a la defensa. FIN DEL ATAQUE.

	PERSAS (numero de guerreros: 6) 
	Vivos (6):
	Persa      - ENERGIA: 10 - HC: 1 - HE: 4 - HA: 2 - [FIA]: 3 - [FID]: 14
	Persa      - ENERGIA: 10 - HC: 10 - HE: 3 - HA: 1 - [FIA]: 11 - [FID]: 13
	Persa      - ENERGIA: 10 - HC: 4 - HE: 6 - HA: 2 - [FIA]: 6 - [FID]: 16
	Persa      - ENERGIA: 10 - HC: 0 - HE: 7 - HA: 2 - [FIA]: 2 - [FID]: 17
	Inmortal   - ENERGIA: 10 - HC: 10 - HE: 4 - HA: 0 - [FIA]: 20 - [FID]: 14
	Inmortal   - ENERGIA: 10 - HC: 10 - HE: 6 - HA: 2 - [FIA]: 22 - [FID]: 16
	Muertos (0)

	GRIEGOS (numero de guerreros: 3) 
	Vivos (3):
	Griego     - ENERGIA: 5 - HC: 7 - HE: 0 - HA: 7 - [FIA]: 16 - [FID]: 5 - CT: 2
	Griego     - ENERGIA: 5 - HC: 2 - HE: 1 - HA: 1 - [FIA]: 7 - [FID]: 6 - CT: 4
	Espartano  - ENERGIA: 15 - HC: 7 - HE: 10 - HA: 7 - [FIA]: 14 - [FID]: 25 - CT: 0 - HEsc: 0
	Muertos (0)



	********************************************
	                ROUND 2
	********************************************

	Atacan los PERSAS con 64 (los GRIEGOS se defienden con 36)
	El ataque aventaja a la defensa en 28
	Restados 10 a cada guerrero vivo de los GRIEGOS. FIN DEL ATAQUE

	PERSAS (numero de guerreros: 6) 
	Vivos (6):
	Persa      - ENERGIA: 10 - HC: 1 - HE: 4 - HA: 2 - [FIA]: 3 - [FID]: 14
	Persa      - ENERGIA: 10 - HC: 10 - HE: 3 - HA: 1 - [FIA]: 11 - [FID]: 13
	Persa      - ENERGIA: 10 - HC: 4 - HE: 6 - HA: 2 - [FIA]: 6 - [FID]: 16
	Persa      - ENERGIA: 10 - HC: 0 - HE: 7 - HA: 2 - [FIA]: 2 - [FID]: 17
	Inmortal   - ENERGIA: 10 - HC: 10 - HE: 4 - HA: 0 - [FIA]: 20 - [FID]: 14
	Inmortal   - ENERGIA: 10 - HC: 10 - HE: 6 - HA: 2 - [FIA]: 22 - [FID]: 16
	Muertos (0)

	GRIEGOS (numero de guerreros: 3) 
	Vivos (1):
	Espartano  - ENERGIA: 5 - HC: 7 - HE: 10 - HA: 7 - [FIA]: 14 - [FID]: 15 - CT: 0 - HEsc: 0
	Muertos (2)

	Atacan los GRIEGOS con 14 (los PERSAS se defienden con 90)
	El ataque no supera a la defensa. FIN DEL ATAQUE.

	PERSAS (numero de guerreros: 6) 
	Vivos (6):
	Persa      - ENERGIA: 10 - HC: 1 - HE: 4 - HA: 2 - [FIA]: 3 - [FID]: 14
	Persa      - ENERGIA: 10 - HC: 10 - HE: 3 - HA: 1 - [FIA]: 11 - [FID]: 13
	Persa      - ENERGIA: 10 - HC: 4 - HE: 6 - HA: 2 - [FIA]: 6 - [FID]: 16
	Persa      - ENERGIA: 10 - HC: 0 - HE: 7 - HA: 2 - [FIA]: 2 - [FID]: 17
	Inmortal   - ENERGIA: 10 - HC: 10 - HE: 4 - HA: 0 - [FIA]: 20 - [FID]: 14
	Inmortal   - ENERGIA: 10 - HC: 10 - HE: 6 - HA: 2 - [FIA]: 22 - [FID]: 16
	Muertos (0)

	GRIEGOS (numero de guerreros: 3) 
	Vivos (1):
	Espartano  - ENERGIA: 5 - HC: 7 - HE: 10 - HA: 7 - [FIA]: 14 - [FID]: 15 - CT: 0 - HEsc: 0
	Muertos (2)



	********************************************
	                ROUND 3
	********************************************

	Atacan los PERSAS con 64 (los GRIEGOS se defienden con 15)
	El ataque aventaja a la defensa en 49
	Restados 50 a cada guerrero vivo de los GRIEGOS. FIN DEL ATAQUE

	PERSAS (numero de guerreros: 6) 
	Vivos (6):
	Persa      - ENERGIA: 10 - HC: 1 - HE: 4 - HA: 2 - [FIA]: 3 - [FID]: 14
	Persa      - ENERGIA: 10 - HC: 10 - HE: 3 - HA: 1 - [FIA]: 11 - [FID]: 13
	Persa      - ENERGIA: 10 - HC: 4 - HE: 6 - HA: 2 - [FIA]: 6 - [FID]: 16
	Persa      - ENERGIA: 10 - HC: 0 - HE: 7 - HA: 2 - [FIA]: 2 - [FID]: 17
	Inmortal   - ENERGIA: 10 - HC: 10 - HE: 4 - HA: 0 - [FIA]: 20 - [FID]: 14
	Inmortal   - ENERGIA: 10 - HC: 10 - HE: 6 - HA: 2 - [FIA]: 22 - [FID]: 16
	Muertos (0)

	GRIEGOS (numero de guerreros: 3) 
	Vivos (0):
	Muertos (3)



	++++++++++++++++ BATALLA TERMINADA ++++++++++++++++



### Observaciones:

* Es obligatorio para que se corrija el examen que:
    * El código compile sin errores sobre Java 7.   
    * Se utilice git de forma correcta para el control de versiones
* No se permite:
    * El uso de la sentencia `break` excepto en claúsulas `switch`.
    * Utilizar más de un `return` en los métodos.
* Es obligatorio:
	* Es obligatorio hacer asbtractas aquellas clases que deban serlo.
	* Es obligatorio que todos los atributos sean privados o protegidos.
	* Es obligatorio apoyarse en el método toString() para mostrar los datos de ejercitos y guerreros.
* Se valora negativamente:
	* No utilizar herencia.
	* No utilizar polimorfismo si es posible.
    * La redundancia de código. 
    * La incorrección del código.
    * La utilización de código ineficiente.
    * La indentación incorrecta.
    * La utilización de números literales dentro del código en vez de constantes.
    * La incorrección en el diseño.


## Importante

* No se permite el uso de ninguna forma de comunicación (verbal, escrita, por Internet) entre alumnos o con cualquier otra persona. 

* Tampoco se permite ningún mecanismo que permita transmitir el código fuente al resto de alumnos, incluido el simple acceso a repositorios de otros alumnos.

En caso de detectar alguna de estas prácticas, el alumno suspende directamente la convocatoria actual.


## Anexo I: Repositorios

Para enlazar tu repositorio local con el remoto de GitHub debes usar el comando:

    git remote add origin git@github.com:iessanandrespro013/XXX.git
    git remote set-url origin https://USERNAME@github.com/iessanandrespro013/XXX.git

donde `USERNAME` debes sustituirlo por el nombre de tu usuario y las `XXX` debes sustituirla por el siguiente número en función de quien seas.

Cuando desees realizar el primer push al repositorio remoto debes usar la instrucción:

    git push --force origin master