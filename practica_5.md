Orientaci�n a Objetos 1 - 2014 - Pr�ctica 5

Ejercicio 1

Sea una red social en donde los usuarios tienen un muro en el cual pueden agregar mensajes para luego
ser le�dos por todos. La red tambi�n incluye relaciones de amistad entre los usuarios, lo que permite
que los usuarios sean avisados cuando un amigo hizo una publicaci�n en su muro.
Implemente la red social con la particularidad de que el muro de cada usuario solo permite 10 mensajes
como m�ximo (cuando llega el mensaje n�mero 11 se descarta el mensaje m�s viejo).

Wall>>post:aMessage
"Agrega un mensaje al muro"

Wall>>list
"Retorna una colecci�n con todos lo mensajes del muro"

Wall>>remove: aMessage
"Elimina el mensaje del muro"

Wall>>numberOfMessages
"Retorna la cantidad de mensajes posteados en el muro"

Los usuarios tienen un nombre, el muro y su lista de amigos.Cuando un usuario
publica (con el mensaje #post:) algo en su muro, sus amigos deben ser
notificados. Considere que la clase que implementa al usuario debe contener
el siguiente protocolo:

User>>name
"Retorna el nombre del usuario"

User>>name: aString
"Cambia el nombre del usuario por el valor recibido"

User>>addFriend: anotherUser
"Agregar anotherUser a la lista de amigos"

User>>post:aMessage
"Publica un mensaje en muro"
User>>newMessage:aMessage from:anotherUser
"Los usuarios reciben este mensaje cuando el amigo indicado por el par�metro
anotherUser public� el mensaje aMessage en su propio muro"

Tareas

1. Realice un diagrama de Clases.
2. Realice un diagrama de secuencia para mostrar c�mo un usuario que tiene dos amigos agrega algo a
su muro (y se agrega a los muros de los amigos).
3. Implemente en Pharo.

3.1 Incluya c�digo de prueba en un workspace.
3.2 Con la asistencia de un ayudante, implemente un test case en base al c�digo del punto
anterior.

Ejercicio 2

En la red social del ejercicio anterior se desea implementar la funcionalidad que responde a la premisa:
"Los amigos de mis amigos tambi�n son mis amigos". Implemente el m�todo #floodPost: el cual es
similar a #post, pero le llega "a los amigos de mis amigos''.

Ejemplo:
Si Juan es amigo de Pedro, Pedro es amigo de Carlos y sin importar si Juan y Carlos son amigos,
   cuando Juan hace un floodPost:, Carlos debe enterarse.

   Tareas

   1. Realice un diagrama de secuencia para el ejemplo.
   2. Implemente en Pharo.

   Ejercicio 3

   Dise�e e implemente un cliente de correo electr�nico de acuerdo con la siguiente especificaci�n:

   Un email tiene como atributos principales la direcci�n de correo del remitente, la del destinatario, un
   asunto, un cuerpo y una fecha. El sistema debe almacenar todos los emails que recibe en la bandeja de
   entrada. Adem�s, la aplicaci�n permite eliminar un mensaje de la bandeja de entrada, y en ese caso,
   pasa a otra bandeja de la que dispone el cliente de correo que es la bandeja de eliminados. De la
   bandeja de eliminados, tambi�n se pueden borrar los mails, pero al eliminarlos de all� se borran
   definitivamente del cliente de correo.

   La aplicaci�n debe permitir:

   marcar un email como "le�do"
   recuperar (en una colecci�n) todos los emails no le�dos de una bandeja.
   determinar el espacio ocupado por una bandeja de entrada (para esto considere que el tama�o

       de un email se calcula como el tama�o de su cuerpo, siendo el cuerpo un String).
   retornar (en una colecci�n) el campo asunto de los emails de cualquier bandeja.
   retornar los mails de una bandeja ordenados cronol�gicamente
   retornar los mails de una bandeja ordenados por tama�o.
   eliminar mails de las bandejas respetando el comportamiento explicado anteriormente.
   Tareas:

   1. Realice el diagrama de clases.
   2. Implemente en Pharo.

   Ejercicio 4

   Sea una empresa telef�nica que brinda servicios de comunicaci�n a sus abonados. Las comunicaciones
   pueden ser locales, interurbanas e internacionales. De cada comunicaci�n se conoce el momento de su
   comienzo, la distancia entre los destinos (que llama y que recibe) y la duraci�n. Cada una de las
   llamadas se factura de una forma distinta. Las locales tienen un costo fijo por minuto. Las interurbanas
   tienen un valor que depende de la ciudad destino y en funci�n de la distancia (hay 3 rangos
       discriminados) es el costo de la misma. Y por �ltimo, para las llamadas internacionales el costo depende
   de la hora en la que comience la misma. Si comienza entre las 08:00 y las 20:00 tienen un costo,
   mientras que de noche tienen un costo menor.
   Por otro lado, los abonados se clasifican en dos categor�as. Est�n los particulares a los que se les
   factura el precio neto y las entidades gubernamentales que reciben un 10% de descuento.

   Tareas:

   1. Realice el diagrama de clases.
   2. Implemente el mensaje para calcular el monto que cada abonado debe pagar.
   3. Implemente el mensaje para calcular la llamada de mayor duraci�n entre todas las llamadas de entre
   todos los abonados, para las llamadas realizadas dentro de los �ltimos 30 d�as.
   4. Implemente el mensaje para calcular el abonado con mayor tiempo total de comunicaci�n para las
   llamadas realizadas dentro de los �ltimos 30 d�as.

   Ejercicio 5

   Continuando con la implementaci�n del ejercicio de la computadora que comenz� en el Trabajo Pr�ctico
   previo, usted debe extender el modelo con los siguientes mensajes en el protocolo de la clase
   Computadora:

#memoria:unString
   "Almacena unString como contenido de la memoria"

#archivar
   "Pasa el contenido de la memoria al disco r�gido"

#contenidoMemoria
   "Imprime en Transcript el contenido de la memoria"

#contenidoDisco
   "Imprime en Transcript el contenido del disco r�gido"

   Adem�s de la clase Computadora modifique todo lo necesario para completar la funcionalidad indicada.
   Utilice los mensajes que defini� sin implementar para completar el almacenamiento en memoria y disco
   r�gido.
   Tareas:

   1. Actualice el diagrama de clases con el dise�o completo.
   2. Realice un diagrama de secuencia para mostrar la interacci�n entre objetos que tiene lugar cuando la
   computadora recibe #memoria:"Esto va a la memoria" .
   3. Implemente todas las modificaciones.

   3.1 Incluya c�digo de prueba en un workspace.
   3.2 Con la asistencia de un ayudante, implemente un test case en base al c�digo del punto
   anterior.

   Ejercicio 6

   Imagine una red de alumbrado donde cada farola est� conectada a una o varias vecinas formando un
   grafo conexo. Cada una de las farolas tiene un interruptor. Es suficiente con encender o apagar una
   farola para que se enciendan o apaguen todas las dem�s. Sin embargo, si se intenta apagar una farola
   apagada (o si se intenta encender una farola encendida) no habr� ning�n efecto, ya que no se propagar�
   esta acci�n hacia las vecinas.

   Tareas:

   1. Realice el diagrama de clases.

   2. Realice el diagrama de secuencia para el escenario en donde se enciende una farola con dos vecinas
   que estan apagadas y se conocen mutuamente.

   3. Implemente en Pharo los siguientes m�todos para las farolas:

#initialize
   "Inicializa a la farola como apagada"

#pairWithNeighbor: otraFarola
   "Crea la relaci�n de vecinos entre las farolas. Tenga presente que la relaci�n de
   vecinos entre las farolas es rec�proca, es decir el receptor del mensaje ser� vecino
   de otraFarola, al igual que otraFarola tambi�n se convertir� en vecina del receptor
   del mensaje "

#turnOn
   "Si la farola no esta encendida, la enciende y propaga la accion"

#turnOff
   "Si la farola no esta apagada, la apaga y propaga la accion"

#isOn
   "Retorna true si la farola esta encendida"

   4. Implemente el m�todo de instancia #createLightPost en la clase TestLightGrid. Este m�todo debe
   retornar una instancia de la farola, la cual debe estar inicializada apropiadamente.

   5. Utilice los test provistos por la c�tedra para probar las implementaciones de 3.
   6. Implemente el mensaje #activarEncendidoDeEmergencia. Este mensaje puede ser enviado a
   cualquier farola de la red de alumbrado y debe propagarse a toda la red sin importar si las farolas est�n
   encendidas o apagadas. Todas las farolas deben recibir el mensaje.

   7. Cree un nuevo tipo de farola, la cual al agregarle una vecina se asegura que el estado de la nueva
   vecina coincida con el propio.

   8. Implemente el m�todo de instancia #createLightPost en la clase TestLightAcuteGrid. Este m�todo
   retorna una instancia de la nueva farola definida en 6, la cual debe estar inicializada apropiadamente.

   9. Indique por qu� el test #testMixed es diferente. Discuta este punto con un ayudante.

   Ejercicio 7

   Sean los sem�foros de tr�nsito de una ciudad que quiere proveer de "onda verde" a los conductores.
   Para ello, cuando un sem�foro recibe la orden de cambiar a verde, espera 20 segundos y le propaga el
   pedido al siguiente.

   Tareas

   1. Realice el diagrama de clases.

   2. Implemente en Pharo la clase TrafficLight con los siguientes m�todos:

#initialize
   "Inicializa el sem�foro en luz roja"

#pairWithNeighbor: otroSemaforo
   "Crea la relaci�n de vecinos entre los semaforos. Tenga presente que a diferencia de las farolas, con los
   sem�foros hay un orden entre ellos."

#green
   "El sem�foro cambia a verde, espera 20 segundos y le propaga el pedido al siguiente."

   Para implementar el retardo puede utilizar una instancia de la clase Delay, por ejemplo:

   "Codigo para esperar 3 segundos"
   |d|
   d:= Delay forSeconds: 3.
   d wait.

   3. Cree un test para verificar que el m�todo #green propaga correctamente la onda verde (no se
       preocupe por testear el retardo).
   Ejercicio 8

   Un SpoolerFIFO es un administrador de impresi�n que maneja una lista de documentos que deben ser
   impresos respetando el orden en que fueron enviados a imprimir. El protocolo de SpoolerFIFO incluye
   los siguientes mensajes:

