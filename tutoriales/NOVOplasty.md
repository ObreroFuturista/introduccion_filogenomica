#NOVOPlasty

Este tutorial tiene como objetivo guiar el proceso de uso de NOVOPlasty (Dierckxsens et al, 2016), una herramienta diseñada para ensamblar genomas circulares, como los genomas mitocondriales o de cloroplastos, utilizando datos de secuenciación de lectura corta (Illumina). NOVOPlasty es útil para reconstruir estos genomas directamente a partir de secuencias de novo, ayudado por una secuencia de referencia conocida (semilla o seed).


![image](https://github.com/user-attachments/assets/aba76627-5477-4ed3-8ef6-b2761f7bd742)

## Requisitos previos:


 Instalación de NOVOPlasty: Para instalar NOVOPlasty, es necesario clonar su repositorio desde GitHub o se puede instalar desde conda
 > https://anaconda.org/bioconda/novoplasty 

Ya está instalado en el servidor. 
Se activa el ambiente correspondiente 

> conda activate novoplasty

Para correr novoplasty es necesario lo siguiente

+ Datos de secuenciación: Se requiere un archivo de secuencias en formato FASTQ con lecturas cortas (Illumina), las cuales pueden estar comprimidas en formato .fastq.gz.

+ Secuencia de semilla (seed): Es recomendable contar con una secuencia corta de ADN del genoma mitocondrial o cloroplasto de interés. Esta secuencia actúa como punto de partida para el ensamblaje y generalmente proviene de una región conservada, como un gen conocido (por ejemplo, COI para mitocondrias o rbcL para cloroplastos).



## Crear el archivo de configuración
NOVOPlasty requiere un archivo de configuración que contenga todos los parámetros necesarios para realizar el ensamblaje. A continuación, se muestra un ejemplo de archivo de configuración para un proyecto de ensamblaje mitocondrial:

![image](https://github.com/user-attachments/assets/b8265ccc-4e63-4269-a105-fd7d4e4008dc)


Descripción de los parámetros clave:
+ Project name: Nombre del proyecto.
+ Type: Define el tipo de genoma a ensamblar (mito para mitocondrias, chloro para cloroplastos).
+ Genome Range: Rango estimado del tamaño del genoma. Por ejemplo, los genomas mitocondriales suelen estar entre 14,000 y 19,000 pb.
+ K-mer: Tamaño del k-mer utilizado para el ensamblaje. Generalmente, un valor de 39 es adecuado, pero puede ajustarse según los resultados.
+ Seed Input: La secuencia de semilla que inicia el proceso de ensamblaje (una secuencia conocida de ADN conservado).
+ Platform: La plataforma de secuenciación utilizada, en este caso Illumina.
+ Single/Paired: Indica si los datos son de lecturas apareadas (PE) o simples (SE).
+ Paired reads: Archivos FASTQ de lecturas apareadas, que contienen las secuencias forward y reverse.

## Ejecutar NOVOPlasty
Con el archivo de configuración listo, se puede iniciar el ensamblaje. Para ello, debe ejecutarse el siguiente comando en la terminal, dentro del directorio de trabajo que contiene el archivo de configuración y los datos de secuencias.


Crear un directorio para el ensamble de mitogenoa

`mkdir analisis/mitogenoma`

`cd analisis/mitogenoma/`

Copiamos el archivo de configuración a nuestro directorio actual

`cp ../../seqs/mitogenoma_wgs/config.txt ./`

Con nano modificamos las rutas de las lecturas wgs, la semilla y el genoma de referencia



Activamos el ambiente de NOVOplasty

`conda activate novoplasty`

Corremos el análisis

`NOVOPlasty.pl -c config.txt`

Para anotar el mitogenoma

Galaxy
https://usegalaxy.org/?tool_id=toolshed.g2.bx.psu.edu%2Frepos%2Fiuc%2Fmitos2%2Fmitos2%2F2.1.7%20galaxy0

https://mitofish.aori.u-tokyo.ac.jp/annotation/input/



