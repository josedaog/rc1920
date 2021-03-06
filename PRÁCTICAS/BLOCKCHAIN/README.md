# Creación de una BlockChain con Prolog
<p align="center">
  <img width="950" height="300" src="../../Imagenes/foto portada blockchain.jpg">
</p>

:office: Universidad de Huelva (UHU)  
:calendar: Curso 2019-2020  
:mortar_board: Representación del conocimiento  
:octocat: José David Ortiz Gómez 

## Introducción
En el presente documento se describen los pasos que habría que seguir para la implementación de una red **BlockChain** local de manera sencilla. Además, se aportarán referencias de utilidad para que el trabajo se pueda llevar a cabo. Este es un proyecto que solo está pensado pero **no realizado**.

El lenguaje de programación propuesto es **Prolog**. Este es un lenguaje **declarativo**, por lo que ayudará a que la implementación sea rápida y sencilla.

## Aspectos básicos
### ¿Qué es BlockChain?
Dando una respuesta rápida y breve, blockchain es como una base de datos **distribuida** y **descentralizada** en la que la información está protegida gracias a que cada **bloque** de información contiene un código hash que lo identifica como único. 

Este código hash, es dependiente a su vez del bloque anterior, por lo que modificar un bloque de información conllevaría **calcular el código hash de todos los bloques**, algo que requeriría de una gran potencia computacional. De ahí, que se utilice cuando la **seguridad** es prioridad. Es una tecnología usada por ejemplo en las **criptomonedas**.

### ¿Qué hace falta para hacer un ejemplo de BlockChain de forma sencilla?
Para llevar a cabo una implementación sencilla y aprender los fundamentos de esta tecnología, simplemente haría falta una **lista de datos** que se quieran meter en la blockchain, y un **algoritmo de encriptado** de información para generar el código hash de cada bloque.

### ¿Por qué este proyecto no ha sido implementado?
La idea y funcionamiento de una blockchain, como se ha explicado anteriormente, resulta fácil de entender. Es el algoritmo de encriptado de datos el que **dificulta** el proceso, ya que sólo se han encontrado implementaciones de claves públicas y privadas, encriptación simple de datos, etc. Este problema sin embargo, necesita crear un código hash único dependiendte de **bastantes otros campos**, para que así el bloque sea único, irrepetible y seguro. Con dicho algoritmo, la resolución resultaría bastante sencilla.

## ¡Manos a la obra!
### Estructura de los bloques
Para empezar, debemos que definir una **estructura** para los bloques de información. Aunque en la realidad se incluyen muchos campos, nos va a bastar con definir lo siguiente:

* **Identificador:** Para saber qué posición ocupa el bloque en la blockchain.
* **Fecha de inserción del bloque:** La fehca de inserción de la información del bloque es importante ya que cada bloque podrá tener una fecha distinta (o no), lo que le añade seguridad a la cadena de bloques.
* **Datos:** La información que queremos guardar a la blockchain. Puede ser por ejemplo, una contraseña que queremos guardar con seguridad, el pago de algún objeto o servicio, etc.
* **Hash:** Código hash del bloque en cuestión.
* **Hash del bloque anterior:** Con esto se garantiza que la cadena de bloques tiene consistencia y es segura. 


<p align="center">
  <img width="900" height="160" src="../../Imagenes/Estructura de los bloques.png">
</p>

En Prolog, se podría escribir de la siguiente forma:

>block(Index, TimeStamp, Dato, Hash, PrevHash).

El primer paso que habría que dar sería **preparar** la información de los datos para incluir todos los campos antes mencionados, exceptuando los códigos hash que son propios de los bloques.

### Generando un bloque
Para la generación de un bloque a partir de los datos, entra en juego la **función de encriptación**. En [esta página](https://www.metalevel.at/prolog/cryptography)[1] se exponen varias **técnicas** de encriptación de datos. Sin embargo, habría que adaptar alguna para que el hash generado fuera apartir de los datos que tenemos (identificador, fecha, y datos).

Si se le añade el **hash** del bloque **anterior**, ya tendríamos el bloque creado y preparado para **meterlo** en nuestra blockchain.

### Almacenar un bloque en la blockchain
Del mismo modo que se ha propuesto la utilización de listas para la almacenar la información de entrada, la cadena de bloques resultante podría tambien ser una **lista de bloques**, con la estructura antes mencionada. Por tanto a la vez que se crean los bloques, se podrían ir incluyendo en la lista final.

## ¿Cómo comprobar la integridad de los datos en la blockchain?
La seguridad y la integridad de los datos es fundamental en una blockchain. Pero, ¿qué habría que tener en cuenta para decidir si una blockchain **no tiene ningún fallo de seguridad**?

El proceso consiste en **recorrer la lista de bloques** generada anteriormente e ir verificando los códigos hash de cada par de bloques consecutivos: **el código hash de un bloque debe coincidir con el campo del "hash del bloque anterior" del siguiente bloque**. Si al explorar todos los pares de bloques se produce una discordancia, la blockchain no será íntegra y se habrá modificado algún bloque después de su incorporación a la blockchain.

## Recopilación de datos
Se añaden una serie de referencias de interés para llevar a cabo el proyecto:

Qué es blockchain: la explicación definitiva para la tecnología más de moda: https://www.xataka.com/especiales/que-es-blockchain-la-explicacion-definitiva-para-la-tecnologia-mas-de-moda

Code your own blockchain in less than 200 lines of Go!: https://medium.com/@mycoralhealth/code-your-own-blockchain-in-less-than-200-lines-of-go-e296282bcffc

A blockchain in 200 lines of code: https://medium.com/@lhartikk/a-blockchain-in-200-lines-of-code-963cc1cc0e54

Cryptography with Prolog[1]: https://www.metalevel.at/prolog/cryptography

Block chain/distributed ledger library? (Foro en el que se habla de un proyecto parecido a este): https://swi-prolog.discourse.group/t/block-chain-distributed-ledger-library/481

Libreria de criptografía Prolog: https://github.com/mthom/scryer-prolog/blob/master/src/lib/crypto.pl