#spool: aDocument
   "El spooler agrega aDocument en su cola de impresi�n"

#nextDocument
   "Retorna el siguiente documento a imprimir (FIFO) o nil si no hay ninguno"

   De los documentos se conoce: el nombre del mismo, su contenido y los datos del usuario que lo cre�.

   Tareas

   1. Realice el diagrama de clases.

   2. Implemente en Pharo el SpoolerFIFO.

   3. �C�mo logr� que los documentos sean impresos en el orden en que fueron recibidos?

   4. Implemente en Pharo un SpoolerLIFO (last in first out) que permite imprimir los documentos en el
   orden inverso al que fueron enviados a imprimir.

   5. Extender el Spooler con un PrioritySpooler que entiende el mensaje: #spool: aDocument withPriority:
   aPriority, el cual ordena los documentos por prioridad. En este caso hay que tener en cuenta que la
   informaci�n de prioridad es ajena al documento y solamente se utiliza para el spooler de impresi�n.

   6. Implemente en el spooler los siguientes reportes:

#sortedDocumentsFromUser: aUsername
   "Retorna, ordenados por nombre los documentos del usuario"

#documentsFromUser: aUsername sortedBy: aBlock
   "Retorna los documentos del usuario, ordenados por el criterio recibido como
   par�metro"

