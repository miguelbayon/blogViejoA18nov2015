---
layout: page
title:  "Examen 3ª Evaluación Curso 2013-2014"
---

<style>
h3 {
	margin-top: 25px;
}
</style>


## Mundial de Fútbol  Brasil 2014

<div class="row">

    <div class="col-md-7" markdown="1">

32 equipos jugarán el Mundial de Fútbol de Brasil 2014. 

Inicialmente, estos 32 equipos entran en un sorteo para dividirlos en 8 grupos de 4 equipos.

Una vez distribuidos por grupos comienza la primera fase del mundial, en la que en cada grupo se disputa una liguilla a una sola vuelta. Es decir, cada equipo de un grupo juega un partido contra los otros 3 equipos de ese grupo.

Cuando un equipo gana un partido se le conceden 3 puntos; si empata, 1 punto. 

Al finalizar la primera fase, los dos mejores equipos de cada grupo se clasifican para la siguiente fase, la fase de eliminatorias. 

El objetivo del examen es realizar __un programa que nos permita simular el sorteo y la primera fase__ del Mundial de Fútbol de Brasil 2014.

</div>
<div class="col-md-4 col-md-offset-1">
    <img src="/images/mundial.jpg" class="img-responsive">
</div>
</div>


## Consideraciones

1. Cada equipo cuenta con una valoración de 0 a 100 (ambos incluidos), que el programa calcula de forma aleatoria.

2. Cuando un equipo juega un partido se suma a su valoración un valor entre 0 y 50 (ambos incluidos) que se obtiene de forma aleatoria y que representa la suerte que tendrá ese equipo en ese partido.

3. Por cada 40 puntos de la valoración final el equipo consigue un gol en el partido. Por ejemplo, si un equipo tiene una valoración de 20 y su suerte para el partido vale 12 no marcará ningún gol en ese partido ya que no llega a 40 puntos. En cambio, si la valoración del equipo fuera de 70 y su suerte en ese partido de 12, el equipo marcaría 2 goles.



## Pasos a completar

1. Crea un repositorio local de git en tu equipo.

2. Asocia dicho repositorio con el repositorio remoto adecuado conforme las instrucciones del anexo II.

3. <span class="label label-info">20 puntos</span> Codifica el código necesario, conforme a la documentacón de las clases del anexo I, para que se pueda crear un objeto de tipo `Mundial` desde la interfaz de BlueJ. 

    Haz un commit en la rama master y realiza un push.

4. <span class="label label-info">20 puntos</span> Codifica el código necesario, conforme a la documentacón de las clases del anexo I, para que se distribuyan los equipos en grupos (método `generaGrupos()`) y se pueda ver por pantalla dicha distribución (método `mostrarGrupos()`). 

    Puedes ver [aquí](/images/grupos.png) un ejemlo de cómo debe ser la salida por pantalla. 

    Haz un commit en la rama master y realiza un push.

5. <span class="label label-info">20 puntos</span> Codifica el código necesario, conforme a la documentacón de las clases del anexo I, para que se generen los partidos que los equipos deben disputar dentro de cada grupo (método`generaPartidosPrimeraFase()`) y se pueda ver por pantalla el listado de los mismos por grupo (método `mostrarPartidosPrimeraFase()`). 

    Puedes ver [aquí](/images/partidos.png) un ejemlo de cómo debe ser la salida por pantalla. 

    Haz un commit en la rama master y realiza un push.

6. <span class="label label-info">40 puntos</span> Codifica el código necesario, conforme a la documentacón de las clases del anexo I, para que se generen los resultados de cada partido de cada grupo y las clasificaciones de cada grupo (método `generaResultadosPrimeraFase()`) y se pueda ver por pantalla el resultado de los partidos de cada grupo y a clasificacion final de los equipos ordenada por puntos (método `mostrarResultadosYClasificacionesPrimeraFase()`).  

    Puedes ver [aquí](/images/resultadosYClasificacion.png) un ejemlo de cómo debe ser la salida por pantalla. 

    Haz un commit en la rama master y realiza un push.




### Observaciones:

* Es obligatorio para que se corrija el examen que:
	* El código compile sin errores sobre Java 7.	
	* Se utilice git de forma correcta para el control de versiones
* No se permite:
	* El uso de la sentencia `break` excepto en claúsulas `switch`.
	* Utilizar más de un `return` en los métodos.
* Se valora negativamente:
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


## Anexo I: Clases

A continuación se incluyen enlaces a la documentación de las 4 clases que deben crearse:

1. Clase `Mundial`: [ver documentación](/paginas/pro013/examen20140606/Mundial.html)

2. Clase `Equipo`: [ver documentacion](/paginas/pro013/examen20140606/Equipo.html)

3. Clase `Grupo`: [ver documentacion](/paginas/pro013/examen20140606/Grupo.html)

4. Clase `Partido`: [ver documentacion](/paginas/pro013/examen20140606/Partido.html)


A continuación se incluye el código completo de la quinta y última clase del programa, la clase `NombresEquipos`:

{% highlight java %}

/**
 * Esta clase contiene los nombres de los 32 equipos clasificados para
 * el Mundial de Fúbtol de Brasil 2014
 * 
 */
public class NombreEquipos
{
    private static String[] nombresEquipos= {
        "Brasil         ", "España         ", 
        "Alemania       ", "Argentina      ", 
        "Colombia       ", "Bélgica        ", 
        "Uruguay        ", "Suiza          ", 
        "Holanda        ", "Italia         ", 
        "Inglaterra     ", "Portugal       ", 
        "Grecia         ", "Bosnia         ", 
        "Croacia        ", "Rusia          ",
        "Chile          ", "Costa de Marfil", 
        "Francia        ", "Ecuador        ", 
        "Ghana          ", "Argelia        ", 
        "Nigeria        ", "Camerún        ",
        "EEUU           ", "México         ", 
        "Costa Rica     ", "Honduras       ", 
        "Japón          ", "Irán           ", 
        "Corea del Sur  ", "Australia      "
    };
    
    
    /*
     * Devuelve el nombre de equipo que ocupa la posición index
     * en el array nombresEquipos
     *
     * @param index el indice que ocupa el equipo dentro del array
     * @return un nombre de equipo
     */
    public static String getNombreEquipo(int index) 
    {
        return nombresEquipos[index];
    }
}


{% endhighlight %}


## Anexo 2: Repositorios

Para enlazar tu repositorio local con el remoto de GitHub debes usar el comando:

    git remote add origin git@github.com:iessanandrespro013/XXX.git
    git remote set-url origin https://USERNAME@github.com/iessanandrespro013/XXX.git

donde `USERNAME` debes sustituirlo por el nombre de tu usuario y las `XXX` debes sustituirla por el siguiente número en función de quien seas:

* `002` juanma
* `003` diego
* `004` juanvi
* `005` sara
* `006` alejandroaller
* `007` angel
* `008` sergiodiaz
* `010` laura
* `011` alberto
* `012` arturo
* `013` alejandrogrande
* `014` sergioalvarez
* `016` cristian
* `017` marco
* `018` francisco
* `019` roberto



