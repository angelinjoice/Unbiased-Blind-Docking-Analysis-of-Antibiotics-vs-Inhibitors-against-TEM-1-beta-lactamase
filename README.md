# Unbiased Blind Docking Analysis of beta-Lactam Antibiotics vs. Mechanism-Based Inhibitors against TEM-1 Beta-Lactamase


Unbiased blind molecular docking protocol and interaction analysis of Ampicillin, Amoxicillin, Tazobactam, Sulbactam, and Clavulanic Acid against TEM-1 Beta-Lactamase (PDB: 1ZG4).

---

## 🛠️ Protocol & Workflow

1. **Fetch Receptor Structure (PDB: 1ZG4)**  
   *Download TEM-1 β-lactamase from RCSB PDB to acquire high-resolution 3D coordinates of the target protein.*

2. **Fetch Ligand Structures (PubChem)**  
   *Download 2D SDF files for all 5 compounds from PubChem to obtain initial molecular chemical structures.*

3. **Receptor Preparation & Cleanup**  
   *Delete water molecules and add polar hydrogens in BIOVIA Discovery Studio to eliminate physical obstruction and simulate physiological protonation states.*

4. **Format Standardization**  
   *Save protein and ligands into standard PDB format to ensure seamless input compatibility across screening tools.*

5. **Ligand Minimization & PDBQT Conversion**  
   *Run Universal Force Field (UFF) energy minimization in PyRx and convert to PDBQT format to remove steric strain and define torsional root trees.*

6. **Global Grid Box Setup**  
   *Enclose the entire protein surface inside a global search box within PyRx to enable unbiased blind docking across all potential binding sites.*

7. **AutoDock Vina Docking Execution**  
   *Run Vina simulation routines to search ligand binding conformations and compute predicted binding free energy (kcal/mol).*

8. **Top-Pose Extraction**  
   *Export Model 1 (the lowest energy pose) for each docked ligand as a PDB file to isolate optimal binding configurations.*

9. **Protein-Ligand Complex Reconstruction**  
   *Merge each top ligand pose back into the prepared receptor structure within Discovery Studio to reconstruct accurate 3D interaction complexes.*

10. **Non-Covalent Interaction Analysis**  
    *Generate 2D non-bonded interaction maps to identify critical hydrogen bonds, measure atomic distances, and verify engagement with catalytic active-site residues like Ser70.*

---

## 📊 Summary Results

| Ligand | Category | Binding Affinity ($\text{kcal/mol}$) | Total H-Bonds | Key Residues Engaged |
| :--- | :--- | :---: | :---: | :--- |
| **Ampicillin** | β-Lactam Antibiotic | **-8.2** | 7 | Ser70, Ser130, Arg244, Ser235, Val216, Glu166 |
| **Tazobactam** | β-Lactamase Inhibitor | **-7.5** | 9 | Ser70, Asn132, Asn170, Ala237, Ser235 |
| **Amoxicillin** | β-Lactam Antibiotic | **-7.3** | 4 | Lys73, Ser130, Asn170 |
| **Sulbactam** | β-Lactamase Inhibitor | **-6.9** | 2 | Ala237, Arg244 |
| **Clavulanic Acid** | β-Lactamase Inhibitor | **-6.4** | 3 | Ser70, Asn132, Lys234 |

---

## 🔬 Key Insights

* **Top Antibiotic:** Ampicillin achieved the highest overall binding affinity (ΔG = -8.2 kcal/mol), stabilized by an extensive 7-hydrogen-bond network.
* **Top Inhibitor:** Tazobactam proved to be the most potent inhibitor (ΔG = -7.5 kcal/mol), establishing 9 total hydrogen bonds across the binding pocket.
* **Catalytic Engagement:** All 5 compounds successfully targeted the primary active pocket of TEM-1 β-lactamase, directly interacting with essential catalytic residues including **Ser70**, **Ser130**, and **Arg244**.
