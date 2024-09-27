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

# Con Outgroups y bootstraps automáticos

raxmlHPC -f a -m GTRGAMMA -p 12345 -x 12345 -o 33588_przewalskii_SRR1754727,32082_przewalskii_SRR1754729 -# autoMRE -s pedicularis.phy -n autoB_out
