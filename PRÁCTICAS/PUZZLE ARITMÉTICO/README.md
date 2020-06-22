# Puzle Aritmético usando Prolog
:office: Universidad de Huelva (UHU)  
:calendar: Curso 2019-2020  
:mortar_board: Representación del conocimiento  
:octocat: José David Ortiz Gómez 

## Introducción
En este documento se detallará la implementación de un puzle aritmético que se explicará a continuación. Es parte de la serie de problemas de la página [P-99: Ninety-Nine Prolog Problems](https://www.ic.unicamp.br/~meidanis/courses/mc336/2009s2/prolog/problemas/)[1]. Más concretamente, se trata del problema 93.

## Planteamiento del problema
El puzle aritmético consiste en encontrar la forma correcta de insertar signos aritméticos para que una lista de números puedan formar una ecuación matemática válida.

Por ejemplo, para la lista de números **[5,4,3,7]**, podemos hacer una sola ecuación válida: **5 = 4*3-7**.

Para la lista **[5,4,3,5]**, podemos formar tres ecuaciones: 

**5 = (4-3)*5;  
5*(4-3) = 5;   
5/(4-3) = 5**

## Metodología usada
* Se divide la lista de números en todas sus combinaciones posibles.
* Se calculan todas las posibles combinaciones de términos de la parte izquierda de la ecuación final.
* Se calculan ahora las de la parte derecha.
* Para cada combinación de términos de la parte izquierda y derecha, se evalúa si se cumple que son iguales.

## Descripción del código
A continuación se describirá el código desde la llamada inicial, pasando por todos los predicados que se utilizan internamente.

### do(+L).
*Es cierto cuando por pantalla se imprimen todas las posibles soluciones al problema planteado, dada una lista L de números.*

```
do(L) :- 
  equation(L,LT,RT),
     writef('%w = %w\n',[LT,RT]),
  fail.
do(_).
```

Es la llamada inicial al problema. En ella, se detalla una lista de números. Hace uso del predicado *equation(+L, -LT, -RT).*, y de la escritura por pantalla para mostrar todos los resultados.

### equation(+L, -LT, -RT).
*Es cierto cuando LT y RT pueden formar una ecuación válida para los números de la lista L.*

```
equation(L,LT,RT) :-
   split(L,LL,RL),           
   term(LL,LT),                
   term(RL,RT),                 
   LT =:= RT. 
  ``` 
  
Este predicado se usa para comprobar todas las combinaciones de LT y RT posibles que forman una ecuación válida. LT se refiere a la parte izquierda de la ecuación (left term), y RT a la parte derecha (right term). 

Hace uso del predicado *split(-L,+L1,+L2)* y *term(+L,T-)*. Finalmente evalúa si los términos LT y RT unifican.

### split(-L, +L1, +L2).
*Es cierto cuando L1 y L2 forman una lista L.*

```
split(L,L1,L2) :- append(L1,L2,L), L1 = [_|_], L2 = [_|_].
```

Se utiliza para dividir la lista L en otras dos listas L1 y L2 que concatenadas forman la lista L. Así, se podrán conocer todas las combinaciones de números de la lista L que pueden formar parte de una ecuación.

Se hace uso del predicado interno de Prolog *append(L, L1, L2).*. Este predicado concatena dos listas L1 y L2 en una lista L, pero gracias a Prolog se puede usar de manera reversible, de modo que dada una lista L, devuelve las listas L1 y L2 que pueden formar la lista L cuando se concatenan.

### term(+L,-T).
*Es cierto si T es un término formado a partir de la lista L.*

```
term([X],X). //Caso base. Un número es término de sí mismo.
term(L,T) :-                   
   split(L,LL,RL),              
   term(LL,LT),                
   term(RL,RT),                
   binterm(LT,RT,T). 
```

Se utiliza para obtener la lista de términos posibles dada la lista L. Se obtendrán todas las listas con los distintos operadores aritméticos posibles para una ecuación.

Este predicado vuelve a hacer uso de *split(-L,+L1,+L2).* y *term(+L,T-).* , además de un nuevo predicado llamado *binterm (+LT, +RT, -T).* .

### binterm (+LT, +RT, -T).
*Es cierto cuando T es un término combinado binario construido desde LT y desde RT*.

```
binterm(LT,RT,LT+RT).
binterm(LT,RT,LT-RT).
binterm(LT,RT,LT*RT).
binterm(LT,RT,LT/RT) :- RT =\= 0.
```

Se usa para construir los términos que se dan en el predicado *term(+L,T-).* "poco a poco", ya que coge los valores por pares para devolver todas las listas de esos dos números con los distintos operadores aritméticos.

## Cómo usar el programa
Para utilizar este programa, debemos hacer la llamada al predicado *do(+L).*

Se le pasará la lista de números con los que se quiere formar las ecuaciones.

#### do([1,2,3,4]).

<p align="center">
  <img width="675" height="364" src="../../Imagenes/predicado 1234.PNG">
</p>

#### do([7,10,2,5,4]).
<p align="center">
  <img width="675" height="364" src="../../Imagenes/predicado 7,10,2,5,4.PNG">
</p>