#documentsGreaterThan: aSize
   "Retorna una lista con los documentos de tama�o mayor al recibido,
   manteniendo el orden de impresi�n. "

   Ejercicio 9

   En una librer�a existen dos tipos de libros: libros de texto y de literatura. De ellos se conoce su t�tulo,
   autor, precio y cantidad de p�ginas. En la librer�a se organiz� una promoci�n por el comienzo de clases
   en la cual la facturaci�n var�a de acuerdo al tipo y n�mero de libros comprados. Usted debe implementar
   un facturador para ventas con promociones el cual genera las facturas que poseen los libros que
   integran la compra, el bruto y el neto facturados.
   Las promociones se aplican de la siguiente manera:
   Los libros de texto tienen un 20 % de descuento.
   Los libros de literatura tienen un 15 % de descuento.
   Por la compra de 5 o m�s libros se realiza un 2 % extra de descuento.
   Adicionalmente a todos aquellos clientes que alguna vez compraron algo en la librer�a se les realiza un 5
   % extra de descuento (se calcula sobre el neto resultante de aplicar los descuentos anteriores).

   Su soluci�n debe respetar las siguientes indicaciones:
   La clase Facturador debe entender el mensaje #facturar: unosLibros para: unCliente, que genera la
   factura correspondiente.
   Una vez determinado el monto a pagar, el mismo debe informarse en el Transcript usando mensaje
