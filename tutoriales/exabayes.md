# Exabayes

ExaBayes realiza inferencias filogenéticas mediante métodos bayesianos, es particularmente efectivo 
en análisis de conjuntos de datos a escala genómica.

Crear una carpteta

`mkdir analisis/exabayes
`
`cd analisis/exabayes/`

Activar el ambiente

`conda activate exabayes`

Copiar el alineamiento

`cp ../ipyrad_p/denovo_pedicularis/pedicularis_outfiles/pedicularis.phy ./`

`yggdrasil -n test -s 123 -f pedicularis.phy -m DNA`

Donde:

+ yggdrasil: Es el ejecutable principal de ExaBayes, que coordina los análisis MCMC. Se encarga de realizar la inferencia filogenética utilizando algoritmos bayesianos.

+ -n test: Especifica el nombre del análisis. Todos los archivos de salida generados por ExaBayes llevarán este prefijo (en este caso, test).

+ -s 123: Define la semilla para la generación de números aleatorios, necesaria para reproducir el análisis exactamente. 

+ -f : Especifica el archivo de alineamiento en formato PHYLIP.

+ -m DNA: Define el tipo de datos que se están analizando. En este caso, DNA indica que los datos corresponden a secuencias de ADN.

  El análisis correra por 1,000,000 generaciones. Para un mayor control de las generaciones y parametros se puede implementar un [archivo de
  configuracion](https://app.assembla.com/spaces/exa-bayes/git/source/master/examples/configFile-all-options.nex)

El análisis completo lleva algún tiempo, lo detenemos para inspeccionar los outputs. 

Generamos un arbol de concenso, lo descargamos y visualizamos en FigTree. (ExaBayes_ConsensusExtendedMajorityRuleNexus.myCons)

`./consense -f ExaBayes_topologies.myRun.0 -n test`

En Tracer verificamos los valores de ESS con el archivo. 

ExaBayes_parameters.run-0.test
