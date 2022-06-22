3D molecular structure comparison

This folder contains the protocol code of Scipion and its associated script. Software tools for this protocol belong to the RDKit module rdkit.Chem.rdMolAlign module[1]. 

The goal of this analysis is to use the shape of the query molecule/ligand in the search for similar structures. 
The methods applied in the shape filtering are usually based on the calculation of distances, surface areas and/or volumes.

![image](https://user-images.githubusercontent.com/83068588/175064994-6df51e74-933d-4dfb-8530-4b70653e6ebe.png)


The similarity values that can be calculated using the script are: 

- A commonly used measure for comparing the structure of two molecules in virtual screening programs is the calculation of the Root Mean Square Deviation (RMSD) between the atoms of two molecules. The RMSD is a distance which describes the structural difference between two topologies. The lower the RMSD between two structures, the greater the similarity between them.

- Protrude Distance focusses on the volume mismatch and is defined as the percentage of the larger molecule which protrudes/exceeds from the smaller molecule. 

- Tanimoto Distance measures similarity between finite sample sets and is defined as the size of the intersection divided by the size of the union of the sample sets!


The protocol allows you to choose which coefficient you want to calculate and requires as input a SetOfSmallMolecules Scipion object which oly can be produced by a smi extension file. 

Analysis result will be another SetOfSmallMolecules object with those molecules that have obtained a coefficient range specified by the user in the protocol GUI.
Before the calculation of RMSD and the Tanimoto and Protrude distances, it is necessary to superimpose the structures which are to be compared. So far RDKit does not have a tool that performs an alignment prior to the calculation of similarity, so the results provided by these tools must be carefully analyzed by users.


No additional installation is required apart from Scipion-chem's own installation, all the necessary software to use the protocol is installed and launched with Scipion-chem.

[1]rdkit.Chem.rdMolAlign module — The RDKit 2022.03.1 documentation. (s/f). Rdkit.org. Recuperado el 22 de junio de 2022, de https://www.rdkit.org/docs/source/rdkit.Chem.rdMolAlign.html

