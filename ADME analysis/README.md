Qualitative evaluation of pharmacokinetic properties

This folder contains the protocol code of Scipion and the associated script. The script is adapted from the code provided by Volkamer Lab[1] and another source code form oddt github (https://oddt.readthedocs.io/en/latest/_modules/oddt/virtualscreening.html).

Pharmacokinetic properties give a notion of whether the analyzed compounds can fulfil their function as a drug when they are ingested by humans. This analysis is done using an empirical rule known as Lipinski's rule of five (Ro5) as it was developed to estimate the bioavailability of a compound solely based on its chemical structure. The most important pharmacokinetic properties (in the human body) are Absorption, Distribution, Metabolism and Excretion (ADME). 

![image](https://user-images.githubusercontent.com/83068588/175049326-a4809cb2-c590-479e-a8e6-a6cb49417568.png)

This filtering is particularly useful for testing compounds whose pharmacological properties/activity have already been proven.
The Ro5 dictates that for a compound to be orally administered it can only fail to meet one of the Lipinski rules, there are variants of the standard that include new rules that do not require the complete fulfillment of them by the compound. However, in this paper only the original Ro5 rules will be considered. The compound must: 
-	Contain no more than 5 hydrogen bond donors (the total number of nitrogen–hydrogen and oxygen–hydrogen bonds).

-	Contain no more than 10 hydrogen bond acceptors (all nitrogen or oxygen atoms).

-	Have a molecular mass of 160 or less than 500 Da, as large molecules (high molecular weight) might have more difficulties in passing phospholipid membranes.

-	Not exceed 5 in its octanol-water partition coefficient (log P). This coefficient measures the distribution of a compound, usually between a hydrophobic (e.g. 1-octanol) and a hydrophilic (e.g. water) phase.

The script offers the user the possibility of filtering a set of compounds by the rule Lipinski's rule and the Rule of 3 (Ro3). This new rule has the same statements as the Ro5, the difference between them is that the values that define whether a compound satisfies the rule are multiples of 3 and not of 5, in the case of Ro3:
-	Contain no more than 3 hydrogen bond donors (the total number of nitrogen–hydrogen and oxygen–hydrogen bonds).

-	Contain no more than 3 hydrogen bond acceptors (all nitrogen or oxygen atoms).

-	Have a molecular mass of 160 or less than 300 Da, as large molecules (high molecular weight) might have more difficulties in passing phospholipid membranes.

-	Not exceed 3 in its octanol-water partition coefficient (log P). This coefficient measures the distribution of a compound, usually between a hydrophobic (e.g. 1-octanol) and a hydrophilic (e.g. water) phase.


The protocol accepts as input a SetOfSmallMolecules Scipion object, which can be taken from a smi, mol, mol2, pdb or sdf file and the result of the process are those molecules that have successfully passed the chosen filter in a new SetOfSmallMolecules object.

No additional installation is required apart from Scipion-chem's own installation, all the necessary software to use the protocol is installed and launched with Scipion-chem.


[1]T002 · Molecular filtering: ADME and lead-likeness criteria. (s/f). Volkamerlab.Org. Recuperado el 22 de junio de 2022, de https://projects.volkamerlab.org/teachopencadd/talktorials/T002_compound_adme.html

