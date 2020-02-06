# ChallengeDevOps



<h2>Nivel Docker Jenkins</h2>

a)Desde la imagen base de Jenkins, genere un Dockerfile donde descarge e instale Maven, además de ejecutar el pluggins.txt(más abajo se explica la necesidad de este archivo) debe tener en cuenta que este dockerfile se le podría agregar un proxy para entornos cerrados

b)Debe generar un Dockercompose o similar(setearlo en el docker run) para setear el volumen compartido del host a la imagen

c)Debe generar un archivo con los pluggins de Jenkins necesarios para poder levantar un pipeline desde un jenkinsfile que ejecutara un Job que descargue un código de git y ejecute un comando de maven, debe tomar en cuenta todas las tecnologías mencionadas ya que los pluggins correspondientes deben estar el fichero para que pueda ejecutarse el Job

d)Creara la imagen desde este dockerfile, y en caso de usar dockercompose deberá ejecutar los comandos correspondientes para la imagen y el contenedor.

e)Luego de ejecutar el contenedor, en el localhost deberá estar levantando el Jenkins 

f)Dentro de Jenkins debe configurar el agente principal con 12 Nodos/Ejecutores para que pueda ejecutar en Jobs en paralelo

g)Debe generar un Jenkinsfile con los siguientes parámetros:
1)	El agente será el principal de Jenkins y el Nodo debe ser cualquiera que esté disponible
2)	El primer stage será el de descarga de Git donde guardará los datos de las credenciales en el panel de configuración reservada de Jenkins y este será invocado en el Jenkinsfile con la variable del usuario y contraseña, el Brach también deberá ser una variable a selección en la construcción del Job 
3)	Luego en el siguiente stage ejecutara el comando “mvn test” desde la ruta donde se descargó el código

<h2>Criterios de aceptacion</h2>

Debería subir a este repositorio los dockerfiles , jenkinsfile y/o dockercompose solicitados, además de un readme documentando todos los comandos ejecutados en su orden y descripcion. de su imagen se levantara un contenedor el cual tendra el jenkins para ejecutar el job
