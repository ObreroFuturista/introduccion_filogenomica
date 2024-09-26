Utilizaremos datos sinteticos para revisar todo el flujo de trabajo de iPyrad.

En el directorio analisis crea un nuevo directorio _ipyrad_s_ y dentro de esta, una que se llame _denovotest_. Desde tu home sería así 

`mkdir analisis/ipyrad_s`

`cd analisis/ipyrad_s/`

`mkdir denovotest`

`cd denovotest`


Estando en la carpeta recién creada activa el ambiente de conda que tiene ipyrad

`conda activate ipyradg`

Para el ensamble de novo vamos autilizar dos archivos. 

+ `/home/usr30/seqs/ipyrad_sint/rad_example_R1_.fastq.gz` Que contiene secuencias crudas simuladas para 12 muestras.
+ `/home/usr30/seqs/ipyrad_sint/rad_example_barcodes.txt` Los barcodes para demultiplexar las muestras.

Con _tail_ puedes ver la notación de los barcodes, una columna con el nombre de la muestra y se siguiente con el barcode que 
la identifca

`tail ../../../seqs/ipyrad_sint/rad_example_barcodes.txt`

Tenemos que ajustar nuestro ensamble a traves de un archivo de configuración de paramátros. 

Creamos un archivo de configuración que despues modficaremos. 

`ipyrad -n test`

![image](https://github.com/user-attachments/assets/9141bbfb-3616-44c1-81ca-59a255e3311c)

Siete pasos

![image](https://github.com/user-attachments/assets/61333118-c1e4-4df6-82a1-ad084b3e20ba)

Demultiplexado / Carga de archivos FASTQ: Este paso carga los datos de secuencias y los demultiplexea por muestra. 
Si los datos no están demultiplexados, usa un archivo de barcodes para separar las lecturas por muestras.

Filtrado / Edición de lecturas: Aquí se filtran las lecturas de baja calidad basándose la información de calidad del archivo FASTQ. 
Se pueden eliminar adaptadores y eliminar secuencias de baja calidad.

Clústeres / Mapeo y alineación dentro de muestras: Las secuencias se desduplican, fusionan (si son de extremos pareados) y
luego se agrupan por similitud o se alinean a un genoma de referencia, dependiendo del método seleccionado.

Estimación conjunta de heterocigosidad y tasa de error: Se estiman la heterocigosidad y la tasa de error de secuenciación
basándose en los patrones de sitios observados en las lecturas agrupadas.

Llamado de consenso y filtrado: Se generan secuencias consenso a partir de las lecturas agrupadas y se filtran sitios con bases indeterminadas (N). 
Aquí también se registra la profundidad de lectura para análisis posteriores.

Clústeres / Mapeo entre muestras y alineación: Se agrupan las secuencias consenso entre diferentes muestras y se alinean nuevamente 
para generar clusters finales que contienen información de heterocigotos.

Filtrado y formato de archivos de salida: Se aplican filtros finales a las alineaciones y se generan archivos de salida en diferentes formatos,
ajustando el porcentaje de datos faltantes y otras características según los parámetros seleccionados.

Para ejecutarlo

`ipyrad -p params-test.txt -s 1234567`
