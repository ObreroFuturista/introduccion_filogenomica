# IQ TREE

IQ-TREE es un software ampliamente utilizado en la inferencia filogenética por su eficiencia en la estimación de árboles de máxima verosimilitud (ML). 
Este programa es capaz de seleccionar automáticamente el modelo evolutivo óptimo, aplicar técnicas de soporte nodal como el test de razón de verosimilitud 
aproximada (aLRT) y análisis de bootstrap ultrarrápido (UFBoot).

# Análisis básico

Creamos una carpeta para el análisis
 
`mkdir analisis/iqtree`

`cd analisis/iqtree`

`cp ../ipyrad_p/denovo_pedicularis/pedicularis_outfiles/pedicularis.phy ./`

`conda activate iqtree`

Ejecutamos el comando:

`iqtree2 -s pedicularis.phy --alrt 1000 -B 1000 -m basico -m MFP -mset mrbayes -mrate E,I,G,I+G   -T 2 -o 33588_przewalskii_SRR1754727,32082_przewalskii_SRR1754729`

Donde

+ -s: Define el archivo de entrada
+ --alrt: Replicaciones del test de razón de verosimilitud (aLRT).
+ -B: Réplicas de bootstrap ultrarrápido.
+ -m MFP: Selección automática del mejor modelo de sustitución.
+ -mset mrbayes: Limita los modelos a los compatibles con MrBayes.
+ -mrate E,I,G,I+G: Prueba modelos con tasas iguales, sitios invariables, gamma e I+G.
+ -T : Hilos de CPU.
+ -o : outgrpup
+ -m : Nombre del análisis


Comparación respecto a RaxML

# Con determinación del mejor## modelo por particion

{ echo "#NEXUS"; sed -n '/BEGIN SETS;/,/END;/p' pedicularis.nex; } > particiones.nex

iqtree -s pedicularis.phy -p example.nex

`cp ../ipyrad_p/denovo_pedicularis/pedicularis_outfiles/pedicularis.nex ./`
