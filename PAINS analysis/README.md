PAINS (Pan-Assay INterference compoundS) analysis

![image](https://user-images.githubusercontent.com/83068588/175040431-fbf09679-7b4c-4b36-837c-ff62dfba377e.png)

This folder contains the protocol code in Scipion and the associated script. The script is adapted from the code provided by Volkamer Lab[1] and the code used for filtering by personal catalogue comes from https://github.com/iwatobipen/rdkit_pains.

PAINS are compounds that frequently show erroneous results (false positives) in high-throughput screening (HTS). This is a consequence of the functional groups they contain which cause non-specific binding to a wide range of targets.

The improved script make possible to choose between the predefined PAINS catalogue offered by the RDKit library or to use a catalogue provided by the user (example uploaded in the folder). This user supplied file must be structured as follows: on each line, the first position is reserved for the PAINS molecule in SMART format, and the second position for the PAINS name, both elements must be space separated.

As required input file we found a extension mol, mol2, pdb or sdf file to analyze, converted to a SetOfSmallMolecules object. The protocol GUI requests the user either to have his own PAINS catalogue or to use the RDKit one. In case the user already has this file, the GUI will show a field to enter the catalogue absolute path. 

As output archives, there are two files with txt extension and two SetOfSmallMolecules objects, one of them will contain those molecules where no match has been found with any of the PAINS in the catalogue; the other one, those molecules that have at least one match. The matching PAINS will be registered in the SetOfSmallMolecules in the form of an attribute for each molecule. Therefore, the user will be able to analyze any molecules that have not passed the filter through a viewer attached to SetOfSmallMolecules objects which displays a table with the attributes for each molecule in the set.
