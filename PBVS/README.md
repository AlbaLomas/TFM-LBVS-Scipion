Consensus pharmacophore generation and pharmacophore-based screening


<img width="1031" alt="image" src="https://user-images.githubusercontent.com/83068588/175160330-6bda04bb-8b71-4f21-bfbc-f84b5527c61e.png">

This folder contains the protocol code of Scipion and the associated script. The script is adapted from the code provided by Volkamer Lab[1], and the second part of the protocol, Pharmacophore based Virtual Screening (PBVS) is performed using the tools provided by RDKit on https://github.com/rdkit/UGM_2016/blob/master/Notebooks/Stiefl_RDKitPh4FullPublication.ipynb.

The first part of the process involves the generation of the consensus pharmacophore from the ligands extracted in the previous protocol. 
Each ligand has different pharmacophore characteristics that are divided into the following families: donor, acceptor, aromatic, hydrophobe, lumpedhydrophobe, posionizable. 
The script obtains different clusters, each of them represents one of the families and contains all the family characteristics of all the ligands examined.
Then the coordinates of the pharmacophore characteristics for each feature type are extracted. These coordinates are represented in a 3D space, so each one has three points in a [x,y,z] form. 
Now it is necessary to re-cluster these coordinates using the k-means algorithm, needless to say, the coordinates of each feature are grouped separately. 

K-means clusteringrequires the following parameters:
-	kq: determines the number of clusters (k) per feature type

-	K: number of clusters (number of features/kq)

-	Minimum cluster size: minimum number of features that a cluster must have to be taken into account by the algorithm, it is intended that the clusters contain features of most of the molecules in our set of ligands. 

-	Top cluster number: number of clusters to be selected, the largest ones.

![image](https://user-images.githubusercontent.com/83068588/175160182-88de5f21-0e98-4c4b-918a-f6d906e8215d.png)


It must be mentioned that kq should take a value that assures for all family features at least one cluster, but no more than 5 clusters.

The next step is the selection of clusters from a k-means clustering. It returns the indices of these clusters; the selection is based on cluster size: the largest clusters are chosen. 
After this step, it retrieves cluster center coordinates for selected clusters. The coordinates will finally be the consensus pharmacophore within the starting ligands.

Once the coordinates corresponding to the consensus pharmacophore are available, the last step of the protocol is filtering by this pharmacophore.
The starting molecules are analyzed for their pharmacophore characteristics, and these are compared with the characteristics of the consensus pharmacophore. In other words, thanks to the RDKit package, the pharmacophoric characteristics of analyzed molecules are extracted per family and compared family by family with those for which the consensus pharmacophore has been constructed.


The inputs required by this protocol are two SetOfSmallMolecules objects, one of them containing the ligands which will build the pharmacophore (for example, those obtained in the programmatic access, or provided by the user in the form of PDB files); and another one containing the molecules that must match to the built pharmacophore. The output is a new object SetOfSmallMolecules containing only those molecules that have passed the filtering.



[1] T009 · ligand-based pharmacophores. (s/f). Volkamerlab.Org. Recuperado el 22 de junio de 2022, de https://projects.volkamerlab.org/teachopencadd/talktorials/T009_compound_ensemble_pharmacophores.html

