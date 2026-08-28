# PROJECT ATLAS

## Greater Memphis — Critical Infrastructure & Spatial Analysis

**Author:** John-Henry E. Tate  
**Project Area:** Greater Memphis Metropolitan Area, Tennessee / Mississippi / Arkansas  
**GIS Platform:** ArcGIS Pro  
**Project Type:** Applied GIS / Spatial Analysis / Infrastructure Assessment

---

## Table of Contents

- [Project Overview](#project-overview)
- [Project Status](#project-status)
- [01 | Critical Infrastructure](#01--critical-infrastructure)
- [02 | Energy & Infrastructure](#02--energy--infrastructure)
- [03 | Transportation & Logistics](#03--transportation--logistics)
- [04 | Data Centers & Urban Development](#04--data-centers--urban-development)
- [05 | Population & Demographics](#05--population--demographics)
- [06 | Environmental Risk & Flood Exposure](#06--environmental-risk--flood-exposure)
- [07 | Emissions & Integrated Impact Analysis](#07--emissions--integrated-impact-analysis)
- [Cross-Project Lessons Learned](#cross-project-lessons-learned)
- [Final Project Reflection](#final-project-reflection)
- [Primary Data & Reference Sources](#primary-data--reference-sources)
- [Data Source Notes](#data-source-notes)
- [Repository Structure](#repository-structure)

---

# Project Overview

Project ATLAS is an applied GIS project focusing on the Greater Memphis metropolitan area and the spatial relationships between critical infrastructure, transportation, energy systems, population, hydrology, environmental risk and emerging digital infrastructure.

The project was developed as a seven-layer spatial analysis framework rather than as a collection of independent maps. Each thematic layer addresses a different component of the regional system, while the overall objective is to understand how these systems interact spatially.

The Greater Memphis area was selected because of its particularly complex combination of:

- major transportation corridors
- the Mississippi River
- regional aviation infrastructure
- rail infrastructure
- logistics and freight facilities
- energy and utility infrastructure
- military and other critical facilities
- rapidly expanding urban areas
- data-center and AI infrastructure
- population growth
- flood and environmental exposure

The project follows the general GIS workflow:

**Question → Data → Data Preparation → Analysis → Visualization → Interpretation**

The final atlas contains seven thematic map layers:

1. Critical Infrastructure
2. Energy & Infrastructure
3. Transportation & Logistics
4. Data Centers & Urban Development
5. Population & Demographics
6. Environmental Risk & Flood Exposure
7. Emissions & Integrated Impact Analysis

The accompanying maps document the current cartographic and analytical state of the project. This GitHub documentation provides the methodological background, researched data sources, planned analyses, project limitations and lessons learned.

---

# Project Status

The project was developed as an applied GIS analysis with an emphasis on data integration and spatial relationships.

The cartographic framework, thematic structure, initial data preparation and several GIS workflows were implemented in ArcGIS Pro.

However, the complete analytical workflow could not be finalized for every thematic layer within the available project timeframe.

A major reason was the size and complexity of several national and regional datasets. Large feature classes required significant download, loading and processing time in ArcGIS Pro. In addition, some datasets were difficult to identify as standardized GIS resources, particularly for specialized infrastructure such as privately operated data centers.

Rather than artificially simplify the analysis, the remaining analytical steps are documented as planned extensions.

This distinction is important:

- **Implemented:** data and GIS workflows that were actually prepared or used
- **Researched:** datasets and sources identified as relevant
- **Planned:** analytical procedures identified for the next stage
- **Not finalized:** procedures that could not be completed within the project timeframe

---

# 01 | Critical Infrastructure

## Background & Analytical Intention

The first layer establishes the fundamental critical-infrastructure framework for the Greater Memphis metropolitan area.

The intention was to identify and spatially visualize infrastructure facilities that are essential to regional transportation, energy, defense, logistics, aviation, water supply and digital infrastructure.

The layer was also designed as the foundation for the remaining six thematic layers. Later analyses could use these infrastructure locations as reference features for proximity, accessibility, environmental exposure and infrastructure-dependency analysis.

The critical infrastructure categories considered in the project include:

- Air Cargo Hubs
- Airports
- Data Centers
- Naval / military infrastructure
- Ports
- Power Plants
- Water Towers
- other infrastructure categories available within the project dataset

The map also incorporates regional hydrography and stream information to provide geographic context.

## Research Questions

The layer was intended to answer questions such as:

- Where are major critical infrastructure facilities located?
- Which infrastructure types are spatially concentrated?
- How are critical facilities distributed relative to Memphis and the surrounding metropolitan area?
- Which facilities are located near major transportation corridors?
- Which facilities are located near major water systems?
- Which facilities could become relevant reference points for subsequent environmental or accessibility analyses?

## Data Sources

| Source | Dataset / Resource | Purpose | Status |
|---|---|---|---|
| Existing project data | Critical Infrastructure feature layer | Main infrastructure inventory | Used |
| U.S. Geological Survey (USGS) | National Hydrography Dataset / Flowlines | Rivers, streams and hydrographic context | Used |
| U.S. Geological Survey (USGS) | NHD attributes including Stream Level / Stream Order | Hydrological hierarchy and feature selection | Used |
| U.S. Census Bureau | Geographic reference data | Metropolitan and geographic context | Researched / Used |
| Tennessee GIS | State geographic datasets | Regional geographic and infrastructure context | Researched |
| Memphis Light, Gas and Water (MLGW) | Utility information | Local utility infrastructure context | Researched |
| Tennessee Valley Authority (TVA) | Regional energy infrastructure information | Energy infrastructure context | Researched |
| Federal Aviation Administration (FAA) | Airport / aviation GIS information | Aviation infrastructure | Researched |
| Esri | Basemap and reference layers | Cartographic context | Used |
| OpenStreetMap | Transportation and geographic reference | Supplementary geographic context | Researched |

## GIS Workflow

The initial workflow consisted of:

1. Loading the critical infrastructure dataset into ArcGIS Pro.
2. Reviewing the available infrastructure categories.
3. Symbolizing infrastructure by sector/type.
4. Adding transportation and hydrographic reference layers.
5. Investigating the National Hydrography Dataset.
6. Exploring attributes such as `Stream Level` and `Stream Order`.
7. Selecting higher-order stream features for visual representation.
8. Preparing the map framework for subsequent spatial analysis.

An important part of the workflow was the investigation of the hydrographic attribute structure.

The Mississippi River was not initially available through a simple "Mississippi River" selection. Instead, the hydrographic network was investigated through the available attributes. The `Stream Level` classification was explored and different levels were tested to identify the major river network.

This demonstrated an important GIS principle: feature selection often depends on understanding the structure and semantics of the underlying dataset rather than simply searching for a geographic name.

## Planned Spatial Analysis

The intended next steps included:

- buffer analysis around critical infrastructure
- proximity analysis to transportation corridors
- proximity to major rivers and flood-prone areas
- infrastructure clustering
- overlay with population density
- overlay with energy infrastructure
- identification of infrastructure potentially exposed to environmental hazards

## Current Status

The infrastructure layer was successfully established as the core reference layer of the project.

The map contains the major infrastructure categories and provides the spatial framework for the remaining layers.

The complete multi-layer analysis was not finalized within the project timeframe.

## Problems & Limitations

Several problems became apparent during development:

- National-scale hydrographic datasets contain very large numbers of features.
- Attribute-based selections were not always intuitive.
- Some processing operations required significant time.
- The relationship between hydrographic classifications and recognizable geographic features such as the Mississippi River required investigation.
- Symbolization and line-width adjustments required additional experimentation.

## Lessons Learned

A major lesson from this layer was that understanding the attribute structure of a dataset is as important as understanding the map itself.

The Mississippi River example demonstrated that a GIS feature may be identifiable through network hierarchy or coded attributes rather than through a simple name search.

For future work, the workflow should begin with:

**Download → Clip to study area → Inspect attributes → Select relevant features → Analyze**

rather than loading very large national datasets into ArcGIS Pro and processing them at full extent.

---

# 02 | Energy & Infrastructure

## Background & Analytical Intention

The second layer was designed to examine the relationship between critical infrastructure and the regional energy and utility systems supporting Greater Memphis.

Critical infrastructure is dependent on reliable energy and utility systems. Therefore, the objective was to investigate whether major infrastructure facilities are located near relevant energy and utility infrastructure and whether spatial concentrations or dependencies can be identified.

Particular attention was intended for:

- power generation
- electricity infrastructure
- water infrastructure
- utility systems
- critical infrastructure facilities
- transportation infrastructure as a supporting factor

## Research Questions

The analysis was intended to investigate:

- Where are major energy facilities located?
- Which critical infrastructure facilities are located near energy infrastructure?
- Are important infrastructure facilities concentrated around particular utility corridors?
- How does energy infrastructure relate to population and urban development?
- Which facilities could potentially be affected by disruption to regional utility systems?

## Data Sources

| Source | Dataset / Resource | Purpose | Status |
|---|---|---|---|
| Tennessee Valley Authority (TVA) | Energy / electricity infrastructure information | Regional electricity infrastructure | Researched |
| Memphis Light, Gas and Water (MLGW) | Utility information | Local electricity, gas and water infrastructure | Researched |
| Existing project data | Power plants / critical infrastructure | Infrastructure reference | Used |
| U.S. Geological Survey | Hydrography | Water infrastructure and environmental context | Used |
| U.S. Census Bureau | Geographic and demographic data | Population / urban context | Researched |
| Tennessee GIS | State infrastructure datasets | Regional infrastructure | Researched |
| Esri | Basemap / reference data | Geographic context | Used |

## Planned GIS Analysis

The intended workflow included:

1. Identify major energy facilities.
2. Map electricity and utility infrastructure.
3. Integrate energy facilities with the critical infrastructure layer.
4. Create proximity buffers.
5. Identify critical infrastructure located within defined distances of energy infrastructure.
6. Compare infrastructure concentration with population distribution.
7. Identify potential infrastructure dependencies.

A buffer-based approach was considered particularly useful because it would allow the project to move from simple visualization toward an actual spatial relationship analysis.

## Current Status

The energy layer was developed primarily as an analytical framework and map composition.

Relevant infrastructure and reference layers were identified, but the complete proximity and dependency analysis was not finalized.

## Problems & Limitations

The main limitation was data availability.

Utility infrastructure is often more difficult to obtain as a complete, standardized public GIS dataset than roads or administrative boundaries.

In addition, infrastructure datasets may be distributed between federal, state and local organizations.

This creates a data-integration problem:

**different organizations → different formats → different geographic scales → different levels of detail**

## Lessons Learned

Energy infrastructure analysis requires careful attention to data ownership and availability.

A future version should prioritize obtaining locally clipped datasets from TVA, MLGW and state GIS sources before beginning spatial analysis.

---

# 03 | Transportation & Logistics

## Background & Analytical Intention

Greater Memphis is a major transportation and logistics hub because of its location along the Mississippi River and its extensive combination of road, rail, aviation and freight infrastructure.

The third layer was therefore designed to examine the regional transportation network and its relationship with critical infrastructure.

The analysis considered transportation as an interconnected system rather than as individual road features.

The main components were:

- highways
- major roads
- railroads
- airports
- air cargo
- port infrastructure
- Mississippi River
- logistics facilities

## Research Questions

The intended analysis asked:

- Where are the major transportation corridors?
- How are critical infrastructure facilities connected to transportation networks?
- Which facilities are located near major highways?
- Which infrastructure is located near rail or river transportation?
- Where are potential multimodal logistics concentrations?
- How important is Memphis' position as a regional transportation hub?

## Data Sources

| Source | Dataset / Resource | Purpose | Status |
|---|---|---|---|
| U.S. Census Bureau | TIGER/Line transportation data | Roads and geographic transportation framework | Researched / Used |
| Existing project data | U.S. railroads | Rail infrastructure | Used |
| Federal Aviation Administration (FAA) | Airport / aviation GIS data | Airports and aviation infrastructure | Researched |
| Existing project data | Airports / air cargo facilities | Critical transportation facilities | Used |
| Existing project data | Port infrastructure | Mississippi River logistics | Used |
| OpenStreetMap | Roads and transportation reference | Supplementary transportation data | Researched |
| USGS | Hydrography | Mississippi River and waterway context | Used |
| Esri | Basemap | Cartographic reference | Used |

## Planned GIS Analysis

The intended workflow included:

- road proximity analysis
- rail proximity analysis
- airport accessibility
- port accessibility
- multimodal infrastructure analysis
- buffer analysis around major transportation corridors
- identification of infrastructure clusters
- potential network-based accessibility analysis

A future network analysis could use travel distance or travel time rather than simple Euclidean distance.

## Current Status

The transportation layer was established as a thematic map and reference framework.

Major transportation systems are represented, but the complete network analysis was not finalized.

## Problems & Limitations

The main challenge was the volume and complexity of transportation datasets.

National-scale transportation datasets contain very large numbers of features, while the project focuses on a relatively small metropolitan area.

Processing the entire dataset before clipping therefore created unnecessary performance requirements.

## Lessons Learned

Transportation analysis should be performed on a study-area extract rather than on national datasets.

A more efficient workflow would be:

**National dataset → Memphis study-area clip → relevant transport classes → network analysis**

This would substantially reduce processing time and improve ArcGIS Pro performance.

---

# 04 | Data Centers & Urban Development

## Background & Analytical Intention

The fourth layer investigates the relationship between digital infrastructure, data centers, AI-computing infrastructure and urban development.

This topic was selected because data centers increasingly represent an important form of critical infrastructure.

Unlike traditional infrastructure such as roads or airports, data centers are often privately operated and their geographic information is not always available through a single standardized public GIS dataset.

The layer therefore combines an infrastructure question with a data-discovery problem.

## Research Questions

The intended analysis focused on:

- Where are major data centers located?
- Where is digital infrastructure concentrated?
- How close are data centers to population centers?
- How close are data centers to transportation infrastructure?
- How close are they to energy infrastructure?
- Are data-center locations associated with areas of urban growth?
- What supporting infrastructure is required around major digital facilities?

## Data Sources

| Source | Dataset / Resource | Purpose | Status |
|---|---|---|---|
| Existing project data | Data-center facilities | Main digital infrastructure reference | Used |
| U.S. Census Bureau | Population / geographic data | Population and urban context | Researched |
| Tennessee GIS | Geographic and infrastructure data | Regional context | Researched |
| MLGW | Utility infrastructure information | Energy and utility context | Researched |
| TVA | Electricity infrastructure information | Power infrastructure context | Researched |
| OpenStreetMap | Roads and geographic reference | Transportation access | Researched |
| Esri | Basemap / reference data | Cartographic context | Used |
| Facility-specific sources | Individual data-center information | Facility identification | Researched |

## Data Availability Challenge

A major challenge was that no single comprehensive public GIS dataset was identified that captures all major data-center and AI-computing facilities relevant to the Greater Memphis area.

Facility-specific information therefore had to be considered.

This means that a robust future dataset would need to combine:

**facility locations + ownership/operator information + energy infrastructure + transportation + population + urban development**

## Planned GIS Analysis

The planned workflow included:

1. Identify relevant data-center facilities.
2. Standardize facility locations.
3. Overlay data centers with population data.
4. Measure proximity to transportation corridors.
5. Measure proximity to energy infrastructure.
6. Compare data-center locations with urban development.
7. Identify infrastructure concentrations.
8. Develop a composite digital-infrastructure accessibility/dependency analysis.

## Current Status

The conceptual framework and map layer were established.

The data-center analysis was not fully finalized because the required facility-level dataset could not be assembled and standardized within the available project timeframe.

## Problems & Limitations

The largest limitation was data availability rather than GIS functionality.

Data centers are often private facilities and their locations, ownership and operational characteristics are not represented consistently in public GIS datasets.

A second limitation was the processing burden created by combining infrastructure, transportation, demographic and environmental datasets.

## Lessons Learned

The layer demonstrated that data acquisition can be a more significant challenge than the GIS analysis itself.

For future work, the data-center dataset should be constructed first as a dedicated, validated feature class before performing any spatial analysis.

This layer also demonstrated the importance of documenting data uncertainty rather than presenting incomplete facility inventories as comprehensive.

---

# 05 | Population & Demographics

## Background & Analytical Intention

The fifth layer was designed to introduce the human component of the infrastructure analysis.

Infrastructure does not exist independently from the population it serves.

Population distribution, density and demographic characteristics can therefore be used to evaluate where infrastructure demand is concentrated and how infrastructure systems relate to residential and urban areas.

## Research Questions

The intended analysis focused on:

- Where is population concentrated within Greater Memphis?
- Which areas have the highest population density?
- How does population distribution relate to critical infrastructure?
- Where are major infrastructure facilities located relative to population centers?
- Are areas of population growth associated with infrastructure development?
- Are there potential areas where infrastructure demand may increase?

## Data Sources

| Source | Dataset / Resource | Purpose | Status |
|---|---|---|---|
| U.S. Census Bureau | American Community Survey (ACS) | Population and demographic variables | Researched |
| U.S. Census Bureau | Decennial Census | Population distribution | Researched |
| U.S. Census Bureau | TIGER/Line Shapefiles | Census geography and boundaries | Used / Researched |
| U.S. Census Bureau | Metropolitan / geographic reference data | Study-area framework | Researched |
| Tennessee GIS | State geographic data | Regional reference | Researched |
| Existing project data | Critical infrastructure | Infrastructure comparison | Used |
| Esri | Basemap | Geographic context | Used |

## Planned GIS Analysis

The planned workflow included:

- population-density mapping
- demographic choropleth mapping
- infrastructure/population overlay
- proximity analysis
- population-to-infrastructure comparison
- identification of underserved or highly concentrated areas
- comparison with urban development

A particularly useful future analysis would be to compare infrastructure capacity or facility density with population density.

## Current Status

The demographic layer was defined as a thematic component of the atlas but the complete statistical/spatial analysis was not finalized.

## Problems & Limitations

Population analysis requires consistent geographic units.

Different datasets may use:

- census blocks
- block groups
- census tracts
- municipalities
- counties
- metropolitan areas

These units are not interchangeable.

The choice of geographic unit therefore has a direct impact on the resulting spatial pattern.

## Lessons Learned

A future workflow should establish the geographic unit before importing demographic data.

For a metropolitan-scale analysis, census tracts or block groups would provide a useful balance between spatial detail and processing requirements.

---

# 06 | Environmental Risk & Flood Exposure

## Background & Analytical Intention

The sixth layer addresses environmental risk, with particular emphasis on hydrology, elevation and flood exposure.

This is particularly relevant to Greater Memphis because the Mississippi River and associated waterways form a major geographic component of the metropolitan region.

The intention was to move beyond simply displaying rivers and instead examine how environmental conditions interact with infrastructure.

## Research Questions

The analysis was intended to investigate:

- Which critical infrastructure facilities are located near major waterways?
- Which facilities are potentially exposed to flood hazards?
- How does elevation influence infrastructure exposure?
- Where do flood-prone areas overlap with transportation or critical infrastructure?
- Which areas could represent higher-risk infrastructure concentrations?

## Data Sources

| Source | Dataset / Resource | Purpose | Status |
|---|---|---|---|
| U.S. Geological Survey | National Hydrography Dataset / NHDPlus | Rivers, streams and drainage network | Used |
| U.S. Geological Survey | 3DEP elevation data | Elevation and terrain analysis | Researched |
| Federal Emergency Management Agency (FEMA) | National Flood Hazard Layer (NFHL) | Flood hazard areas | Researched |
| National Oceanic and Atmospheric Administration (NOAA) | Environmental / climate data | Environmental context | Researched |
| U.S. Census Bureau | Geographic boundaries | Population and infrastructure overlay | Researched |
| Existing project data | Critical infrastructure | Exposure assessment | Used |
| Tennessee GIS | State environmental/geographic data | Regional environmental context | Researched |

## Planned GIS Analysis

The planned workflow included:

1. Prepare hydrographic data.
2. Identify major waterways.
3. Add elevation data.
4. Add flood hazard zones.
5. Overlay critical infrastructure.
6. Create infrastructure-to-waterway proximity buffers.
7. Identify infrastructure located within flood-risk areas.
8. Compare infrastructure exposure with population.
9. Produce a regional flood-exposure assessment.

A buffer analysis around major rivers was considered as an initial step, followed by intersection with flood-hazard polygons.

## Current Status

Hydrographic data were successfully incorporated into the project.

The flowline dataset was explored in ArcGIS Pro, including attributes such as `Stream Level` and `Stream Order`.

The environmental risk layer was established conceptually, but the complete flood/elevation overlay analysis was not finalized.

## Problems & Limitations

Hydrographic datasets were among the more computationally demanding datasets used in the project.

The number of flowline features made repeated selection and processing operations relatively slow.

The investigation also demonstrated that the visually recognizable Mississippi River is not necessarily represented as a single simple feature in the underlying GIS dataset.

## Lessons Learned

Hydrological analysis requires understanding the network structure of the data.

Future analysis should begin by clipping the hydrographic dataset to the Greater Memphis study area and then selecting only the required feature classes and stream hierarchy levels.

This would substantially improve performance.

---

# 07 | Emissions & Integrated Impact Analysis

## Background & Analytical Intention

The seventh layer was designed as the final synthesis layer of Project ATLAS.

Instead of focusing on a single infrastructure category, the objective was to combine several previously developed themes and examine potential cumulative spatial impacts.

The concept was to investigate the relationship between:

- transportation
- energy infrastructure
- population
- urban development
- critical infrastructure
- environmental conditions
- emissions

This layer therefore represents the transition from individual thematic mapping toward integrated spatial analysis.

## Research Questions

The intended analysis focused on questions such as:

- Where do transportation, energy and population concentrations overlap?
- Where might infrastructure and environmental pressures accumulate?
- Are areas with high transportation activity also associated with higher population exposure?
- Where are major infrastructure facilities located in relation to environmental risk?
- Can multiple GIS layers be combined to identify areas of increased cumulative impact?

## Data Sources

| Source | Dataset / Resource | Purpose | Status |
|---|---|---|---|
| U.S. Environmental Protection Agency (EPA) | Emissions / environmental datasets | Emissions and environmental impact | Researched |
| EPA | EJScreen / environmental indicators | Environmental burden and demographic context | Researched |
| NOAA | Environmental / climate datasets | Environmental conditions | Researched |
| U.S. Geological Survey | Hydrography | Water and environmental context | Used |
| U.S. Geological Survey | Elevation / terrain data | Environmental exposure | Researched |
| U.S. Census Bureau | Population / demographic data | Population exposure | Researched |
| Transportation datasets | Roads / rail / airports | Transportation intensity | Used / Researched |
| Energy datasets | TVA / MLGW | Energy infrastructure | Researched |
| Existing project data | Critical infrastructure | Infrastructure exposure | Used |
| Esri | Basemap / geographic context | Visualization | Used |

## Planned GIS Analysis

The final analytical workflow was intended to combine multiple layers through:

- spatial overlay
- proximity analysis
- buffer analysis
- density analysis
- weighted spatial criteria
- infrastructure exposure assessment
- population exposure assessment
- cumulative impact mapping

A possible final workflow would assign analytical criteria to individual components and combine them into an integrated spatial index.

For example:

**Transportation + Energy + Population + Environmental Risk + Critical Infrastructure**

could be combined to identify areas where multiple spatial pressures overlap.

## Current Status

The layer was developed primarily as the conceptual synthesis stage of the project.

The thematic framework and required data relationships were identified, but the complete integrated analysis was not finalized.

## Problems & Limitations

The integrated layer depends on all previous thematic datasets being sufficiently complete and standardized.

Because several preceding layers remained partially implemented, a final integrated index would have created a false impression of analytical completeness.

For this reason, the final integrated analysis was documented as a planned extension rather than presented as a finished quantitative result.

## Lessons Learned

An integrated GIS analysis is only as reliable as its underlying datasets.

Combining incomplete or inconsistent datasets can produce a visually convincing but analytically weak result.

The project therefore demonstrates the importance of:

**Data quality → Data consistency → Spatial analysis → Interpretation**

rather than beginning with visualization alone.

---

# Cross-Project Lessons Learned

## 1. Data Availability Is Part of GIS Analysis

One of the most important lessons from Project ATLAS was that obtaining appropriate spatial data can be as difficult as performing the analysis itself.

Some datasets are standardized and easily available, while others require research across federal, state, local and private sources.

This was particularly apparent for:

- data centers
- energy infrastructure
- utility infrastructure
- emissions
- detailed local infrastructure

## 2. Large Datasets Should Be Reduced Early

Several national datasets were much larger than required for the actual study area.

Working with national-scale data inside ArcGIS Pro created unnecessary processing requirements.

A more efficient workflow would be:

**Download → Clip → Filter → Project → Analyze**

rather than:

**Download → Load national dataset → Symbolize → Process → Clip**

## 3. Attribute Knowledge Is Essential

The hydrography analysis demonstrated that GIS data cannot always be interpreted visually.

Fields such as:

- Stream Level
- Stream Order
- Feature Type
- Geographic Names Information System identifiers

may be more useful for analysis than the visible feature name.

Understanding the attribute model is therefore an essential part of spatial analysis.

## 4. Visualization and Analysis Are Different Stages

The project also demonstrated the difference between creating a visually convincing map and completing a spatial analysis.

A map can communicate a spatial relationship without proving that the relationship is statistically or analytically significant.

The final project therefore distinguishes between:

- **cartographic representation**
- **data preparation**
- **planned spatial analysis**
- **completed spatial analysis**

## 5. Performance Is a Design Constraint

ArcGIS Pro performance became an important practical constraint during the project.

Large feature classes, repeated selections and complex layer combinations increased processing time.

This affected the ability to complete all planned analyses within the available timeframe.

Future iterations would therefore prioritize:

- study-area clipping
- smaller feature classes
- targeted data extraction
- efficient geoprocessing
- simplified intermediate datasets
- processing only the features required for the specific analysis

---

# Final Project Reflection

Project ATLAS was designed as a regional GIS framework rather than a single analytical result.

The project demonstrates how multiple spatial datasets can be combined to investigate the relationship between critical infrastructure, transportation, energy, population, environmental risk and emerging digital infrastructure.

The final maps represent the current state of the project, while the documented analytical extensions show how the project could be developed further.

The incomplete analytical components are therefore considered part of the documented project process rather than omitted from the project record.

The next development stage would focus on completing the spatial analysis using geographically clipped datasets, standardized infrastructure inventories and targeted geoprocessing workflows.

---

# Primary Data & Reference Sources

The following organizations and datasets were investigated or used during the development of Project ATLAS:

| Organization | Data / Resource | Main Relevance |
|---|---|---|
| U.S. Geological Survey (USGS) | National Hydrography Dataset / NHDPlus / 3D Hydrography | Rivers, streams, drainage and hydrology |
| U.S. Geological Survey (USGS) | 3DEP | Elevation and terrain |
| U.S. Census Bureau | Census / ACS | Population and demographics |
| U.S. Census Bureau | TIGER/Line | Geographic boundaries and transportation |
| Federal Aviation Administration (FAA) | Airport GIS / airport data | Aviation infrastructure |
| Federal Emergency Management Agency (FEMA) | National Flood Hazard Layer | Flood exposure |
| Environmental Protection Agency (EPA) | Environmental / emissions datasets | Emissions and environmental impact |
| EPA | EJScreen | Environmental and demographic indicators |
| National Oceanic and Atmospheric Administration (NOAA) | Climate / environmental data | Environmental context |
| Tennessee GIS | State GIS datasets | Tennessee geographic and infrastructure data |
| Tennessee Valley Authority (TVA) | Energy infrastructure information | Regional energy systems |
| Memphis Light, Gas and Water (MLGW) | Utility information | Local utility infrastructure |
| Esri | Basemaps and reference layers | Cartographic context |
| OpenStreetMap | Open geographic data | Roads, geographic reference and supplementary transportation information |
| Existing project datasets | Critical Infrastructure | Infrastructure inventory and thematic mapping |

---

# Data Source Notes

USGS hydrography was particularly important to the project because it provided the flowline network used to investigate the regional river and stream system. The NHD contains networked surface-water features and attributes such as names, flow direction and stream hierarchy. The legacy NHD was retired as a maintained product in 2023, with the USGS now developing the 3D Hydrography Program as its successor.

U.S. Census Bureau TIGER/Line data were considered important for establishing standardized geographic and transportation reference layers and for linking geographic entities to demographic information.

FAA airport GIS resources were investigated as a source for aviation infrastructure and airport-related geographic information.

---

# Repository Structure

The Project ATLAS documentation is organized around the seven thematic layers:

- `01 | Critical Infrastructure`
- `02 | Energy & Infrastructure`
- `03 | Transportation & Logistics`
- `04 | Data Centers & Urban Development`
- `05 | Population & Demographics`
- `06 | Environmental Risk & Flood Exposure`
- `07 | Emissions & Integrated Impact Analysis`

The final atlas PDF provides the cartographic outputs, while this README documents the underlying analytical intention, data sources, methodology, limitations and future development.
