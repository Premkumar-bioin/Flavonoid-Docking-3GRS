# Computational Investigation of Flavonoids Targeting Glutathione Reductase in Intestinal Inflammation

## 📌 Project Overview
This project investigates the antioxidant and anti-inflammatory potential of a flavonoid library, specifically comparing **Naringin** and **Luteolin**, against Human Glutathione Reductase (3GRS). This computational workflow was designed to support an *in vivo* Zebrafish Inflammatory Bowel Disease (IBD) model.

## 🔬 Scientific Rationale
Naringin is a major flavonoid glycoside studied in zebrafish IBD models. This project utilizes molecular docking to determine whether Naringin directly inhibits 3GRS or if it likely acts as a prodrug (requiring metabolism into an aglycone) compared to planar flavonoids like Luteolin.

## 🛠️ Tools & Technologies Used
* **Data Preparation:** Python, RDKit, Pandas
* **Molecular Docking:** AutoDock Vina, Meeko
* **Interaction Analysis:** BioPython, PyMOL, py3Dmol
* **ADMET Prediction:** SwissADME (Lipinski's Rule of Five)

## 📊 Key Findings
1. **Luteolin emerged as the lead compound.** It successfully penetrated the deep catalytic pocket of 3GRS, forming a critical **1.91 Å hydrogen bond** with Thr40 near the redox-active Cys58/Cys63 disulfide center.
2. **Naringin exhibited steric hindrance.** Due to its bulky neohesperidoside sugar moiety, Naringin showed a weaker binding profile compared to Luteolin. 
3. **Conclusion:** The data suggests that for high-affinity binding to Glutathione Reductase, the aglycone structure is preferred. In the zebrafish model, Naringin's efficacy is likely dependent on gut microbiota or enzymatic cleavage into Naringenin.

## 🖼️ Visualization: Consensus Binding
<img width="1919" height="752" alt="Screenshot 2026-04-24 100150" src="https://github.com/user-attachments/assets/84337257-5baa-49ad-9988-f49e1d447d54" />
<img width="1919" height="752" alt="Screenshot 2026-04-24 100109" src="https://github.com/user-attachments/assets/c0dff68c-fb16-4e7f-b180-8080d6c99f39" />
<img width="1465" height="563" alt="Screenshot 2026-04-24 100047" src="https://github.com/user-attachments/assets/50d85ae5-0fa9-4f11-8a19-5ff7fa5b5c44" />
<img width="1618" height="625" alt="Screenshot 2026-04-24 100011" src="https://github.com/user-attachments/assets/7f0de25d-4347-473d-8acd-21ade3dff528" />
<img width="909" height="440" alt="Screenshot 2026-04-24 095946" src="https://github.com/user-attachments/assets/e4201720-4712-4d26-be5f-3d25c6013e01" />
<img width="731" height="493" alt="Screenshot 2026-04-24 095905" src="https://github.com/user-attachments/assets/7038b8db-d985-4431-93d8-f530ef6d3ff3" />
<img width="831" height="480" alt="Screenshot 2026-04-24 095850" src="https://github.com/user-attachments/assets/1ed00fa0-96d2-43a5-8453-85314df00113" />



## 📂 Repository Structure
* `Final_Zebrafish_IBD_Docking_Project.csv`: Contains binding affinities (kcal/mol), RMSD values, and ADMET Lipinski violations.
* `notebook.ipynb`: The complete Google Colab pipeline from protein preparation to interaction analysis.
