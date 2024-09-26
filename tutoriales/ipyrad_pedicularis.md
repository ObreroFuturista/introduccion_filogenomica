Utilizaremos datos del estudio de Eaton & Ree (2013) single-end RAD para revisar todo el flujo de trabajo de iPyrad.


![image](https://github.com/user-attachments/assets/9acac277-6026-443f-9e3d-0f98fb6fba3e)


En el directorio analisis crea un nuevo directorio ipyrad_p y dentro de esta, una que se llame denovotest. Desde tu home sería así

`mkdir analisis/ipyrad_p`

`cd analisis/ipyrad_p/`

`mkdir denovo_pedicularis`

`cd denovo_pedicularis`

Activamos el ambiente de conda de ipyrad

`conda activate ipyradg`

Creamos un archivo de configuración qde parametros ue después modficaremos.

`ipyrad -n pedicularis`

En este caso las lecturas ya estan demultiplexadas, así el archivo de parametros lo modificaremos 
para que lea las lecturas individuales desde la carpeta **/seqs/ipyrad_pedic**

/home/usr30/seqs/ipyrad_pedic/*fastq   [4]

También indicamos que el umbral de clustering [14]  sea de 0.90

Cambiamos el parametro [27] por un _*_ para obtener todos los archivos de output

Corremos el ensamble

`ipyrad -p params-pedicularis -s 12345678 -c 2`
