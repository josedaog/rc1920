# Creación de una BlockChain con Prolog
## Introducción
En el presente documento se describen los pasos que habría que seguir para la implementación de una red **BlockChain** local de manera sencilla. Además, se aportarán referencias de utilidad para que el trabajo se pueda llevar a cabo. Este es un proyecto que solo está pensado pero **no realizado**.

El lenguaje de programación a utilizar será **Prolog**. Este es un lenguaje declarativo, por lo que ayudará a que la implementación sea rápida y sencilla.

## Aspectos básicos
### ¿Qué es BlockChain?
Dando una respuesta rápida y breve, blockchain es como una base de datos **distribuida** y **descentralizada** en la que la información está protegida gracias a que cada **bloque** de información contiene un código hash que lo identifica como único. 

Este código hash, es dependiente a su vez del bloque anterior, por lo que modificar un bloque de información conllevaría **calcular el código hash de todos los bloques**, algo que requeriría de una gran potencia computacional. De ahí, que se utilice cuando la **seguridad** es prioridad. Es una tecnología usada por ejemplo en las **criptomonedas**.

### ¿Qué hace falta para hacer un ejemplo de BlockChain de forma sencilla?
Para llevar a cabo una implementación sencilla y aprender los fundamentos de esta tecnología, simplemente haría falta una **lista de datos** que se quieran meter en la blockchain, y un **algoritmo de encriptado** de información para generar el código hash de cada bloque.

### ¿Por qué este proyecto no ha sido implementado?
La idea y funcionamiento de una blockchain, como se ha explicado anteriormente, resulta fácil de entender. Es el algoritmo de encriptado de datos el que **dificulta** el proceso, ya que sólo se han encontrado implementaciones de claves públicas y privadas, encriptación simple de datos, etc. Este problema sin embargo, necesita crear un código hash único dependiendte de **bastantes otros campos**, para que así el bloque sea único, irrepetible y seguro. Con dicho algoritmo, la resolución resultaría bastante sencilla.

## ¡Manos a la obra!
Para empezar, debemos que definir una **estructura** para los bloques de información. Aunque en la realidad se incluyen muchos campos, nos va a bastar con definir lo siguiente:

* **Identificador:** Para saber qué posición ocupa el bloque en la blockchain.
* **Fecha de edición del bloque*:** La fehca de edición de la información del bloque es importante ya que cada bloque podrá tener una fecha distinta (o no), lo que le añade seguridad a la cadena de bloques.
* **Datos:** La información que queremos guardar a la blockchain. Puede ser por ejemplo, una contraseña que queremos guardar con seguridad, el pago de algún objeto o servicio, etc.
* **Hash:** Código hash del bloque en cuestión.
* **Hash del bloque anterior:** Con esto se garantiza que la cadena de bloques tiene consistencia y es segura. 



## Como comprobar la integridad de los datos
Si los hash coinciden...
