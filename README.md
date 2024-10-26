A biotechnologist by training, aspiring Computational biologist and Al/ML enthusiast.

This is my project for masters dissertation: 
Understanding the antimicrobial resistance mechanism of alanine racemase in Mycobacterium tuberculosis against Cycloserine.

Step 1:
Prediction of mutant Protein structure by ColabFold with follwing configuration. (https://github.com/sokrypton/ColabFold)
"msa_mode": "mmseqs2_uniref_env"
"model_type": "alphafold2_multimer_v3"
PDB file will be generated along with the PAE and pLDDT scores to check the accuracy of structure by model. 
The predicted stcture is Amber Relaxed to refine protein structures. By minimizing the energy of a protein model, researchers can achieve more accurate and stable conformations, which are crucial for subsequent molecular dynamics simulations.

Step 2:
DynamicBind Webserver: https://github.com/luwei0917/DynamicBind
the predicted structure is used for molecular docking by the DynamicBind tool. It predicts ligand-specific protein-ligand complex structure with a deep equivariant generative model
The canonical smiles of the ligand along with protein is uploaded to get the protein-ligand complex.
Affinity Score, Binding Pose, Binding Center, Pose Score along with the pdb of complex is generated. 


Step 3: CHARMM input generator for the GROMACS to create topology and parameter files for protein structure and ligand by CgenFF. 
https://charmm-gui.org/. The output was according to GROMACS compatible type with correct forcefield.
energy minimization until the maximum force was below 1000 kJ/mol. 
NVT. For pressure coupling, the C-rescale was used along with an isotropic
pressure coupling type. equilibration was carried out for 200 ps at a temperature of 303.15 K, using V-rescale for
temperature coupling. NPT equilibration was also carried out for 200 ps at a temperature
of 303.15 K. For long-range van der Waals energies, a cutoff of 1.2 nm was
applied, and the particle mesh Ewald technique was used for calculating electrostatic
interactions

Step 4: 
Analysis of trajectory

All the notebooks used are in Notebook folder for reference. 

The codes in this project were already present in some GitHub pages, i integrated those GitHub pages with some my tweeks to create a Workflow from Protein Prediction to molecular dynamics simulation.

Acknowledgement and references: 

Mirdita M, Schütze K, Moriwaki Y, Heo L, Ovchinnikov S and Steinegger M. ColabFold: Making protein folding accessible to all.Nature Methods (2022) doi: 10.1038/s41592-022-01488-1
https://github.com/sokrypton/ColabFold

Lu, W., Zhang, J., Huang, W. et al. DynamicBind: predicting ligand-specific protein-ligand complex structure with a deep equivariant generative model. Nat Commun 15, 1071 (2024). https://doi.org/10.1038/s41467-024-45461-2

User friendly molecular dynamics simulation combining GROMACS and Google Colab: A complete guide
https://github.com/paulshamrat/ColabMDA


Jo S, Kim T, Iyer VG, Im W. CHARMM-GUI: a web-based graphical user interface for CHARMM. J Comput Chem. 2008 Aug;29(11):1859-65. doi: 10.1002/jcc.20945. PMID: 18351591.

My sincere apologies for using your repositories for my work without permission.
