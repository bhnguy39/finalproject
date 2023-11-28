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


cat tree.fa.contree #copy everything 

#in R

if (!require("BiocManager", quietly = TRUE))

  install.packages("BiocManager")
  
BiocManager::install("ggtree")


install.packages("BiocManager")


install.packages("ape") 

install.packages("ggtree") 

library(ape)

library(ggtree)

shh_tree <- "(O157:0.0000023121,(EHEC:0.0034411895,(NBRC:0.0000023121,JCM:0.0000023121)72:0.0023831722)52:0.0000023045,U:0.0000023121);"


shh_tree <- read.tree(text=shh_tree)

shh_tree <- ape::root.phylo(shh_tree, outgroup = "NBRC")

ggtree(shh_tree) + geom_tiplab()



