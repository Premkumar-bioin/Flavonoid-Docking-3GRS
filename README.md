![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![RDKit](https://img.shields.io/badge/RDKit-Cheminformatics-green)
![AutoDock Vina](https://img.shields.io/badge/AutoDock%20Vina-Docking-orange)
![OpenBabel](https://img.shields.io/badge/OpenBabel-Converter-yellow)
![Google Colab](https://img.shields.io/badge/Google%20Colab-Notebook-red?logo=googlecolab)
![License](https://img.shields.io/badge/License-MIT-lightgrey)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)


# 🧬 Targeted Computational Docking of Flavonoids Against Glutathione Reductase (3GRS)

---

## 📌 Project Overview

This project performs a **targeted molecular docking analysis** of selected flavonoids (**Naringin, Naringenin, Quercetin, Kaempferol, and Luteolin**) against **Human Glutathione Reductase (PDB ID: 3GRS)** using a fully automated **Google Colab-based pipeline**.

The workflow is designed to investigate how structural features of flavonoids influence their binding within the **catalytic redox-active site**, which plays a critical role in oxidative stress regulation associated with **Inflammatory Bowel Disease (IBD)**.

---

## 🔬 Scientific Rationale

Glutathione reductase (GR) maintains cellular redox balance by regenerating reduced glutathione (GSH).  
Disruption of this system contributes to oxidative stress observed in inflammatory conditions such as IBD.

This study aims to:

- Evaluate binding affinity of flavonoids at the **catalytic cysteine site (Cys58, Cys63)**  
- Compare **aglycones vs glycosylated flavonoids**  
- Understand structure–activity relationships (SAR)  
- Support prior **zebrafish IBD model findings**

---

## ⚙️ Computational Workflow (Code-Driven)

### 🔹 1. Environment Setup

- Installed tools:
  - OpenBabel  
  - AutoDock Vina  
  - RDKit  
  - Meeko  
  - py3Dmol  
  - Pandas  

---

### 🔹 2. Protein Preparation

- Structure: **3GRS (RCSB PDB)**
- Steps:
  - Removed water and heteroatoms  
  - Retained only protein atoms  
  - Protonation at **physiological pH (7.4)**  
  - Gasteiger charge assignment  
  - Converted to **PDBQT format**

---

### 🔹 3. Ligand Preparation

- SMILES → 3D structures using RDKit  
- Hydrogen addition  
- Geometry optimization (MMFF)  
- Conversion to docking format using Meeko  

---

### 🔹 4. Targeted Docking Setup

Docking was performed specifically at the **catalytic active site**:

- **Target residues:** Cys58, Cys63  
- Grid center:
x = 65.022
y = 46.284
z = 15.613
- Grid size:
22 × 22 × 22 Å
- Exhaustiveness: **32 (high precision search)**

---

### 🔹 5. Molecular Docking

- Tool: AutoDock Vina  
- Batch docking of all ligands  
- Best binding pose extracted from each run  
- Binding energies parsed from log files

---

### 🔹 6. Visualization

- Interactive 3D visualization using **py3Dmol**  
- Ligand displayed within protein structure  
- Docking grid box visualized  
- Binding pose inspection enabled

---

## 📊 Results

### 🧪 Docking Scores (kcal/mol)

| Ligand | Binding Energy |
|--------|--------------|
| Luteolin | ~ -8.6 |
| Quercetin | ~ -8.6 |
| Kaempferol | ~ -8.4 |
| Naringenin | ~ -8.0 |
| Naringin | ~ -7.6 |

---

## 🔍 Key Observations

### 🥇 1. Lead Compounds
- **Luteolin and Quercetin showed strongest binding affinity**
- Efficient accommodation within catalytic pocket

---

### 🧪 2. Structure–Activity Relationship (SAR)

| Feature | Effect on Binding |
|--------|------------------|
| Increased hydroxyl groups | Enhances H-bonding |
| Planarity | Improves pocket fitting |
| Glycosylation (Naringin) | Reduces binding efficiency |

---

### ⚠️ 3. Naringin Behavior

**Naringin showed weaker binding affinity (~ -7.66 kcal/mol)** due to:

- High molecular weight  
- Steric hindrance from sugar moiety  
- Reduced ability to penetrate catalytic pocket  

👉 Supports hypothesis:
> Naringin likely acts as a **prodrug**, requiring conversion to Naringenin for effective interaction.

---
<img width="1023" height="614" alt="Screenshot 2026-04-24 112600" src="https://github.com/user-attachments/assets/46f68c38-c9b5-4db6-8398-f5679c9e18b2" />
<img width="1308" height="537" alt="Screenshot 2026-04-24 112535" src="https://github.com/user-attachments/assets/97052857-6371-497d-a461-953787e73d5a" />
<img width="849" height="201" alt="Screenshot 2026-04-24 112441" src="https://github.com/user-attachments/assets/09dea86a-4452-41d9-bb58-4e1cbcfc3e13" />

### 💊 4. ADMET Insights

| Compound | Drug-likeness |
|----------|--------------|
| Luteolin | ✅ |
| Quercetin | ✅ |
| Kaempferol | ✅ |
| Naringenin | ✅ |
| Naringin | ❌ (Lipinski violations) |

---

## 🖼️ Visualization — Binding Interactions

<img width="1919" height="752" alt="Screenshot 2026-04-24 100150" src="https://github.com/user-attachments/assets/84337257-5baa-49ad-9988-f49e1d447d54" />
<img width="1919" height="752" alt="Screenshot 2026-04-24 100109" src="https://github.com/user-attachments/assets/c0dff68c-fb16-4e7f-b180-8080d6c99f39" />
<img width="1465" height="563" alt="Screenshot 2026-04-24 100047" src="https://github.com/user-attachments/assets/50d85ae5-0fa9-4f11-8a19-5ff7fa5b5c44" />
<img width="1618" height="625" alt="Screenshot 2026-04-24 100011" src="https://github.com/user-attachments/assets/7f0de25d-4347-473d-8acd-21ade3dff528" />
<img width="909" height="440" alt="Screenshot 2026-04-24 095946" src="https://github.com/user-attachments/assets/e4201720-4712-4d26-be5f-3d25c6013e01" />
<img width="731" height="493" alt="Screenshot 2026-04-24 095905" src="https://github.com/user-attachments/assets/7038b8db-d985-4431-93d8-f530ef6d3ff3" />
<img width="831" height="480" alt="Screenshot 2026-04-24 095850" src="https://github.com/user-attachments/assets/1ed00fa0-96d2-43a5-8453-85314df00113" />

## 📂 Repository Structure
* `Final_drug_discovery_report.csv`: Contains binding affinities (kcal/mol), RMSD values, and ADMET Lipinski violations.
* `colab_.ipynb`: The complete Google Colab pipeline from protein preparation to interaction analysis.


---

## 🧠 Key Insights

- Flavonoid **aglycones outperform glycosides** in enzyme binding  
- Structural features strongly influence docking outcomes  
- Computational results align with known antioxidant activity trends  
- Supports mechanistic explanation for zebrafish experimental observations  

---

## 🚀 Project Significance

This study bridges:
- Computational drug discovery (CADD)  
- Natural product chemistry  
- Experimental zebrafish models  

It demonstrates how in silico approaches can:
- Predict molecular interactions  
- Support biological hypotheses  
- Guide future experimental validation  

---

## ⚠️ Limitations

- Docking does not account for full protein flexibility  
- Solvent effects are approximated  
- Requires experimental validation (in vitro/in vivo)  

---

## 🛠️ Tools & Technologies

- Python (Google Colab)  
- RDKit  
- AutoDock Vina  
- OpenBabel  
- PyMOL / ChimeraX  
- Pandas  
- SwissADME  

---

## 👨‍🔬 Author

**Premkumar S**  
M.Sc. Biochemistry  
Computational Chemistry | Drug Discovery | Bioinformatics  
