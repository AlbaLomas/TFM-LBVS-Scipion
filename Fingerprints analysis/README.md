Fingerprint analysis protocol explores molecular 2D descriptors.
This folder contains the protocol code in Scipion and the associated script. The script is adapted from the code provided by Volkamer Lab[1].  

Fingerprints are computational representations of molecules encoding chemical and molecular features in the form of 0 (absence of the feature) and 1 (presence of the feature).
This protocol offer two different types of fingerprints for calculate: MACCS and Morgan.

The similarity between fingerprints is measured by different similarity coefficients, Tanimoto and Dice coefficients are the chosen ones. 

- Tanimoto coefficient: it is the most popular in both chemical informatics and computational medicinal chemistry because of its ease of implementation and quickness [33].![image](https://user-images.githubusercontent.com/83068588/175019284-b0db6768-3af5-410a-a62a-5e38bae91185.png)


The protocol result is a SetOfSmallMolecules object (Scipion) that would contain those molecules that obtain a similarity result with the molecule used as target equal to or higher than the one set by the user using the type of fingerprint and similarity index specified in the protocol GUI.

The protocol requires a file with extension mol, mol2, pdb, sdf or smi and a target molecule in SMILES format, in case the target is not in the analyzed set. 

No additional installation is required apart from Scipion-chem's own installation, all the necessary software to use the protocol is installed and launched with Scipion-chem.

[1]T004 · Ligand-based screening: compound similarity. (s/f). Volkamerlab.Org. Recuperado el 22 de junio de 2022, de https://projects.volkamerlab.org/teachopencadd/talktorials/T004_compound_similarity.html

