Compound data acquisition

This folder contains the protocol code of Scipion and the associated script. The script is adapted from the code provided by Volkamer Lab[1].

The first workflow protocol aims to obtain an initial set of compounds that present bioactivity recorded in ChEMBL against a target molecule. It is therefore recommended for cases where the user does not have a starting set of ligands to analyze.
The result of the protocol is the import of the obtained molecules, in SMILES format, into a SetOfSmallMolecules Scipion object, this import is key so that the molecules of the set can be used in the following protocols.


The protocol filters the compounds according to the following parameters:
-	Uniprot ID: Uniprot code of the target molecule.

-	Assay type: ChEMBL includes six different types of assays, “biological assays are experimental methods for assessing the presence, localization, or biological activity of a substance in living cells and biological matrices”:

a)	Binding (B): it is based on the binding of ligand molecules to receptors, antibodies, or other macromolecules. This type of assays obtain data for measuring binding of compound to a molecular target, e.g.  Ki, IC50, Kd.

b)	Functional (F): a set of systematic in vivo experiments designed to measure the effect or biological role of a compound in a cellular pathway or biological process, e.g., cell death in a cell line.

c)	ADMET (A): assays related to the pharmacokinetic characteristics of a compound e.g., t1/2, oral bioavailability.

d)	Toxicity (T): Data measuring toxicity of a compound, e.g., cytotoxicity.

e)	Physicochemical (P): this type of assay is performed in the absence of biological material and measures physicochemical properties of the compounds e.g., chemical stability, solubility.

f)	Unclassified (U): those assays which cannot be included in the rest of type are classified into one of the above categories e.g., ratio of binding vs efficacy.

In case that the chosen assay type is Binding, which is recommended, the next parameter is the Bioactivity measure. 

-	Bioactivity measure:
 
a)	IC50: (Half maximal inhibitory concentration) indicates the required concentration of a compound to inhibit a biological process by 50%. The lower the IC50 value, the higher the compound bioactivity. 

b)	EC50: (Half maximal effective concentration) is the drug concentration required to produce half (50%) of the maximum effect of that compound. The lower the EC50 value, the higher the compound bioactivity. EC50 is equivalent to IC50, but this last is used in the case of working with inhibitors.

c)	Kd: dissociation constant, this term is generic and describes the binding affinity between a molecule and an enzyme or a receptor. 

d)	Ki: inhibition constant, the term is equivalent to the dissociation constant (Kd), but it is used when the molecule for which bioactivity is measured is an inhibitor.

-	Target type: it is highly advisable that the chosen target type is "SINGLE PROTEIN", as the aim of the LVBS is to find compounds that have activity on a single target. Although it is possible to choose between other options.

Organism of compound origin: it is recommended to choose human proteins; since the ultimate goal is to obtain possible molecules to be used as human drugs.


[1] T001 · Compound data acquisition (ChEMBL). (s/f). Volkamerlab.Org. Recuperado el 22 de junio de 2022, de https://projects.volkamerlab.org/teachopencadd/talktorials/T001_query_chembl.html

