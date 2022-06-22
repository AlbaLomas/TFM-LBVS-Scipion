Compound data acquisition

![image](https://user-images.githubusercontent.com/83068588/175167107-ddd5e7d5-233c-4893-938c-1204a3218f7e.png)


This folder contains the protocol code of Scipion and the associated script. The script is adapted from the code provided by Volkamer Lab [1].

The first workflow protocol aims to obtain an initial set of compounds that present bioactivity recorded in ChEMBL against a target molecule. It is therefore recommended for cases where the user does not have a starting set of ligands to analyze.Programmatic access is provided by a Python library called ChEMBL webresource client [2].

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

- Organism of compound origin: it is recommended to choose human proteins; since the ultimate goal is to obtain possible molecules to be used as human drugs.


The user will specify the search according to these parameters using the GUI of the protocol. In cases where the type of assay chosen is a Binding assay, the script undertakes the following steps: firstly, it retrieves the ChEMBL ID of the compound with the highest affinity on the target; then, it obtains the bioactivity data of the affine compound similar molecules and filters them according to assay type, bioactivity measure, target type and organism of compound origin fields. 
Next, for those molecules that have passed the screening, their structure is obtained in form of "canonical SMILES". After collecting the bioactivity and structural data for each molecule, the filter is performed according to the average bioactivity chosen. The adapted script is able to sort the obtained molecules in bioactivity ascending order independently of the chosen bioactivity measure.

In all other cases the search is limited to filtering without screening for bioactivity. 

The result of the protocol is a number of compounds, also determined by the user, that show activity against the target and have the highest bioactivity levels. If the user wants to obtain ALL compounds, the box corresponding to the final number of compounds must be left blank.


[1] T001 · Compound data acquisition (ChEMBL). (s/f). Volkamerlab.Org. Recuperado el 22 de junio de 2022, de https://projects.volkamerlab.org/teachopencadd/talktorials/T001_query_chembl.html

[2]Davies, M., Nowotka, M., Papadatos, G., Dedman, N., Gaulton, A., Atkinson, F., Bellis, L., & Overington, J. P. (2015). ChEMBL web services: streamlining access to drug discovery data and utilities. Nucleic Acids Research, 43(W1), W612-20. https://doi.org/10.1093/nar/gkv352![image](https://user-images.githubusercontent.com/83068588/175167817-f6972cf9-7804-4caa-90c3-10dace6b5f4f.png)

