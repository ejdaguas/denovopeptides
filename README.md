
Rational Design of de novo CCL2 Binding Peptides<br>

Contact: Erika D. Aguas, ejdaguas@gmail.com<br>
Rutgers University Dept of Biomedical Engineering<br>

Descriptions of all files are listed below. <br>
\* refers to the four-character peptide code:<br>
aea2 = AEAPSDKLEVE, αCCL-2 <br>
wkn2 = WKNFQTI<br>
ydap = YDAPSLKFQVE, αCCL-3<br>
ygap = YGAPCHKFDVK, αCCL-1<br>
<br>
---INPUT FILES--- <br>
contacts_\*.txt	&emsp;	CPPTRAJ script for intermolecular contacts analysis<br>
hbond_\*.ptraj	&emsp;	CPPTRAJ script for H-bond analysis<br>
MMPBSA.in	&emsp;	Input file to MMPBSA.py, see notes<br>
pcascript_\*.ptraj	&emsp;CPPTRAJ script for PCA<br>
process_mdout.perl	&emsp;PERL script to process output MD files<br>
rmsd_\*.in	&emsp;	CPPTRAJ script for RMSD analysis<br>
\*_cpx.prmtop		&emsp;Amber trajectory of complex alone, for MMPBSA<br>
\*_lig.prmtop	&emsp;	Amber trajectory of ligand/peptide alone, for MMPBSA<br>
\*_rec.prmtop	&emsp;	Amber trajectory of receptor/CCL2 alone, for MMPBSA<br>
\*_sol.pdb	&emsp;	PDB of complex in solution<br>
\*_sol.prmtop	&emsp;	Amber PARM of complex in solution<br>
\*_sol.crd&emsp;		Amber trajectory of complex in solution<br>
<br>
---OUTPUT FILES---<br>
--PCA--<br>
\*_pca.vmd &emsp;	VMD visualization file of PCA <br>
\*-modeX.nc&emsp;	NetCDF file with PCA eigenvector X<br>
\*_nmwiz.nmd &emsp;	PCA file to be used with NMWiz in VMD<br>
<br>
--H-BONDS and CONTACTS--<br>
avgbfactor_\*.txt	&emsp;	Chimera output of average B-factor per-residue<br>
\*_contacts.pyc	&emsp;	Chimera map of intermolecular contacts<br>
\*_hbond4.dat	&emsp;	List of # of H-bonds per frame<br>
\*-all-residues-nn4.dat	&emsp;List of # of intermolecular contacts per frame<br>
\*-nn-contacts4.dat	&emsp;List of most common intermolecular contacts<br>
<br>
--MMPBSA--<br>
mmpbsa_\*_10frames.out&emsp;	Output of MMPBSA script, see notes<br>
<br>
--RMSD--<br>
rmsd_\*.dat	&emsp;Output from CPPTRAJ rmsd_\*.in<br>
<br>
---NOTES---<br>
MMPBSA analysis is performed using the following command (example for AEA2):<br>
$AMBERHOME/bin/MMPBSA.py -O -i mmpbsa_aea2.in -o mmpbsa_aea2.out -sp aea2_sol.prmtop -cp aea2_cpx.prmtop -rp aea2_rec.prmtop -lp aea2_lig.prmtop -y aea2_eq3_2.nc
