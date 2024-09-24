#NOVOPlasty

Este tutorial tiene como objetivo guiar el proceso de uso de NOVOPlasty (Dierckxsens et al, 2016), una herramienta diseñada para ensamblar genomas circulares, como los genomas mitocondriales o de cloroplastos, utilizando datos de secuenciación de lectura corta (Illumina). NOVOPlasty es útil para reconstruir estos genomas directamente a partir de secuencias de novo, ayudado por una secuencia de referencia conocida (semilla o seed).


![image](https://github.com/user-attachments/assets/aba76627-5477-4ed3-8ef6-b2761f7bd742)

## Requisitos previos:


+ Instalación de NOVOPlasty: Para instalar NOVOPlasty, es necesario clonar su repositorio desde GitHub:

![image](https://github.com/user-attachments/assets/fe2c34b5-7929-487f-93dc-3a9745c81245)


+ Datos de secuenciación: Se requiere un archivo de secuencias en formato FASTQ con lecturas cortas (Illumina), las cuales pueden estar comprimidas en formato .fastq.gz.

+ Secuencia de semilla (seed): Es recomendable contar con una secuencia corta de ADN (20-200 pb) del genoma mitocondrial o cloroplasto de interés. Esta secuencia actúa como punto de partida para el ensamblaje y generalmente proviene de una región conservada, como un gen conocido (por ejemplo, COI para mitocondrias o rbcL para cloroplastos).



## Crear el archivo de configuración
NOVOPlasty requiere un archivo de configuración que contenga todos los parámetros necesarios para realizar el ensamblaje. A continuación, se muestra un ejemplo de archivo de configuración para un proyecto de ensamblaje mitocondrial:


![image](https://github.com/user-attachments/assets/a322a329-207b-479a-a7b8-4bf87ea3d9d4)

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

> python NOVOPlasty.py -c config.txt

