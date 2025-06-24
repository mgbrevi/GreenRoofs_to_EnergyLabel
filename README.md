# GreenRoofs_to_EnergyLabel

This project investigates how retrofitting green roofs can improve the energy label of buildings in Amsterdam. It combines machine learning predictions with empirical energy savings to simulate the city-wide impact of retrofitting different types of buildings.

##  Project Goals

- Predict energy labels of buildings using a Random Forest model
- Estimate counterfactual labels for green-roof buildings: *What if they didn’t have a green roof?* and a second counterfactual to estimate the labels of buildings retrofitted with a green roof: *What would be the expected energy label of buildings if they were retrofitted with a green roof?*
- Apply empirical energy reduction percentages from literature (Virk et al., 2015)
- Quantify how many buildings would improve their energy label after retrofitting

## Repository Structure 
├── CODE.ipynb # Main analysis notebook ├── data/ │ ├── Energy_Labels.csv # Building energy label classification │ ├── heating_coolig_reductions.csv # Scenario reduction percentages │ └── .gitkeep # Keeps folder in Git tracked ├── Brevi_2025.pdf # (Optional) Thesis report ├── README.md # This file ├── LICENSE # MIT License 



##  Data

The following datasets are included in the `/data/` folder:

- `Energy_Labels.csv`: Energy label categories by primary building function (RVO classification)
- `heating_coolig_reductions.csv`: Percentage reductions in energy use under green roof retrofit scenarios

The main dataset is too large to upload here:

> 🔗 Download `GR_unfiltered_energy_all_address.gpkg` from Google Drive:  
> [Click here to download](https://drive.google.com/file/d/13_jKlsRL72F8jiIy8ZDA_F74d3wtT94/view?usp=sharing)  
> After downloading, place it in the root folder of the repo to run the notebook.

## Methodology Overview

- Trained a Random Forest on non-green-roof buildings to predict energy labels and tested on green roofs to establish whether we can make generalizations over the patterns between the two
- Tested model on green-roof buildings to simulate labels *as if* they didn’t have a green roof (counterfactual 1)
- Once stablished generalizations patterns another model is trained on both on green roofs and non green roofs to then establish the labels of retrofitted green roofs (counterfactual 2)
- Applied empirical energy savings to estimate how retrofitting would change labels (Virk et al. 2015)
- Disaggregated results by original label and building type

## Key Insights

- Green roofs can improve building energy labels, but the effect is modest and context-dependent.
- In the first counterfactual (removing existing green roofs), only 3% of buildings showed a downgrade, suggesting limited but real performance benefits.
- In the second counterfactual (retrofitting green roofs), just 1.9% of buildings improved their label—most notably those with initially poor energy performance (labels D–G).
- City-wide simulation using empirical values from Virk et al. (2015) showed that ~19% of buildings could improve their energy label if retrofitted.
- Label gains were concentrated in inefficient or underperforming building types, such as education and lodging facilities.


## Thesis Report

You can also download the full thesis as a PDF here:  
[Brevi_2025.pdf](Brevi_2025.pdf) 

## Author

Maria Graziella Brevi  
MSc Data Science – Utrecht University 
MSc Spatial Sustainability - University of Amsterdam 
[LinkedIn](# www.linkedin.com/in/maria-graziella-brevi-2a9086198) | 📧 [mariagraziellabrevi@email.com]

---

## 📜 License

This project is licensed under the MIT License. See the `LICENSE` file for more details.
