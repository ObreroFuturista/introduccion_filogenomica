# RAxML

RAxML (Randomized Axelerated Maximum Likelihood) es uno de los software más poderosos y eficientes para 
la inferencia filogenética mediante el método de máxima verosimilitud (ML). RAxML es capaz de manejar 
grandes conjuntos de datos genómicos.


# Análisis Básico

El comando básico para inferir un árbol filogenético con bootstrap es el siguiente:

> raxmlHPC -f a -m GTRGAMMA -p 12345 -x 12345 -# 100 -s dna.phy -n test

-f a: Análisis rápido de bootstrap mientras y búsqueda del mejor árbol ML de manera simultánea

-m: Modelo evolutivo GTRGAMMA

-#: 100 réplicas de bootstrap

-s: Alineamiento dna.phy en formato PHYLIP

-p y -x : Semillas para reproducibilidad del análisis

-n:  prefijo del análisis 


Reconstruyamos un árbol con RAXML

`mkdir analisis/raxml`

`cd analisis/raxml/`

copiar el alineamiento de los resultados del ensamble

`cp ../ipyrad_p/denovo_pedicularis/pedicularis_outfiles/pedicularis.phy ./`

Activamos el ambiente correspondiente

`conda activate raxml`

`raxmlHPC -f a -m GTRGAMMA -p 12345 -x 12345 -# 100 -s pedicularis.phy -n test`

En el archivo RAXML_bipartitions.test esta el mejor árbol con valores de botstrap en los nodos

# Con Outgroup y bootstraps automáticos

`raxmlHPC-PTHREADS -f a -m GTRGAMMA -p 12345 -x 12345 -o 33588_przewalskii_SRR1754727,32082_przewalskii_SRR1754729 -# autoMRE -s pedicularis.phy -n autoB_out -T 2`

+ raxmlHPC-PTHREADS: versión de raxml que permite hacer en análisis con varios threads 

+ T: número de threads

+ -o: grupo externo (outgroup). En este caso, se están especificando dos taxones (33588_przewalskii_SRR1754727 y 32082_przewalskii_SRR1754729) como el grupo externo del árbol. Estos taxones servirán como referencia para enraizar el árbol filogenético.

+ -# autoMRE: criterio de convergencia automática utilizando MRE (Majority Rule Extended) para determinar el número óptimo de réplicas de bootstrap. Esto significa que el análisis de bootstrap se detendrá automáticamente cuando la topología del árbol y los valores de soporte de los nodos converjan y dejen de cambiar de manera significativa con la adición de más réplicas.


Comparar ambos árboles
