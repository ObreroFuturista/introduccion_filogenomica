# Shell de Linux

Introducir a los participantes en el uso de la línea de comandos en Linux, cubriendo temas fundamentales como la navegación
por el sistema de archivos, la gestión de archivos y directorios, y el uso de comandos esenciales en bioinformática. 

**¿Qué es la línea de comandos?**
La línea de comandos, también conocida como CLI (Command Line Interface), es una herramienta que permite interactuar directamente
con el sistema operativo mediante la introducción de comandos en texto. A diferencia de las interfaces gráficas, aquí se deben
escribir instrucciones específicas para realizar tareas. Permite un control mucho mayor sobre tu sistema, permitiéndote automatizar
tareas y trabajar de manera más eficiente, especialmente cuando se trata de manejar grandes cantidades de datos,
como es común en bioinformática.



## El prompt

El prompt indica que el sistema está listo para recibir un comando. Cuando se abre la terminal, aparecerá algo como esto:

![image](https://github.com/user-attachments/assets/0f88b950-d2bf-43c6-9071-44736ee2d935)

+ user: Tu nombre de usuario.
+ hostname: El nombre de tu máquina.
+ ~: El directorio en el que te encuentras actualmente (en este caso, el directorio personal o "home")


## Navegación por archivos y directorios

La línea de comandos es una herramienta muy potente para navegar por el sistema de archivos. Aquí aprenderemos a moverte entre carpetas, 
listar el contenido y verificar en qué directorio nos encontramos.



+ pwd (Print Working Directory): Este comando te muestra en qué directorio estás actualmente. Úsalo cuando quieras verificar tu ubicación dentro del sistema de archivos.

![image](https://github.com/user-attachments/assets/7ee5ac00-53d5-454f-8bd5-efd601ebc877)


El comando _ls_ lista el contenido del directorio actual, mostrando los archivos y carpetas que están presentes en la ubicación actual. 
Es uno de los comandos más utilizados porque que permite explorar el contenido de diferentes directorios.


![image](https://github.com/user-attachments/assets/0efc752e-520b-438d-acc6-05eaa8b94878)

+ ls -l: Muestra una lista detallada con información adicional como permisos de archivos, propietarios, tamaño y fecha de modificación.
+ ls -a: Muestra todos los archivos, incluyendo los ocultos (aquellos cuyo nombre comienza con un punto ., como .bashrc).
+ ls -lh: Lista los archivos en un formato legible por humanos, donde los tamaños de archivos se muestran en KB, MB, etc.

![image](https://github.com/user-attachments/assets/7ce84ba6-59f9-4169-a146-ace7a825abb5)



Cuando nos movemos entre directorios o trabajas con archivos, hay dos tipos de rutas que podemos utilizar:

Ruta Absoluta
Una ruta absoluta es aquella que comienza desde el directorio raíz del sistema de archivos, que en Linux y macOS está representado por **/**. 
Este tipo de ruta proporciona la ubicación completa de un archivo o directorio, desde el directorio raíz hasta el destino final. Siempre comienza con **/**.

Una ruta relativa es aquella que se especifica en relación con el directorio en el que se está trabajando actualmente. En lugar de comenzar desde el directorio raíz, se inicia desde la ubicación actual dentro del sistema de archivos, que puede variar dependiendo del directorio de trabajo en el que se esté.

Las rutas relativas no comienzan con /. En cambio, se basan en el directorio actual y pueden incluir referencias especiales como:

+ **.** (punto) para referirse al directorio actual.

++ **..** (doble punto) para referirse al directorio superior o padre.























### 1.1 Rutas absolutas

Una ruta absoluta especifica la ubicación exacta de un archivo o directorio desde el directorio raíz (/), 
que es el punto más alto de la jerarquía de directorios en Linux. Siempre comienzan con el carácter **/**

Ejemplo: Si tienes un archivo llamado _secuencia.fasta_ en la carpeta Documentos de tu usuario, la ruta absoluta al archivo sería:






![image](https://github.com/user-attachments/assets/c65f89ab-3b35-4acb-8c92-abbb6f39ca0a)
