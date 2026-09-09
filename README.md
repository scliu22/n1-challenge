# N1 Health: Take-Home Data Challenge

## Overview
### Directory Structure
```
.
├── challenge.db
├── data
│   ├── 2025-food-environment-atlas-data
│   │   ├── ReadMeFile2025.txt
│   │   ├── StateAndCountyData.csv
│   │   └── VariableList.csv
│   └── 500-cities-2019-release
│       ├── 500_Cities__Census_Tract-level_Data_(GIS_Friendly_Format),_2019_release_20260902.csv
│       └── 500_cities_variables.csv
├── deliverables
│   └── main.ipynb
├── environment.yml
└── README.md
```

### Description
N1 Health’s client, a national Medicare Advantage plan, is seeking to understand how best to use its resources to address food access challenges in its membership. N1 Health has been tasked with presenting a short analysis (~5-10 minutes) of publicly available data to the Chief Medical Officer to answer this question. The guiding questions are:
1. Where should we deploy a food access program?
2. How many people will be included? How many might be successfully engaged?
3. Which subgroup of the population might benefit the most from the program?
4. What is the projected impact of this program?

### Datasets
- Food Environment Atlas
    - Food Choices—Indicators of the community's access to and acquisition of healthy, affordable food, such as: access and proximity to a grocery store; number of food stores and restaurants in a county; food and nutrition assistance program participation; and availability of local foods in a county.
    - Health and Well-Being—Indicators of the community's success in maintaining healthy diets, such as: food insecurity; diabetes and obesity rates; and physical activity levels.
    - Community Characteristics—Indicators of community characteristics that might influence the food environment, such as: demographic composition; income and poverty; population loss; metropolitan-nonmetropolitan status; natural amenities; and recreation and fitness centers.
- 500 Cities: Census Tract-level Data

Notes:
The food environment atlas csv file `StateAndCountyData.csv` contains negative values: Counties that didn’t exist in a particular year are referenced with -8888. Data that were not available, not applicable, or suppressed for specific areas in previous Food Environment Atlas data releases are denoted with a blank cell or –9999 as indicated in the individual files.

### Environment
To reproduce the results from the notebook:

**Step 1: Create Conda Environment**
```
conda env create -f environment.yml
```

**Step 2. Import the 2025 Food Environment Atlas into the SQLite Database**
```
$ sqlite3 challenge.db
> .mode csv
> .import path/to/2025-food-environment-atlas-data.csv my_table
```
