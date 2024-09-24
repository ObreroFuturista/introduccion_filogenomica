# Control de calidad de datos crudos de secuenciación 

Cuando se reciben datos de secuenciación crudos (raw data) de un servicio de secuenciación, típicamente llegan en formato FASTQ comprimido (.fastq.gz). 
Estos archivos contienen la información de las secuencias leídas junto con los valores de calidad asociados a cada base.
Realizar el control de calidad (QC) de estos datos de secuenciación es fundamental para obtener resultados fiables 
en estudios filogenómicos. Se utilizan dos herramientas  clave en este proceso: FastQC, que permite evaluar 
la calidad de las lecturas de secuenciación, y Fastp, una herramienta para la limpieza y filtrado de dichas lecturas. 

## FastQC

FastQC es un programa que proporciona una evaluación rápida y exhaustiva de la calidad de los datos crudos de secuenciación. 
Se utiliza para generar un informe detallado que incluye métricas clave de calidad, permitiendo identificar problemas potenciales como:

+ Lecturas de baja calidad.
+ Adaptadores de secuenciación sin recortar.
+ Sesgos en la composición de bases.
+ Distribuciones anómalas del contenido GC.
+ Longitudes inadecuadas de las lecturas.

FastQC puede ejecutarse en dos modos: línea de comandos (ideal para grandes conjuntos de datos) o una interfaz gráfica (GUI) para análisis más pequeños o exploratorios.
Utilizaremos la interfaz gráfica. Esto debes hacerlo en tu propia computadora, pues no hay GUI en el servidor.  

Dirigete a la página de FASTQ y descarga la versión para tu susteme operativo
> https://www.bioinformatics.babraham.ac.uk/projects/download.html#fastqc

Al descomprmir la carpeta te deben aparecer estos archivos. Ejecuta fastqc

![image](https://github.com/user-attachments/assets/d9a731eb-1f2e-4a1a-aa47-3deccf65cc19)

Descarga los archivos de secuencias crudas. Estos archivos son la subselección de muestras multiplexadas en un pool.  



[Archivo_R1](../dddrad/sub_Vlad_1_S8_R1_001.fastq.gz)

[Archivo_R2](../dddrad/sub_Vlad_1_S8_R2_001.fastq.gz)

Siguente la pestaña File y luego Open selecciona los arvhivos que descargaste. 

![image](https://github.com/user-attachments/assets/11f21f27-1f26-4486-bf78-2f42c253072d)

Aparece un reporte como este:

![image](https://github.com/user-attachments/assets/e778ce13-42b8-49b9-b4d2-4800498f534f)

Una vez revisados los resultados de FastQC, es importante identificar si las lecturas cumplen con los estándares de calidad esperados.
Si se detectan problemas como presencia de adaptadores o baja calidad en los extremos de las lecturas, se puede proceder al siguiente paso, 
que consiste en limpiar y filtrar las secuencias utilizando Fastp.

## fastp 

Es una herramienta de preprocesamiento para datos de secuenciación que permite el recorte de adaptadores, el filtrado de lecturas de baja calidad, 
y la corrección de diversos problemas en las lecturas crudas. Es eficiente y rápida, además de generar un reporte detallado sobre las operaciones realizadas.

![image](https://github.com/user-attachments/assets/7ae390bb-a4a1-4a42-be06-f9e3f091b510)


Ya está instalado en el servidor. La manera más eficiente instalarlo en tu propia computadora es a través de conda
> conda install bioconda::fastqc

Para usarlo en el servidor tenemos que activar el ambiente conda
![image](https://github.com/user-attachments/assets/9ec2caf7-d953-4949-901a-a01de234e1f3)

Las lecturas que vamos a filtrar ya estan cargadas en el servidor, para tener acceso a ellas creamos un link simbólico a la carpeta. Primero creamos una carpeta,
y despues creamos los links simbólicos

![image](https://github.com/user-attachments/assets/23fb40bc-7c13-474a-a8b9-f36475858a64)


Ejecución básica de Fastp
Para ejecutar Fastp con un archivo de lectura forward (R1) y uno reverse (R2), el siguiente comando básico será suficiente para realizar una limpieza de las secuencias:

![image](https://github.com/user-attachments/assets/85a83080-f0db-4ffc-a0b2-a6c30341afc4)


+ -i: especifica el archivo de lectura forward (R1). 
+ -I: especifica el archivo de lectura reverse (R2). 
+ -o: define el archivo de salida para las lecturas forward limpias. 
+ -O: define el archivo de salida para las lecturas reverse limpias. 
+ -q: Calidad mínima


![image](https://github.com/user-attachments/assets/f662aa1a-d061-499b-9960-14c9d2738f4a)

## Descargar resultados mediante Filezilla

Bajar e instalar Filezilla

![image](https://github.com/user-attachments/assets/37576af7-d65e-4b7c-9697-51b481aaa4dc)

Ingresar con los datos de IP, usuario y contraseña

![image](https://github.com/user-attachments/assets/48ca7164-ffb8-4322-8e5c-342e75e88ef7)

Localizar el archivo _fastp.html_. Es el reporte del control de calidad.


