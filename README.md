# 🧬 Computational Investigation of Flavonoids Targeting Glutathione Reductase in Intestinal Inflammation

---

## 📌 Project Overview

This project explores the binding potential of selected flavonoids (**Naringin**, **Naringenin**, **Quercetin**, **Kaempferol**, and **Luteolin**) against **Glutathione Reductase (PDB ID: 3GRS)** using a fully code-driven computational pipeline implemented in Google Colab.

The study aims to understand how structural variations among flavonoids influence their interaction with antioxidant enzymes involved in oxidative stress regulation, which is closely associated with Inflammatory Bowel Disease (IBD).

---

## 🔬 Scientific Rationale

Oxidative stress plays a significant role in the pathophysiology of IBD.  
**Glutathione reductase (GR)** is a key enzyme responsible for maintaining intracellular redox balance by regenerating reduced glutathione (GSH).

In prior *in vivo* zebrafish experiments, **Naringin** demonstrated protective effects against intestinal inflammation. This study investigates:

- Whether Naringin directly interacts with GR  
- Or functions as a **prodrug**, requiring metabolic conversion to its aglycone (**Naringenin**)  
- How planar flavonoids (e.g., Luteolin, Quercetin) compare in binding efficiency  

---

## ⚙️ Computational Workflow

This project was executed entirely through code (no GUI tools), following a structured CADD pipeline:

### 🔹 Phase 1 — Ligand Preparation
- SMILES retrieval and processing using RDKit  
- 3D conformer generation (ETKDG)  
- Energy minimization (MMFF94)  
- Output formats: `.sdf`, `.pdb`  

---

### 🔹 Phase 2 — Protein Preparation
- Structure retrieved from RCSB PDB (3GRS)  
- Removal of water molecules and unwanted heteroatoms  
- Retention of FAD cofactor (catalytic relevance)  
- Hydrogen addition and charge assignment using OpenBabel  

---

### 🔹 Phase 3 — Molecular Docking
- Docking performed using AutoDock Vina  
- Grid box centered around FAD-associated catalytic region  
- Exhaustiveness: 16  
- Top binding poses extracted and ranked  

---

### 🔹 Phase 4 — Visualization & Interaction Analysis
- Structural visualization using:
  - PyMOL  
  - UCSF ChimeraX  
  - py3Dmol (in-notebook rendering)  
- Interaction profiling:
  - Hydrogen bonds  
  - Residue-level contacts  
  - Binding orientation analysis  

---

### 🔹 Phase 5 — ADMET Evaluation
- Drug-likeness prediction via SwissADME  
- Lipinski Rule of Five assessment  
- Physicochemical property analysis  

---

## 📊 Key Findings

### 🥇 1. Lead Compound Identification
**Luteolin** demonstrated the strongest binding affinity (~ -8.66 kcal/mol), followed closely by Quercetin.

- Favorable positioning within catalytic pocket  
- Strong hydrogen bonding interactions near active-site residues  
- Planar structure enhances π–π and H-bond interactions  

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
