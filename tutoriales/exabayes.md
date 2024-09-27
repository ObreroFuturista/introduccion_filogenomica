# Exabayes

ExaBayes realiza inferencias filogenéticas mediante métodos bayesianos, es particularmente efectivo 
en análisis de conjuntos de datos a escala genómica.



`mkdir analisis/exabayes
`
`cd analisis/exabayes/`

`conda activate exabayes`

`cp ../ipyrad_p/denovo_pedicularis/pedicularis_outfiles/pedicularis.phy ./`

`yggdrasil -n test -s 123 -f pedicularis.phy -m DNA`

Donde:

+ yggdrasil: Es el ejecutable principal de ExaBayes, que coordina los análisis MCMC. Se encarga de realizar la inferencia filogenética utilizando algoritmos bayesianos.

+ -n test: Especifica el nombre del análisis. Todos los archivos de salida generados por ExaBayes llevarán este prefijo (en este caso, test).

+ -s 123: Define la semilla para la generación de números aleatorios, necesaria para reproducir el análisis exactamente. 

+ -f : Especifica el archivo de alineamiento en formato PHYLIP.

+ -m DNA: Define el tipo de datos que se están analizando. En este caso, DNA indica que los datos corresponden a secuencias de ADN.
