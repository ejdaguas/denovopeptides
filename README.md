Rational Design of de novo CCL2 Binding Peptides

Contact: Erika D. Aguas, ejdaguas@gmail.com
Rutgers University Dept of Biomedical Engineering

Descriptions of all files are listed below. * refers to the four-character peptide code:
aea2 = AEAPSDKLEVE, αCCL-2 
wkn2 = WKNFQTI
ydap = YDAPSLKFQVE, αCCL-3
ygap = YGAPCHKFDVK, αCCL-1

---INPUT FILES---
contacts_*.txt		CPPTRAJ script for intermolecular contacts analysis
hbond_*.ptraj		CPPTRAJ script for H-bond analysis
MMPBSA.in		Input file to MMPBSA.py, see notes
pcascript_*.ptraj	CPPTRAJ script for PCA
process_mdout.perl	PERL script to process output MD files
rmsd_*.in		CPPTRAJ script for RMSD analysis
*_cpx.prmtop		Amber trajectory of complex alone, for MMPBSA
*_lig.prmtop		Amber trajectory of ligand/peptide alone, for MMPBSA
*_rec.prmtop		Amber trajectory of receptor/CCL2 alone, for MMPBSA
*_sol.pdb		PDB of complex in solution
*_sol.prmtop		Amber PARM of complex in solution
*_sol.crd		Amber trajectory of complex in solution

---OUTPUT FILES---
--PCA--
*_pca.vmd 	VMD visualization file of PCA 
*-modeX.nc	NetCDF file with PCA eigenvector X
*_nmwiz.nmd	PCA file to be used with NMWiz in VMD

--H-BONDS and CONTACTS--
avgbfactor_*.txt		Chimera output of average B-factor per-residue
*_contacts.pyc		Chimera map of intermolecular contacts
*_hbond4.dat		List of # of H-bonds per frame
*-all-residues-nn4.dat	List of # of intermolecular contacts per frame
*-nn-contacts4.dat	List of most common intermolecular contacts

--MMPBSA--
mmpbsa_*_10frames.out	Output of MMPBSA script, see notes

--RMSD--
rmsd_*.dat	Output from CPPTRAJ rmsd_*.in

---NOTES---
MMPBSA analysis is performed using the following command (example for AEA2):
$AMBERHOME/bin/MMPBSA.py -O -i mmpbsa_aea2.in -o mmpbsa_aea2.out -sp aea2_sol.prmtop -cp aea2_cpx.prmtop -rp aea2_rec.prmtop -lp aea2_lig.prmtop -y aea2_eq3_2.nc
