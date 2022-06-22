PDB access and ligand extraction

<img width="180" alt="image" src="https://user-images.githubusercontent.com/83068588/175131200-7e794edb-802e-4812-8e22-f86610852590.png">

This folder contains the protocol code of Scipion and the associated script. The script is adapted from the code provided by Volkamer Lab[1]. 
Aditionally, it presents some modifications in order to automatizate the process. This improvement facilitates the calculation of the centers of mass of the different extracted ligands and their subsequent clustering thanks to the DBSCAN algorithm[2] implemented by scikit-learn package.


Protein Data Bank (PDB) is a public and supervised (Worldwide Protein Data Bank) database that stores the three-dimensional (3D) structure of different nucleic acids and proteins. 
These structures are provided by different biologists and biochemists from all over the world who obtain them through different techniques such as magnetic/nuclear resonance, X-ray crystallography or electron microscopy [46].![image](https://user-images.githubusercontent.com/83068588/175132836-6eb79bf5-94f2-42d3-9e98-b7a196f4a819.png)


The output of the protocol is the generation of different SetOfSmallMolecules objects that will be made up by the ligands that have been grouped in the same cluster; in other words, there will be as many sets as clusters are obtained. 
Moreover, each molecule includes its canonical SMILES and the structure of its target protein as attributes, so that the binding site can be visualized and allows the user to check the clustering performed by the script.


[1] T008 · Protein data acquisition: Protein Data Bank (PDB). (s/f). Volkamerlab.Org. Recuperado el 22 de junio de 2022, de https://projects.volkamerlab.org/teachopencadd/talktorials/T008_query_pdb.html
[2]Ester, Martin; Kriegel, Hans-Peter; Sander, Jörg; Xu, Xiaowei (1996). «A density-based algorithm for discovering clusters in large spatial databases with noise». En Simoudis, Evangelos; Han, Jiawei; Fayyad, Usama M., eds. Proceedings of the Second International Conference on Knowledge Discovery and Data Mining (KDD-96). AAAI Press. pp. 226-231. ISBN 1-57735-004-9.
