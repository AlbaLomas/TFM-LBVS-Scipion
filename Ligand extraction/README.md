PDB access and ligand extraction

<img width="180" alt="image" src="https://user-images.githubusercontent.com/83068588/175131200-7e794edb-802e-4812-8e22-f86610852590.png">


This folder contains the protocol code of Scipion and the associated script. The script is adapted from the code provided by Volkamer Lab[1]. 
Aditionally, it presents some modifications in order to automatizate the process. This improvement facilitates the calculation of the centers of mass of the different extracted ligands and their subsequent clustering thanks to the DBSCAN algorithm[2] implemented by scikit-learn package.


Protein Data Bank (PDB) is a public and supervised (Worldwide Protein Data Bank) database that stores the three-dimensional (3D) structure of different nucleic acids and proteins. 
These structures are provided by different biologists and biochemists from all over the world who obtain them through different techniques such as magnetic/nuclear resonance, X-ray crystallography or electron microscopy.

The Scipion protocol is focused on the search and extraction of ligands that bind to a target by PDB programmatically accessing, and filtering the structures it provides when we submit the target protein Uniprot ID. The objective of the protocol is to obtain a set of ligands that attach to the target protein at the same binding site in order to subsequently obtain a consensus pharmacophore. 
The fields used for filtering are: 
-	Uniprot ID of the target protein.

-	Experimental method: structure determination method, among the possible options are X-RAY DIFFRACTION, SOLUTION NMR, ELECTRON MICROSCOPY, etc or None, in case the experimental technique is not specified.

-	Minimum molecular weight of the ligand associated with the structure. 

-	Quality of the structure: the lower the angstrom resolution of the structure, the higher the quality.

-	Number of structure chains: it is recommended to set the value of this field to 1, as it simplifies the processing of the structure and the search.

-	Date of deposition: this field is enabled to ensure the reproducibility of the screening; the user sets a date after which any structure that is uploaded on the database will not be considered. In the protocol the user must choose a year and the date that will be passed to the search criteria is January 1st of the year set.

-	Number of final extracted ligands.


The output of the protocol is the generation of different SetOfSmallMolecules objects that will be made up by the ligands that have been grouped in the same cluster; in other words, there will be as many sets as clusters are obtained. 
Moreover, each molecule includes its canonical SMILES and the structure of its target protein as attributes, so that the binding site can be visualized and allows the user to check the clustering performed by the script.


[1] T008 · Protein data acquisition: Protein Data Bank (PDB). (s/f). Volkamerlab.Org. Recuperado el 22 de junio de 2022, de https://projects.volkamerlab.org/teachopencadd/talktorials/T008_query_pdb.html

[2]Ester, Martin; Kriegel, Hans-Peter; Sander, Jörg; Xu, Xiaowei (1996). «A density-based algorithm for discovering clusters in large spatial databases with noise». En Simoudis, Evangelos; Han, Jiawei; Fayyad, Usama M., eds. Proceedings of the Second International Conference on Knowledge Discovery and Data Mining (KDD-96). AAAI Press. pp. 226-231. ISBN 1-57735-004-9.
