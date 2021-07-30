# Data Engineer Programming Test

### SQL

Para este test hemos creado un entorno inventado que simula situaciones de nuestra arquitectura actual. El candidato debe suponer que es un empleado del banco Santander y debe resolver una situación planteada por un área de negocio.

En este escenario, los datos de logueo de los usuarios del Santander se encuentran en una única tabla sobre BigQuery. En esta table se guarda toda la información referente a las actividades realizan los usuarios cuando ingresan al Home Banking de Santander. La estructura de dicha tabla se pueden ver a continuación:

Field	Type	Comments
USER_ID	NUMBER(38,0)	Id del Usuario
SESSION_ID	NUMBER(38,0)	Id de Sesión
SEGMENT_ID	NUMBER(10,0)	 Id de Segmento
SEGMENT_DESCRIPTION	VARCHAR(100)	Segmento del Usuario logueado
USER_CITY	VARCHAR(50)	Ciudad desde donde se autentica el Usuario
SERVER_TIME	TIMESTAMP
	Día y Hora del Evento
DEVICE_BROWSER	VARCHAR(10)	Explorador desde donde se realize el evento
DEVICE_OS	VARCHAR(5)	Sistema Operativo
DEVICE_MOBILE	VARCHAR(10)	Dispositivo Movil
TIME_SPENT	NUMBER(38,0)	Tiempo que duro la sesión
EVENT_ID	NUMBER(38,0)	Id del Evento
EVENT_DESCRIPTION	VARCHAR(50)	Descripción del Evento
CRASH_DETECTION	VARCHAR(100)	Mensaje de Error
 
Basado en esa tabla, el área de la banca privada del banco desea que se arme un modelo dimensional en donde se contemplen dos tablas principales:
●	La primera vez que el usuario se logueo al Home Banking. Asumiendo que dicha situación es un tipo de evento.
●	La actividad diaria de cada usuario.

Tenga en cuenta las siguientes consideraciones técnicas:
1.	La table de origen contiene mil millones de registros.
2.	El modelo a construer debe poder ejecutarse tanto en consolas SQL o en herramientas de BI.
3.	Uno de los KPIs mas importantes que tiene la organización es la de retención de clientes. Dicho KPI es el porcentaje de usuarios que realizaron una actividad diferente al login durante 2 dos días consecutivos y cuya sesión haya durando al menos 5 minutos.

Pregunta 1
Como resolvería este tipo de petición? Explique detalladamente el proceso de limpieza y transformación del modelo inicial. Que tecnologías utilizaría y por que?

Ejercicio 1
Realice el DER que de soporte al modelo dimensional solicitado por la banca privada.

Ejercicio 2 
Escriba las queries necesarias partiendo de la tabla inicial y que de como resultado el modelo planteado en el ejercicio anterior.

Ejercicio 3
Escriba la consulta necesaria para obtener el KPI de retención de clientes para los 10 clientes que mas veces se hayan logueado en el último mes.
![image](https://user-images.githubusercontent.com/62435760/127664505-8dd107f3-9cec-4b8f-b652-9c830f6d5f3d.png)


### Python 
(Para hacerlo interesante, usar Python 2.7)

Se deberá escribir un script que transforme el archivo datos_data_engineer.tsv en un archivo CSV que pueda ser insertado en una base de datos, y/o interpretado por cualquier parser estándar de archivos delimitados, de la manera más sencilla posible.

El archivo resultante debe tener las siguientes características:
* Cada row contiene la misma cantidad de campos
* Los campos se separan con un pipe |
* Se deben poder leer correctamente los caracteres especiales que estén presentes en los campos actuales del archivo. 
* El encoding del archivo final debe ser UTF-8 (datos_de_santander.tsv es un archivo UTF-16LE)