#show:.
   La clase Facturador debe entender el mensaje #totalDescontado que retorna el monto total descontado
   por las promociones.

   Tareas

   1. Realice el diagrama de clases.

   2. Realice un diagrama de secuencia UML donde se muestre c�mo se determina el monto final de una
   compra por un libro de texto y uno de literatura.

   3. Implemente en Pharo.

   4. Instancie en un workspace su facturador, 2 libros de texto y 2 de literatura (a su elecci�n), un nuevo
   cliente y env�e al facturador el mensaje #facturar:para:. Indique cual es el monto que deber� informarse
   en el Transcript para ese caso en particular.

Ejercicio 10 (Avanzado)

  Una instancia de Homero responde a los siguientes mensajes

#beberCerveza
  "imprime en el transcript: bebiendo una Duff"

#verTelevision
  "imprime en el transcript: Mirando sala de emergencia para
  monos"

  Cuando recibe cualquier otro mensaje un Homero, responde en el Transcript con el text "D'oh!".

  Tarea

  1. Estudie el m�todo #doesNotUnderstand en Object, categor�a "reflective operations".
  2. Implemente el Smalltak el objeto Homero.
  3. Compruebe que las instancias de Homero responden correctamente.
  4. Extienda la implementaci�n para que adem�s de imprimir: D'oh! en transcript indique el nombre

  del mensaje que no entendi�. Por ejemplo si en el workspace escribimos:
  Homero new irAlTrabajo

  El resultado en el Transcript deber�a ser:
  irAlTrabajo ? Do'h!

Ejercicio 11 (Avanzado)

  Inspeccione a nil (utilice la opci�n "inspect it" desde un workspace) y responda:
  1. �A qu� clase pertenece?
  2. �Qu� comportamiento se implementa en el testing de esa clase?
  3. �Puede instanciar esa clase?

Ejercicio 12 (Avanzado)

  Ahora que conoce un poco m�s sobre nil defina el siguiente comportamiento para nil. El objeto nil ahora
  debe comportarse como el elemento neutro para la suma y la multiplicaci�n cuando aparece como
  receptor del mensaje + o * respectivamente. Es decir, si en workspace evaluamos:

  nil + 9
  el resultado debe ser 9. Y si en workspace evaluamos

  nil * 25
  el resultado debe ser 25.

  Tareas

  1. Implemente en la clase de la cual es instancia nil, los mensajes + y *, que reciben como
  par�metro un n�mero.

  2. Pruebe en el workspace

Ejercicio 13 (Avanzado)

  En Smalltalk todo son objetos: las clases y los m�todos tambi�n. Enviando el mensaje #methods a una
  clase obtendr� un array con todos los m�todos. Y enviando el mensaje #withAllSubclasses a una clase
  obtendr� una colecci�n con todas las subclases de esa clase.

  Tareas

  1. Busque la implementaci�n de ambos m�todos y lea los comentarios para entender la funcionalidad
  provista. Sugerencia: utilice el finder, que se puede encontrar dentro del tools en el menu de world.
  2. Utillizando esos mensajes e indique cuantos m�todos se encuentran definidos en la jerarqu�a de
  Collection
