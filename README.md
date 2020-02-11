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
2)	El primer stage será el de descarga de Git donde guardará los datos de las credenciales en el panel de configuración reservada de Jenkins y este será invocado en el Jenkinsfile con la variable del usuario y contraseña, el Brach también deberá ser una variable a selección en la construcción del Job (el repo que se va a descargar es el siguiente https://github.com/luishernandez25/easyTest)
3)	Luego en el siguiente stage ejecutara el comando “mvn test” desde la ruta donde se descargó el código

<h2>Criterios de aceptacion</h2>

Debería subir a un repositorio los dockerfiles , jenkinsfile y/o dockercompose solicitados, además de un readme documentando todos los comandos ejecutados en su orden y descripcion. de su imagen se levantara un contenedor el cual tendra el jenkins para ejecutar el job


<h2>Nivel Kubernetes </h2>

Deberera crear infra como codigo mediante kubernetes 
1)Su tarea es proporcionar un repositorio git que contendrá el código para construir un clúster de Kubernetes con las siguientes especificaciones:

A)El clúster tendrá mínimo 2 nodos de trabajo.
Los worker tendrán:
1 nodos completos no preferentes de tipo n1-standard-2 (sin escala automática)
1 nodos preferentes de tipo n1-standard-2 
El clúster tendrá 1 usuario administrador (admin) y 5 usuarios regulares (usuario-1, usuario-2, etc.)
El clúster tendrá 2 espacios de nombres
usuario-1
usuario-2

B)El usuario administrador tendrá permisos de lectura y escritura para todos los espacios de nombres

C)El usuario-1 tendrá permisos de lectura para el clúster y permisos de escritura para el espacio de nombres del usuario-1

D) Del mismo modo, el usuario 2 tendrá acceso de lectura al clúster y acceso de escritura al espacio de nombres del usuario 2

F)Cree un archivo README.md que proporcione instrucciones sobre cómo usar su repositorio

P.D)Puede elegir cualquier herramienta disponible gratuitamente que considere útil en las tareas anteriores. Para Azure y Google Cloud, puede haber algunas diferencias en los requisitos este challenge está adaptado para AWS. Traduzca los requisitos al similar según la plataforma.

<h2> Criterios de aceptación </h2>

A)Debe proporcionar su código completo para que podamos replicar su clúster

B)Puede usar cualquier servicio en la nube de su selección (AWS, Google Cloud) para construir el clúster anterior (no necesita proporcionar acceso al clúster, solo al código)

C)El código debe ser limpio legible y sencillo

D)Debe documentar cualquier paso que no esté automatizado en README.md
