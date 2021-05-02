# Introduction
These github projects are a collection of tools and improvements made to accomplish tasks as well as potential tools and applications designed for future applications. Core capabilities include tools that interact with Google Earth Engine, Planet Labs API, Arctic DEM datasets and coupling large scale data pipelines using satadd projects. These projects extends tools and stand alone CLI(s) and GUI(s) for testing and implementation on various platforms. Some tools are designed to allow for easy intergation with cloud services such as Digital Ocean along with standalone hackathon tools and collaborations.

<center> **Projects Include work on following Platforms** </center>

<center>![combined_logo](https://user-images.githubusercontent.com/6677629/67629902-68297700-f854-11e9-8379-8e613e0c3d75.png)</center>

Two projects included looking at different aspects of raster analysis and landscape modeling and hence I decided to create an ArcMap toolbox with tools that I have developed and continue to develop further. The toolbox can be downloaded and added to existing toolbox to create additional functionalities. The synthetic landscape models are designed to try different randomizing and clustering algorithms. An additional project was completed during the [Polar Geospatial Bootcamp](https://www.pgc.umn.edu/) which allows users to bulk download and process 2m high resolution ArcticDEM provided by the Polar Geospatial Center. The list now also includes a notifier application using the Slack interface along with including an application of the Clips API from Planet.

<center>

| Recent Project Names       |                          Digital Object Identification Number(DOI)                              | GitHub Release | PyPI Stats |
|----------------------------|-------------------------------------------------------------------------------------------------|----------------|------------|
| porder: Simple ordersv2 CLI|[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1534692.svg)](https://doi.org/10.5281/zenodo.1534692)|[![GitHub version](https://badge.fury.io/gh/samapriya%2Fporder.svg)](https://badge.fury.io/gh/samapriya%2Fporder)|![Build Status](https://img.shields.io/badge/dynamic/json.svg?label=downloads&url=https%3A%2F%2Fpypistats.org%2Fapi%2Fpackages%2Fporder%2Frecent%3Fperiod%3Dmonth&query=%24.data.last_month&colorB=blue&suffix=%2fmonth)|
| Planet-GEE-Pipeline-CLI    | [![DOI](https://zenodo.org/badge/90417237.svg)](https://zenodo.org/badge/latestdoi/90417237)    | [![GitHub version](https://badge.fury.io/gh/samapriya%2FPlanet-GEE-Pipeline-CLI.svg)](https://badge.fury.io/gh/samapriya%2FPlanet-GEE-Pipeline-CLI)|![Build Status](https://img.shields.io/badge/dynamic/json.svg?label=downloads&url=https%3A%2F%2Fpypistats.org%2Fapi%2Fpackages%2Fppipe%2Frecent%3Fperiod%3Dmonth&query=%24.data.last_month&colorB=blue&suffix=%2fmonth)|
| GEE Asset Manager Addons   | [![DOI](https://zenodo.org/badge/87708514.svg)](https://zenodo.org/badge/latestdoi/87708514)    |[![GitHub version](https://badge.fury.io/gh/samapriya%2Fgee_asset_manager_addon.svg)](https://badge.fury.io/gh/samapriya%2Fgee_asset_manager_addon)|![Build Status](https://img.shields.io/badge/dynamic/json.svg?label=downloads&url=https%3A%2F%2Fpypistats.org%2Fapi%2Fpackages%2Fgeeadd%2Frecent%3Fperiod%3Dmonth&query=%24.data.last_month&colorB=blue&suffix=%2fmonth)|
|satadd: MultiSource CLI|[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1450622.svg)](https://doi.org/10.5281/zenodo.1450622)|[![GitHub version](https://badge.fury.io/gh/samapriya%2Fsatadd.svg)](https://badge.fury.io/gh/samapriya%2Fsatadd)|![Build Status](https://img.shields.io/badge/dynamic/json.svg?label=downloads&url=https%3A%2F%2Fpypistats.org%2Fapi%2Fpackages%2Fsatadd%2Frecent%3Fperiod%3Dmonth&query=%24.data.last_month&colorB=blue&suffix=%2fmonth)|
|geeup: GEE Upload CLI       | [![DOI](https://zenodo.org/badge/144343870.svg)](https://zenodo.org/badge/latestdoi/144343870)  |[![GitHub version](https://badge.fury.io/gh/samapriya%2Fgeeup.svg)](https://badge.fury.io/gh/samapriya%2Fgeeup)|![Build Status](https://img.shields.io/badge/dynamic/json.svg?label=downloads&url=https%3A%2F%2Fpypistats.org%2Fapi%2Fpackages%2Fgeeup%2Frecent%3Fperiod%3Dmonth&query=%24.data.last_month&colorB=blue&suffix=%2fmonth)|
|gee2drive: GEE Download CLI | [![DOI](https://zenodo.org/badge/142454859.svg)](https://zenodo.org/badge/latestdoi/142454859)  |[![GitHub version](https://badge.fury.io/gh/samapriya%2Fgee2drive.svg)](https://badge.fury.io/gh/samapriya%2Fgee2drive)|![Build Status](https://img.shields.io/badge/dynamic/json.svg?label=downloads&url=https%3A%2F%2Fpypistats.org%2Fapi%2Fpackages%2Fgee2drive%2Frecent%3Fperiod%3Dmonth&query=%24.data.last_month&colorB=blue&suffix=%2fmonth)|
|pydrop: Digital Ocean CLI   | [![DOI](https://zenodo.org/badge/141707238.svg)](https://zenodo.org/badge/latestdoi/141707238)  |[![GitHub version](https://badge.fury.io/gh/samapriya%2Fpydrop.svg)](https://badge.fury.io/gh/samapriya%2Fpydrop)|![Build Status](https://img.shields.io/badge/dynamic/json.svg?label=downloads&url=https%3A%2F%2Fpypistats.org%2Fapi%2Fpackages%2Fpydrop%2Frecent%3Fperiod%3Dmonth&query=%24.data.last_month&colorB=blue&suffix=%2fmonth)|
|Planet BaseMap CLI|[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1432872.svg)](https://doi.org/10.5281/zenodo.1432872)|[![GitHub version](https://badge.fury.io/gh/samapriya%2FPlanet-Mosaic-Quads-Download-CLI.svg)](https://badge.fury.io/gh/samapriya%2FPlanet-Mosaic-Quads-Download-CLI)|![Build Status](https://img.shields.io/badge/dynamic/json.svg?label=downloads&url=https%3A%2F%2Fpypistats.org%2Fapi%2Fpackages%2Fpbasemap%2Frecent%3Fperiod%3Dmonth&query=%24.data.last_month&colorB=blue&suffix=%2fmonth)|

</center>






