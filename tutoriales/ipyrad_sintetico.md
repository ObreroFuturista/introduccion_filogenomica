Utilizaremos datos sinteticos para revisar todo el flujo de trabajo de iPyrad.

En el directorio analisis crea un nuevo directorio _ipyrad_s_ y dentro de esta, una que se llame _denovotest_. Desde tu home sería así 

`mkdir analisis/ipyrad_s`

`cd analisis/ipyrad_s/`

`mkdir denovotest`

`cd denovotest`


Estando en la carpeta recién creada activa el ambiente de conda que tiene ipyrad

`conda activate ipyrad`

Para el ensamble de novo vamos autilizar dos arvhivos. 
+ ../../../seqs/ipyrad_sint/rad_example_R1_.fastq.gz Que contiene secuencias crudas simuladas para 12 muestras.
+ ../../../seqs/ipyrad_sint/rad_example_barcodes.txt Los barcodes para demultiplexar las muestras.

Con _tail_ puedes ver la notación de los barcodes, una columna con el nombre de la muestra y se siguiente con el barcode que 
la identifca

`tail ../../../seqs/ipyrad_sint/rad_example_barcodes.txt`

Tenemos que ajustar nuestro ensamble a traves de un archivo de configuración de paramátros. 

Creamos un archivo de configuración que despues modficaremos. 

`ipyrad -n test`

![image](https://github.com/user-attachments/assets/9141bbfb-3616-44c1-81ca-59a255e3311c)
