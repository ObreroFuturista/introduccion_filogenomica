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

![image](https://github.com/user-attachments/assets/f39bb81b-8eaa-4c2b-b0ee-1552993827da)

+ user: Tu nombre de usuario.
+ hostname: El nombre de tu máquina.
+ ~: El directorio en el que te encuentras actualmente (en este caso, el directorio personal o "home")


## Comandos básicos

La línea de comandos es una herramienta muy potente para navegar por el sistema de archivos. Aquí aprenderemos a moverte entre carpetas, 
listar el contenido y verificar en qué directorio nos encontramos.


## pwd
+ pwd (Print Working Directory): Este comando te muestra en qué directorio estás actualmente. Úsalo cuando quieras verificar tu ubicación dentro del sistema de archivos.

![image](https://github.com/user-attachments/assets/13b9e8c4-4430-458c-87a8-c21a19fcae9d)

## ls
El comando _ls_ lista el contenido del directorio actual, mostrando los archivos y carpetas que están presentes en la ubicación actual. 
Es uno de los comandos más utilizados porque que permite explorar el contenido de diferentes directorios.

![image](https://github.com/user-attachments/assets/7d3711e6-88cb-4bed-a28a-007d9717b4ef)


+ ls -l: Muestra una lista detallada con información adicional como permisos de archivos, propietarios, tamaño y fecha de modificación.
+ ls -a: Muestra todos los archivos, incluyendo los ocultos (aquellos cuyo nombre comienza con un punto ., como .bashrc).
+ ls -lh: Lista los archivos en un formato legible por humanos, donde los tamaños de archivos se muestran en KB, MB, etc.

![image](https://github.com/user-attachments/assets/ae0982ab-5294-4f1b-83ee-da26cb07202c)


Cuando nos movemos entre directorios o trabajas con archivos, hay dos tipos de rutas que podemos utilizar:

Rutas
Una **ruta absoluta** es aquella que comienza desde el directorio raíz del sistema de archivos, que en Linux y macOS está representado por **/**. 
Este tipo de ruta proporciona la ubicación completa de un archivo o directorio, desde el directorio raíz hasta el destino final. Siempre comienza con **/**.

Una **ruta relativa** es aquella que se especifica en relación con el directorio en el que se está trabajando actualmente. En lugar de comenzar desde el directorio raíz, se inicia desde la ubicación actual dentro del sistema de archivos, que puede variar dependiendo del directorio de trabajo en el que se esté.

Las rutas relativas no comienzan con /. En cambio, se basan en el directorio actual y pueden incluir referencias especiales como:

+ **.** (punto) para referirse al directorio actual.

+ **..** (doble punto) para referirse al directorio superior o padre.

![image](https://github.com/user-attachments/assets/8168461d-1d94-497d-8012-e80c70a3dc2a)


## cd (Change Directory)
El comando _cd_ se utiliza para cambiar de directorio. Puedes moverte a un directorio específico utilizando su ruta absoluta o relativa.


![image](https://github.com/user-attachments/assets/b61c8889-b41f-431f-adcf-519870a30957)

+ cd ..: Sube un nivel en la jerarquía de directorios (al directorio anterior).
+ cd ~: Te lleva al directorio de inicio del usuario actual.
+ cd /: Te lleva al directorio raíz del sistema.


## mkdir (Make Directory)
Este comando permite crear un nuevo directorio o carpeta. Es útil para organizar trabajo en diferentes directorios.

![image](https://github.com/user-attachments/assets/1311fa6e-5ce0-40ae-9df6-0056ea67e9c1)

## touch (Crear archivos vacíos)
El comando touch se usa para crear un archivo vacío o actualizar la fecha de modificación de un archivo existente. Es muy común usarlo para generar archivos de forma rápida, aunque estén vacíos.

![image](https://github.com/user-attachments/assets/ef25578c-feb0-43b5-b1b7-c35832581c7d)

## cp (Copy)
Este comando se usa para copiar archivos o directorios. La opción -r es importante cuando queremos copiar directorios completos de forma recursiva.

para copiar archivos:
>cp archivo_origen archivo_destino

Para copiar directorios:
> cp -r directorio_origen directorio_destino

![image](https://github.com/user-attachments/assets/6f20d898-0ef9-4154-b166-ed5068c27c80)

## mv (Move/Rename)
El comando mv permite mover archivos de una ubicación a otra o renombrarlos. Si el archivo no se mueve de directorio, simplemente se renombra.
> mv archivo_origen archivo_destino

![image](https://github.com/user-attachments/assets/d8a861d9-bbfe-4611-aaf1-848b080ecc54)



## wget: Descarga archivos desde la web
El comando wget se usa para descargar archivos de Internet desde la línea de comandos. 
> wget https://zenodo.org/records/3736457/files/9_Swamp_S2B_trnL_2019_minq7.fastq

![image](https://github.com/user-attachments/assets/9ab0ae26-b054-48a1-af4f-b91968ae7eda)


## cat (Concatenate)
Este comando muestra el contenido de un archivo en la terminal. Es ideal para visualizar archivos de texto rápidamente.

![image](https://github.com/user-attachments/assets/94ad94d0-6aff-4fa2-8010-01792a3fc36c)

![image](https://github.com/user-attachments/assets/51f4b9e0-b5f5-400c-9db1-b18e01edf08f)


## less
El comando less permite visualizar archivos de forma interactiva, desplazándote hacia arriba o abajo. Para salir de less, presiona la tecla q.


## Redirección de salida (>, >>)
La redirección permite enviar la salida de un comando a un archivo en lugar de mostrarla en pantalla. Esto es útil para guardar los resultados de análisis o comandos largos.

![image](https://github.com/user-attachments/assets/9af2e2a5-ad74-4278-ad0e-2fb03efd87bb)

![image](https://github.com/user-attachments/assets/e730924a-900a-4ef7-9d03-f045922c2e8b)


> echo "ATCG" > A.txt  # Sobrescribe el archivo

> echo "GGTA" >> A.txt  # Añade al archivo

![image](https://github.com/user-attachments/assets/68721bde-f5ab-452d-ae01-a44623ed161b)

# Tuberías (|)
El operador | conecta la salida de un comando con la entrada de otro, creando una secuencia de comandos en una línea.

![image](https://github.com/user-attachments/assets/185ad342-a845-407e-96a1-4fac422fcf30)

![image](https://github.com/user-attachments/assets/1c94b18b-1a5c-4c85-a64a-cd0d4fc118d1)

#Actividad: Generar esta structura de directorio y archivos 

![image](https://github.com/user-attachments/assets/41bccaf5-ef9b-4d77-81fc-0ae921c5bb00)

