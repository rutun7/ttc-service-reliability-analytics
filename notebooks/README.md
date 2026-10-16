# Microsoft Fabric Notebooks

PySpark notebooks used to implement the Bronze, Silver, and Gold layers of the TTC service reliability data pipeline.

### Bronze – Data Ingestion
`NB_TTC_Bronze_Ingestion.ipynb`

Ingests raw TTC Bus, Subway, Streetcar, and LRT delay data from Toronto Open Data and stores the source data in the Bronze layer in OneLake.

### Silver – Data Transformation
`NB_TTC_Silver_Transformation.ipynb`

Cleans and transforms the raw TTC datasets using PySpark, standardizes data across transit modes, creates additional analytical fields, and maps TTC incident codes to their descriptions.

### Gold – Analytics Model
`NB_TTC_Gold_Transformation.ipynb`

Combines the transformed datasets and creates analytics-ready fact and dimension tables used by the Power BI semantic model and dashboard.
