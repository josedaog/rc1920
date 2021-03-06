# Técnicas de Representación del Conocimiento en Inteligencia Artificial
:office: Universidad de Huelva (UHU)  
:calendar: Curso 2019-2020  
:mortar_board: Representación del conocimiento  
:octocat: José David Ortiz Gómez 
## Introducción
Los humanos tenemos la capacidad de **organizar ideas** y relacionarlas con otras, para así sacar conclusiones y tomar decisiones. Las máquinas sin embargo, lo tienen más complicado. La representación del conocimiento es el ámbito de la informática encargado de solucionar este problema en los ordenadores, de modo que sean capaces de **tratar** la información de forma adecuada.

*Representar el conocimiento en Inteligencia Artificial es el proceso de transformación de éste a un dominio o un lenguaje simbólico para ser procesado en un computador.* [1].

En este documento, se dará una breve explicación de las técnicas de representación del conocimiento más utilizadas.

## Representación lógica
Este tipo de representación consiste en imponer una serie de reglas inamovibles y sin ningún tipo de **ambigüedad**. Su funcionamiento se basa en definir una serie de condiciones o premisas que derivan en conclusiones con validez plena. Esto se conoce como **regla de inferencia**.

Es como decir que, "Dos más dos son cuatro":  "Dos más dos" sería una premisa, y "Son cuatro" sería la conclusión que se saca. Se dice que la premisa **implica** la conclusión.

Realmente se puede intuir que la lógica es la base de cualquier lenguaje de programación. Formalmente, la lógica utiliza símbolos especiales para escribir las premisas.

<p align="center">
  <img width="640" height="360" src="../Imagenes/Ejemplo lógica 2.png">
</p>

En el ejemplo 1 es lícito concluir que Sócrates es mortal **a partir** de las dos primeras **premisas**. En el ejemplo 2, por el contrario, **no es lícito** llegar a esta conclusión. ¿Por qué? Porque, si bien todos los hombres son mortales y Sócrates es mortal, esto no excluye necesariamente la posibilidad de que Sócrates no sea un hombre. [3]

**Conclusiones**

La lógica aunque es muy potetente, tiende a ser difícil de trabajar debido a sus restricciones, pero es la base de todo lenguaje de programación por lo que está muy presente en la informática de una forma u otra.

## Redes Semánticas
Una red semántica es una forma de representación del conocimiento en la que los conceptos y sus interrelaciones se representan mediante un grafo. En caso de que no existan ciclos, estas redes pueden ser visualizadas como árboles.

Los elementos semánticos se representan mediante nodos, mientras que una relación entre dos elementos semánticos se representa mediante una arista. Así, se obtiene finalmente un grafo conectado en el que se pueden observar diversas relaciones.

Ejemplo [4]:
<p align="center">
  <img width="571" height="342" src="../Imagenes/Ejemplo redes semánticas.png">
</p>

**Conclusiones**

Las redes semánticas destacan por su simplicidad a la hora de plasmar conocimiento humano, es bastante intuitivo. Sin embargo, al estar formada por un grafo, el coste computacional puede elevarse bastante. Además, no son "inteligentes" ya que es el propio usuario el que define su estructura.

## Marcos
Un marco o frame, es una colección de atributos con valores y restricciones asociados, que describe alguna entidad. Un frame tomado independientemente no suele ser útil, por lo que se suelen confeccionar colecciones de ellos.

Los marcos presentan bastante precisión a la hora de definir entidades. Además, es una metodología bastante modular y ordenada.

Ejemplo [6]:
<p align="center">
  <img width="571" height="342" src="../Imagenes/Ejemplo frames.jpg">
</p>


**Conclusiones**

Los frames son una gran opción ya que la información está muy bien recogida, y la posibilidad de adición de elementos es sumamente sencilla. Por contra, el mantenimiento de estas colecciones de frames, si son grandes, pueden causar problemas.

## Reglas de producción
Las reglas de producción son del tipo Si-Entonces. Es una estructura básica que conoce mucha gente y muy utilizada en otros ámbitos de la informática.

Su estructura se compone de un antecedente y un consecuente. **El antecedente** contiene las **cláusulas** que se deben cumplir para que la regla pueda evaluarse o ejecutarse. El **consecuente** indica las **conclusiones** que se deducen de las premisas o las acciones que el sistema debe realizar cuando ejecuta la regla.

Ejemplo [7]:
<p align="center">
  <img width="571" height="342" src="../Imagenes/Ejemplo regla producción.png">
</p>


**Conclusiones**
Las reglas de producción posiblemente constituyen la técnica más utilizada para la representación del conocimiento. Es modular, uniforma y su forma de expresar el conocimiento es bastante natural.

Se pueden dar algunos problemas sin embargo, como es la modificación de reglas existentes, que puede ser complicado. Además, no es difícil incorporar conocimiento contradictorio en un sistema medianamente grande. También puede ser dificil establecer relaciones entre entidades.

## Redes bayesianas
Una red bayesiana es un modelo grafo probabilístico que representa un conjunto de variables aleatorias y sus dependencias condicionales a través de un grafo acíclico dirigido. Por ejemplo, una red bayesiana puede representar las relaciones probabilísticas entre enfermedades y síntomas.

El grafo describe la distribución de probabilidad conjunta que gobierna un conjunto de variables aleatorias. Los nodos pueden representar cualquier tipo de variable, ya sea un parámetro medible (o medido), una variable latente o una hipótesis. Existen algoritmos que realizan inferencias y aprendizaje basados en redes bayesianas.

<p align="center">
  <img width="571" height="342" src="../Imagenes/Red bayesiana.png">
</p>

**Conclusiones**
Las redes bayesianas son potentes ya que pueden modelar sistemas complejos probabilísticos. El problema muchas veces es que hay que conocer *a priori* las probabilidades de los sucesos para generar un sistema fiable y funcional. Las redes bayesianas nos ayudan a *predecir* acontecimientos futuros a partir de los datos estadísticos de los que se forma.
## Bibliografía
[1].- REPRESENTACIÓN DEL CONOCIMIENTO
https://sitiointeligenciaa.wordpress.com/representacion-del-conocimiento/#:~:text=Representar

[2].- What is Knowledge Representation in AI? Techniques You Need To Know
https://www.edureka.co/blog/knowledge-representation-in-ai/

[3].- 
https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.enterarse.com%2F20191216_0001-que-son-las-falacias-y-como-saber-si-tu-argumento-es-un-buen-argumento&psig=AOvVaw2FuYAlU_5shDIfbDpFvlwf&ust=1592680241975000&source=images&cd=vfe&ved=0CAIQjRxqFwoTCKD79bPKjuoCFQAAAAAdAAAAABAl

[4].- http://informatedeiae.blogspot.com/2013/11/ejemplos-de-redes-semanticas.html

[5].-https://es.wikipedia.org/wiki/Red_semántica#

[6].- https://es.slideshare.net/leonardobernalzamora/frames-5316032

[7].- https://prezi.com/iqft5vv71w45/reglas-de-produccion/

Redes bayesianas: https://www.ecured.cu/Red_Bayesiana
