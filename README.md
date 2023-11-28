# finalproject
conda create --prefix /project/stuckert/bhnguy39/Absolute/path/ofa/directory/in/your/file/structure/final_project
conda activate /project/stuckert/bhnguy39/Absolute/path/ofa/directory/in/your/file/structure/final_project
conda install -c bioconda mafft
conda install -c bioconda iqtree
mkdir final_project
cd final_project
nano #paste all of the data from NCBI into this file
ctrl +x #save this file as e.coli
nano 
#!bin/bash
#SBATCH --time=1-00:01
#SBATCH --cpus-per-task=5
#SBATCH --mem=10Gb
mafft --auto e.coli > project.fa
ctrl +x #save this file as proj
mafft --auto e.coli > project.fa #multiple genes alignment

nano 
#!bin/bash
#SBATCH --time=1-00:01
#SBATCH --cpus-per-task=5
#SBATCH --mem=10Gb
iqtree -s project.fa -m GTR -bb 1000 -pre tree.fa
ctrl +x #save this file as tree.fa
iqtree -s project.fa -m GTR -bb 1000 -pre tree.fa 


