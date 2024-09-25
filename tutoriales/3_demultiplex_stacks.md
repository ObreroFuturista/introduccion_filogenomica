

# process_radtags

Stacks es una herramienta bioinformática para procesar datos obtenidos mediante secuenciación
de RADseq (Restriction site Associated DNA Sequencing) y otros métodos de genotipado basados en secuencias. Uno de 
los primeros y más importantes pasos en el análisis de datos RADseq es el preprocesamiento de las lecturas crudas 
usando el programa process_radtags de Stacks. 

El programa process_radtags es parte de la suite Stacks y se utiliza principalmente para:

+ Demultiplexar: Asignar lecturas a sus respectivas muestras, identificando los barcodes asociados.
+ Filtrar por calidad: Eliminar lecturas de baja calidad o con errores en los barcodes o sitios de restricción.
+ Recortar adaptadores: Eliminar adaptadores de secuencias de secuenciación que aún puedan estar presentes en los datos crudos.
+ Recortar lecturas: Recortar lecturas a una longitud específica.

Ya se encuentra instalado en el servidor. Localmente puede installarse a través de conda 
> conda install bioconda::stacks

## Para ejecutar process_radtags, se necesitan los siguientes archivos:

+ Datos crudos de secuenciación en formato FASTQ: Estos son los datos brutos generados por la secuenciación RADseq.
  Pueden ser archivos de lectura simple o lecturas emparejadas. En ellos se encuentral las secuencias crudas de diferentes muestras mezcladas
  entre si.

+ Archivo de barcodes: Un archivo de texto que contiene los barcodes, secuencias cortas que identifican cada muestra. Este archivo puede estar en formato de columnas
 separadas por tabulación. Para el archivo de secuencias crudas que tenemos utilizaremos estos barcodes. 


| CCGAATG     | CTAACGT     | Tau060  |
|-------------|-------------|---------|
| TTAGGCAG    | TCGGTACT    | Tta046  |
| AACTCGTCG   | GATCGTTGT   | Tst044  |
| GGTCTACGTG  | AGCTACACTT  | Teq033  |
| GATACCG     | ACGCATT     | Teq031  |
| AGCGTTGG    | GTATGCAT    | Tpi020  |
| CTGCAACTG   | CACATGTCT   | Tpi009  |


Los archivos que necesitaremos están en 
`seqs/rawdata/`
 
 En la carpeta _analisis_ creamos una carpeta
 
`mkdir stacks`

`cd stacks`

Activamos el ambiente stacks

`conda activate stacks`

Corremos el siguiente comando

process_radtags -P -p ../../dd




Donde: 

+ -P: Procesa lecturas emparejadas (paired-end).
+ -p ./raw/: Directorio de entrada con los datos crudos.
+ -o ./demultiplex/: Directorio de salida para los archivos filtrados.
+ -b ./barx.csv: Archivo con los barcodes para asignar muestras.
+ -c: remueve lectura con bases indeterminadas.
+ -q: Filtra lecturas de baja calidad.
+ -r: rescata bases en los extremos.
+ --renz-1 nheI --renz-2 ecoRI: Enzimas de restricción utilizadas.
+ --inline-inline: Barcodes en ambas lecturas (R1 y R2).

Resultados:

![image](https://github.com/user-attachments/assets/be68d7e9-9252-4c50-a4b9-f037e3f77090)

Borramos achivos .rem., sin pares. 

![image](https://github.com/user-attachments/assets/7205fb77-e3a2-4dfe-96d5-4cc5421eee4d)

