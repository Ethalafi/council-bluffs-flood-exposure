Mapping Flood Exposure in Council Bluffs, Iowa
A GIS-Based Environmental Analysis
Project Overview
This project examines the geographic extent of FEMA-designated Special Flood Hazard Areas (SFHAs) within Council Bluffs, Iowa.
Using QGIS, FEMA's National Flood Hazard Layer (NFHL), and U.S. Census Bureau municipal boundary data, I evaluated how much of the city's mapped geographic area falls within designated flood-hazard zones.
The objective was to demonstrate how GIS can be used to process environmental datasets, perform spatial analysis, and communicate geographic findings through professional cartographic visualization.
Key Findings
	•	23.01% of Council Bluffs' mapped municipal area falls within FEMA-designated Special Flood Hazard Areas.
	•	Approximately 10.47 square miles are classified as SFHA.
	•	The municipal study area covers approximately 45.49 square miles.
	•	53 SFHA polygon features were identified before dissolving them into a combined flood-hazard footprint.
These findings describe geographic exposure, not the percentage of residents, homes, or buildings affected.
Tools and Technologies
	•	QGIS 4.2.2
	•	Geographic Information Systems (GIS)
	•	Vector geoprocessing and spatial analysis
	•	GeoPackage
	•	Coordinate reference systems and area calculations
	•	Cartographic design and map export
Data Sources
FEMA National Flood Hazard Layer (NFHL)
Pottawattamie County, Iowa. County dataset associated with the April 16, 2013 effective study.
U.S. Census Bureau
2024 Cartographic Boundary Files — Iowa Places.
Methodology
	1	Imported the Council Bluffs municipal boundary from U.S. Census Bureau data.
	2	Reprojected the study boundary into NAD83 / Iowa South (EPSG:26976).
	3	Imported FEMA flood-hazard polygons from the county NFHL geodatabase.
	4	Repaired invalid FEMA polygon geometries.
	5	Clipped the flood-hazard dataset to the municipal boundary.
	6	Selected Special Flood Hazard Area features using the FEMA SFHA_TF attribute.
	7	Exported the selected features and dissolved them into a combined flood-hazard footprint.
	8	Calculated the geographic area of the dissolved SFHA geometry and municipal boundary.
	9	Calculated the percentage of the municipal area within mapped SFHA boundaries.
	10	Created and exported a professional flood-exposure map.
Results
The analysis identified approximately 10.47 square miles of FEMA-designated SFHA within the 45.49-square-mile Council Bluffs study area.
This represents approximately 23.01% of the city's mapped municipal area.
The results demonstrate the usefulness of GIS for quantifying environmental exposure and communicating spatial patterns to stakeholders.
Limitations
FEMA-designated Special Flood Hazard Areas represent mapped flood hazards and do not capture every possible flooding scenario.
This analysis measures geographic area rather than the exposure of individual structures, infrastructure assets, or populations.
The results also depend on the effective FEMA flood-hazard data and municipal boundary dataset used in the analysis. Subsequent FEMA map revisions may change the mapped extent.
Future Analysis
Future work could expand this analysis by incorporating:
	•	Building footprints to estimate structural exposure
	•	Census population data to assess potential community impacts
	•	Transportation networks to identify roads within mapped flood-hazard areas
	•	Critical infrastructure locations to evaluate potential service disruptions
Project Deliverables
	•	Council Bluffs Flood Exposure Map (PNG)
	•	Council Bluffs Flood Exposure Map (PDF)
	•	GIS methodology and analytical findings
