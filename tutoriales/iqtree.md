 
mkdir analisis/iqtree

cd analisis/iqtree

cp ../ipyrad_p/denovo_pedicularis/pedicularis_outfiles/pedicularis.nex ./
cp ../ipyrad_p/denovo_pedicularis/pedicularis_outfiles/pedicularis.phy ./

conda activate iqtree

iqtree2 -s pedicularis.phy --alrt 1000
 -B 1000

