Antes de empezar. Crear un link simbólico a los archivos del directorio seqs

`ln -s /home/vs/seqs/ ./seqs`

Aparecerá una carpeta en nuestro home. Creamos el directorio _analisis_ y dentro de ella la carpeta _fastp_ que será en donde guardaremos los outputs
de la limpieza con fastp.

`mkdir analisis`

`cd analisis`

`mkdir fastp`

`cd fastp`


## fastp 

Es una herramienta de preprocesamiento para datos de secuenciación que permite el recorte de adaptadores, el filtrado de lecturas de baja calidad, 
y la corrección de diversos problemas en las lecturas crudas. Es eficiente y rápida, además de generar un reporte detallado sobre las operaciones realizadas.

Ya está instalado en el servidor. Activamos el ambiente virtual en el que está instalada.

`conda activate fastp_env`

Vamos a utilizar las rutas relativas para usar como inputs los archivos de los links simbólicos, y guardarlos en el directorio fasp que creamos y en el que estamos situados. 

`fastp -i ../../seqs/rawdata/Vlad_1_S8_R1_001.fastq.gz -I ../../seqs/rawdata/Vlad_1_S8_R2_001.fastq.gz -o ./Vlad_.q25.R1.fastq.gz -O ./Vlad_.q25.R2.fastq.gz -q 25 -h test25 `

En donde:

+ -i: Archivo de entrada R1
+ -I: Archivo de entrada R2
+ -o: Archivo de salida R1
+ -O: Archivo de salida R2
+ -q: Umbral de calidad Q mínimo
+ -h: Nombre del reporte html

Aparece un reporte en pantalla

![image](https://github.com/user-attachments/assets/b24d0ebb-0bbe-4350-b537-18ad1571cda4)


Prueba con un valor mas estricto de calidad.

`fastp -i ../../seqs/rawdata/Vlad_1_S8_R1_001.fastq.gz -I ../../seqs/rawdata/Vlad_1_S8_R2_001.fastq.gz -o ./Vlad_.q35.R1.fastq.gz -O ./Vlad_.q35.R2.fastq.gz -q 35 -h test35 `

Si usamos _ls_ encontraremos los archiuvos limpiados habo diferentes umbrales de calidad y dos reportes.  

![image](https://github.com/user-attachments/assets/6d1d7e36-d40e-4c18-b4cc-b01c1f0da351)

Vamos usar Filezilla. 
En los campos correspondinetes ponene sus credenciales para entrar al servidor. 

Sale una interfaz muy intuitiva en la que del lado izquierdo están directorios y archivos locales, y del lado derecho directorios y archivos 
en el servidor. 

Basta arrstar los archivos test25 y test35 al sistema local.


![image](https://github.com/user-attachments/assets/5dfdb4ea-7c7c-44d6-9f5f-b5bdcbd5015b)

Inspeccionar resultados

![image](https://github.com/user-attachments/assets/2a9e6d1b-9780-40e8-b9bc-60e1ed3bb6b4)



