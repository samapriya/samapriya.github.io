# ArcMap Addons

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1009210.svg)](https://doi.org/10.5281/zenodo.1009210)

While working on different projects over sometime I had to create and use some tools which acted as valuable addons to arcmap toolbox. I am sharing a few and I will keep on updating these as I keep working on new models.This toolbox was created on ArcMap 10.4 and is not backward compatible. The toolbox can be downloaded and added to existing toolbox to create additional functionalities.

![GUI](https://user-images.githubusercontent.com/6677629/67630043-893f9700-f857-11e9-913c-c36419366d2d.gif)
## Table of contents
* [Installation](#installation)
* [Usage examples](#usage-examples)
    * [Batch Raster to Point](#batch-raster-to-point)
    * [Batch Table to CSV](#batch-table-to-csv)
	* [Email Notification](#email-notification)
    * [Iterative Clip](#iterative-clip)
    * [MultiBand to Single Images](#multiband-to-single-images)
    * [Raster Properties as CSV](#raster-properties-to-csv)
    * [Raster Copy Iterative](#raster-copy-iterative)
	* [Feature Select and Copy](#feature-select-and-copy)
	* [Select and Calculate Field](#select-and-calculate-field)
* [Credits](#credits)

## Installation
We assume that the user already has a copy of ArcMap >=10.4. The toolbox can be downloaded along with adjoining script and added onto existing toolbox. You can keep this toolbox as part of the default toolboxes by clicking Save Settings>Save as Default

## Usage examples
Usage examples will vary and only continue to grow as new tools are added to the toolbox.

### Batch Raster to Point
This tool allows you to convert all Raster datasets in a folder into a point with the value field converted to GRID code. The tool supports all raster formats supported by ArcMap and renames the files automatically to the source file name. The raster pixel is converted to a centroid value.

![batchrp](https://user-images.githubusercontent.com/6677629/67630054-9fe5ee00-f857-11e9-99e1-1ccd53f6d3eb.jpg)

### Batch Table to CSV
This tool allows you to batch convert all table files(in this case it looks for '.dbf' files) and converts the fields into csv columns. This is an effective way when you want to handle a large number of dbf files to be imported into other softwares and or processing chains.

![batchcsv](https://user-images.githubusercontent.com/6677629/67630052-9fe5ee00-f857-11e9-94e4-a5d03555e7c7.jpg)

### Email Notification
I found this to be one of the most useful tools when running a long process and not having to wait for your results. The tool makes use of the smtp library and allows the user to set up an email service for an email to be sent out after a process has been completed.

![Email](https://user-images.githubusercontent.com/6677629/67630051-9fe5ee00-f857-11e9-8a93-93a953f093ef.gif)

### Iterative Clip
This tool does exactl what the name suggests it uses an iterator tool to clip a raster to different boundaries using shapefiles. Requires a single raster file and a folder with multiple polygons for clips.

![iterativeclip](https://user-images.githubusercontent.com/6677629/67630050-9f4d5780-f857-11e9-8993-a925ad045c5b.gif)

If using on a private machine the Key is saved as a csv file for all future runs of the tool.

### MultiBand to Single Images
The aoijson tab within the toolset allows you to create filters and structure your existing input file to that which can be used with Planet's API. The tool requires inputs with start and end date, along with cloud cover. You can choose from multiple input files types such as KML, Zipped Shapefile, GeoJSON, WKT or even Landsat Tiles based on PathRow numbers. The geo option asks you to select existing files which will be converted into formatted JSON file called aoi.json. If using WRS as an option just type in the 6 digit PathRow combination and it will create a json file for you.

![mbim](https://user-images.githubusercontent.com/6677629/67630049-9f4d5780-f857-11e9-81ae-70580366c04d.gif)

### Raster Properties as CSV
The activatepl tab allows the users to either check or activate planet assets, in this case only PSOrthoTile and REOrthoTile are supported because I was only interested in these two asset types for my work but can be easily extended to other asset types. This tool makes use of an existing json file sturctured for use within Planet API or the aoi.json file created earlier

![rasterprop](https://user-images.githubusercontent.com/6677629/67630080-26023480-f858-11e9-882f-79ee37cbce92.gif)

### Raster Copy Iterative
Having metadata helps in organising your asstets, but is not mandatory - you can skip it.
The downloadpl tab allows the users to download assets. The platform can download Asset or Asset_XML which is the metadata file to desired folders.One again I was only interested in these two asset types(PSOrthoTile and REOrthoTile) for my work but can be easily extended to other asset types.

![rastercpy](https://user-images.githubusercontent.com/6677629/67630081-26023480-f858-11e9-9de0-edaf0c8a3cb5.gif)

### Feature Select and Copy
These tools allow the users to iteratively select features using a given SQL expression and then extract that as a new feature class. This can be done iteratively for all feature classes in the folder.

![Ftselect](https://user-images.githubusercontent.com/6677629/67630096-6661b280-f858-11e9-8060-2cf6b9057039.png)

### Select and Calculate Field
This tool allows you to select a field and then recalculate or calculate it based on expressions. The user has the option of simply filling empty fields based on selection of a different field. Meaning I can calculate a field B based on a selection of a seperate field A if I want.

![Ftcalc](https://user-images.githubusercontent.com/6677629/67630095-6661b280-f858-11e9-85c6-7973ffe86627.png)

# Credits
I would like to thank all those who bring me interesting problems to solve, there is little that is needed to keep one inspired.

### Changelog

#### v0.2
- Batch Table to CSV
- Batch Raster to Points
