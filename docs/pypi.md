# **PyPI Releases**
I have successfully converted some of the github projects into PyPI projects for allowing easier installation and usage. Some of these have been tested for compatibility with Google Colaboratory and for building within a Docker image. Currently maintained pypi projects include

<center>![pypi_icon](https://user-images.githubusercontent.com/6677629/67454996-24d3cc00-f5fa-11e9-95a6-db9f52b4af96.jpg)</center>

#### porder: Simple CLI for Planet ordersV2 API
[![PyPI version](https://badge.fury.io/py/porder.svg)](https://badge.fury.io/py/porder)

Ordersv2 is the next iteration of Planet's API in getting Analysis Ready Data (ARD) delivered to you. Orders v2 allows you to improved functionality in this domain, including capability to submit an number of images in a batch order, and perform operations such as top of atmospheric reflectance, compression, coregistration and also enhanced notifications such as email and webhooks. Based on your access you can use this tool to chain together a sequence of operations. This tool is a command line interface that allows you to interact with the ordersv2 API along with place orders and download orders as needed. The tool also allows you to chain multiple processes together and additional functionalities will be added as needed.

<center>
``` js
pip install porder
```
</center>

#### satadd: CLI pipeline for Planet, Satellogic, Google Earth Engine and Digital Globe Imagery
[![PyPI version](https://badge.fury.io/py/satadd.svg)](https://badge.fury.io/py/satadd)

This tool was built with a focus on the same issues and borrow parts from my other projects such as [ppipe](https://pypi.org/project/ppipe/) for handling Planet's datasets, [gee2drive](https://pypi.org/project/gee2drive/) to handle download collections already available in Google Earth Engine (GEE), [pygbdx](https://pypi.org/project/pygbdx/) which is a relatively new project to explore Digital Globe assets and I have now integrated tools to access and download Satellogic imagery. Core components from a lot of these tools have gone into building [satadd](https://pypi.org/project/satadd/) based on the idea of adding satelite data as needed. These tools include authentications setups for every account, and access to datasets, metadata among other tools. This was not build however for heavy lifting though I have tested this on hundreds and thousands of assets delivery so it behaves robustly for now. The tool is build and rebuilt as companies change their authentication protocal and delivery mechanisms and allow for improving many aspects of data delivery and preprocessing in the next iterations.

<center>
``` js
pip install satadd
```
</center>

#### Planet-Mosaic-Quads-Download-CLI
[![PyPI version](https://badge.fury.io/py/pbasemap.svg)](https://badge.fury.io/py/pbasemap)

Planet creates global monthly mosaics apart from creating mosaics at different frequencies, monthly mosaics are of interest to a lot of people who would like to do a consistent time series analysis using these mosaics and would like to apply them to an existing analytical pipeline. I created this tool to allow you pass single or multiple geometries in a folder for the tool to find the mosaic quads and then process and download it. For now the geometry is passed as a geojson file, but I have included a tool for you to convert any shapefile into geojson files so you can use this tool. In the future I will add support for kml and json files as well.

<center>
``` js
pip install pbasemap
```
</center>

#### geeup: Simple CLI for Google Earth Engine Uploads
[![PyPI version](https://badge.fury.io/py/geeup.svg)](https://badge.fury.io/py/geeup)

This came of the simple need to handle batch uploads of both image assets to collections but also thanks to the new table feature the possibility of batch uploading shapefiles into a folder. Though a lot of these tools including batch image uploader is part of my other project geeadd which also includes additional features to add to the python CLI, this tool was designed to be minimal so as to allow the user to simply query their quota, upload images or tables and also to query ongoing tasks and delete assets. I am hoping this tool with a simple objective proves useful to a few users of Google Earth Engine.

<center>
``` js
pip install geeup
```
</center>

#### gee2drive: Google Earth Engine to Drive Export Manager
[![PyPI version](https://badge.fury.io/py/gee2drive.svg)](https://badge.fury.io/py/gee2drive)

I created this tool which allows you to run a terminal environment where your personal and general catalog images are part of a autosuggest feature. This tool allows you to look for images based on names for example " you can search for Sentinel and it will show you full path of images which have the word sentinel in the title". It also creates a report for your image collections and images so apart from the public datasets this can also find your own datasets as well. You can then generate bandlist to make sure all bands you are exporting are of the same type and then export all images that intersect you aoi.

<center>
``` js
pip install gee2drive
```
</center>

#### Planet API Pipeline & Google Earth Engine Batch Assets Manager with Addons
[![PyPI version](https://badge.fury.io/py/ppipe.svg)](https://badge.fury.io/py/ppipe)

The tool allows the user to upload Planet assets to Google Earth Engine from your local system. The tool has been modified and tested in Docker environment and Colab environments. It makes use of the manifest feature of image upload so that it can choose image and asset type appropriately. It also figures out property type automatically to avoid conflict in metadata property type in successive images. You can read more about the [project here](https://samapriya.github.io/projects/planet_gee_pipeline_cli/)

<center>
``` js
pip install ppipe
```
</center>

#### pydrop: Minimal Python Client for Digital Ocean Droplets
[![PyPI version](https://badge.fury.io/py/pydrop.svg)](https://badge.fury.io/py/pydrop)

This is a minimal tool designed to interact with the Digital Ocean API. This does not translate all functionalities of the API but is a template I created for some of the most common operations I could perform. New tools will be added in the future as I familiarize myself further with the API structure and use as a student. For now this tool allows you to summarize all your droplets running, including and necessarily a price summary to keep tabs on your droplets monthly and hourly rates. The tool also allows you to seach by tags, delete a drop or perfrom actions such as start, stop or shutdown a droplet.

<center>
``` js
pip install pydrop
```
</center>

#### **Planet Clip-Ship Tools CLI**
[![PyPI version](https://badge.fury.io/py/pclip.svg)](https://badge.fury.io/py/pclip)

The [Clips API has been deprecated](https://developers.planet.com/changelog) and will no longer be supporting the standalone Clip and Ship service. Deprecation means that there is intention to remove the service at some point; it DOES NOT mean end-of-life for the service, yet. (Deprecate and end-of-life are two distinct terms.) There should be a plan to replace Clips API with new pre-processing functionality, but no new announcement or timetable for the launch of the new service and the removal (end-of-life) for Clips API has been made. Planet’s Clip API was a compute API designed to allowed users to clip the images to their area of interest. This would save them time in preprocessing and also allow the user to save on their area quota which might have restrictions. You can read more about the [project here](https://samapriya.github.io/projects/clip_ship_planet_cli/)

<center>
``` js
pip install pclip
```
</center>

#### **Google Earth Engine Batch Assets Manager with Addons**
[![PyPI version](https://badge.fury.io/py/geeadd.svg)](https://badge.fury.io/py/geeadd)

Google Earth Engine Batch Asset Manager with Addons is an extension of the existing CLI and additional tools were added to include functionality that was missing from the EarthEngine CLI. This includes printing quota, moving and batch copying images, print asset report and task lists to name a few of the features. It is developed case by case basis to include more features in the future as it becomes available or as need arises.You can read more about the [project here](https://samapriya.github.io/projects/gee_asset_manager_addon/)

<center>
``` js
pip install geeadd
```
</center>

#### **Google Takeout and Transfer: Tools and Guide for Code and Asset Transfer**
[![PyPI version](https://badge.fury.io/py/geetakeout.svg)](https://badge.fury.io/py/geetakeout)

This tool replicates a Google Earth Engine account and transfer everything over to a new account. Even if you are not replicating your account, think of this as an add on which allows you to download your entire code repositories, create an asset report and best of all iteratively change permissions to all image-collection and images whether or not within a folder.You can read more about the [project here](https://github.com/samapriya/gee-takeout)

<center>
``` js
pip install geetakeout
```
</center>
