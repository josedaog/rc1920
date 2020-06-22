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
