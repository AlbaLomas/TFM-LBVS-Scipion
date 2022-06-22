Consensus pharmacophore generation and pharmacophore-based screening

<img width="285" alt="image" src="https://user-images.githubusercontent.com/83068588/175142526-f09a8552-8cd9-4b1d-84cd-1c5a88dcf7a8.png">

This folder contains the protocol code of Scipion and the associated script. The script is adapted from the code provided by Volkamer Lab[1]

The first part of the process involves the generation of the consensus pharmacophore from the ligands extracted in the previous protocol. 
Each ligand has different pharmacophore characteristics that are divided into the following families: donor, acceptor, aromatic, hydrophobe, lumpedhydrophobe, posionizable. 
The characteristics are obtained by RDKit “GetFeatureDefs()” function and classified into the above-mentioned families with “GetFamily()” function.
Up to this point, the script obtains different clusters, each of them represents one of the families and contains all the family characteristics of all the ligands examined.
Then the coordinates of the pharmacophore characteristics for each feature type are extracted by “GetPos()” function. These coordinates are represented in a 3D space, so each one has three points in a [x,y,z] form. 
Now it is necessary to re-cluster these coordinates using the k-means algorithm, needless to say, the coordinates of each feature are grouped separately. ![image](https://user-images.githubusercontent.com/83068588/175143740-81bbd4f4-e257-40a8-8dcd-ded70dc68546.png)


[1] T009 · ligand-based pharmacophores. (s/f). Volkamerlab.Org. Recuperado el 22 de junio de 2022, de https://projects.volkamerlab.org/teachopencadd/talktorials/T009_compound_ensemble_pharmacophores.html

