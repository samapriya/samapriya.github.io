# [pydrop: Minimal Python Client for Digital Ocean Droplets](https://github.com/samapriya/pydrop)

[![PyPI version](https://badge.fury.io/py/pydrop.svg)](https://badge.fury.io/py/pydrop)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1323340.svg)](https://doi.org/10.5281/zenodo.1323340)
[![Say Thanks!](https://img.shields.io/badge/Say%20Thanks-!-1EAEDB.svg)](https://saythanks.io/to/samapriya)

This is a minimal tool designed to interact with the Digital Ocean API. This does not translate all functionalities of the API but is a template I created for some of the most common operations I could perform. New tools will be added in the future as I familiarize myself further with the API structure and use as a student. For now this tool allows you to summarize all your droplets running, including and necessarily a price summary to keep tabs on your droplets monthly and hourly rates. The tool also allows you to seach by tags, delete a drop or perfrom actions such as start, stop or shutdown a droplet.

## Table of contents
* [Installation](#installation)
* [Getting started](#getting-started)
* [Digital Ocean Python CLI Tools](#digital-ocean-python-cli-tools)
	* [Digital Ocean Key](#digital-ocean-key)
    * [Account Info](#account-info)
    * [Droplets Info](#droplets-info)
    * [Volume Info](#volume-info)
    * [Snapshot Info](#snapshot-info)
    * [ssh read](#ssh-read)
    * [ssh post](#ssh-post)
    * [ssh delete](#ssh-delete)
    * [Droplets Delete](#droplets-delete)
    * [Droplets Reset](#droplets-reset)
    * [Droplets Action](#droplets-action)


## Installation
This assumes that you have native python & pip installed in your system, you can test this by going to the terminal (or windows command prompt) and trying

```python``` and then ```pip list```

If you get no errors and you have python 2.7.14 or higher you should be good to go. Please note that I have tested this only on python 2.7.15 but can be easily modified for python 3.

To install **Python CLI for Digital Ocean** you can install using two methods

```pip install pydrop```

or you can also try

```
git clone https://github.com/samapriya/pydrop.git
cd pydrop
python setup.py install
```
For linux use sudo.

Installation is an optional step; the application can be also run directly by executing pydrop.py script. The advantage of having it installed is being able to execute ppipe as any command line tool. I recommend installation within virtual environment. If you don't want to install, browse into the pydrop folder and try ```python pydrop.py``` to get to the same result.

![pydrop](https://user-images.githubusercontent.com/25802584/59007392-33a91600-87f4-11e9-867c-22131bb98d32.gif)

## Getting started

As usual, to print help:

```
usage: pydrop [-h]
              {dokey,accinfo,dropinfo,volinfo,snapinfo,sshread,sshpost,sshdelete,dropaction,dropdelete,dropreset}
              ...

Digital Ocean API Python CLI

positional arguments:
  {dokey,accinfo,dropinfo,volinfo,snapinfo,sshread,sshpost,sshdelete,dropaction,dropdelete,dropreset}
    dokey               Enter your Digital Ocean API Key
    accinfo             Prints your account info
    dropinfo            Prints information about all your droplets
    volinfo             Prints information about all your volumes
    snapinfo            Prints information about all your snapshots
    sshread             Prints information about your ssh keys
    sshpost             Adds new ssh keys to account
    sshdelete           Deletes a ssh keys from account
    dropaction          Performs an action on your droplets
    dropdelete          Permanently deletes the droplet
    dropreset           Resets password for the droplet

optional arguments:
  -h, --help            show this help message and exit

```

To obtain help for a specific functionality, simply call it with _help_ switch, e.g.: `pydrop dropinfo -h`. If you didn't install pydrop, then you can run it just by going to *pydrop* directory and running `python pydrop.py [arguments go here]`

## Digital Ocean Python CLI Tools
The Digital Ocean Python CLI and tools setup contains minimal CLI in python to perform basic actions on droplets along with query and analyze your DO enviroment quickly.

### Digital Ocean Key
This tool basically asks you to input your Digital Ocean API Key using a password prompt this is then used for all subsequent tools. This tool now includes an option for a quiet authentication using the API key incase it is unable to invoke an interactive environment such as in Google colaboratory.

```
usage: pydrop dokey [-h] [--key KEY]

optional arguments:
  -h, --help  show this help message and exit

Optional named arguments:
  --key KEY   Your Digital Ocean API Key
```

If using on a private machine the Key is saved as a csv file for all future runs of the tool.

### Droplets Info
This tool prints account info about your account including, droplet and volume limit, your email, and so on. The setup would be

```
pydrop accinfo
```

### Droplets Info
The droplets info tool prints summary info about all your droplets. You can choose to narrow it down further using a droplet tag so only those droplets with speific tags will be printed. Since I wanted the ability of including price summaries, I have included prices summaries.

```
usage: pydrop dropinfo [-h] [--tag TAG]

optional arguments:
  -h, --help  show this help message and exit

Optional named arguments:
  --tag TAG   Use a tag to refine your search
```

### Volume Info
As the name suggest incase you have any volumes attched, this will print information about the volumes attached. If no volumes exists, it will print that and exit out. The setup would be

```
pydrop volinfo
```

### Snapshot Info
This will print information about any existing snapshot that you might have. Setup again is

```
pydrop snapinfo
```

### ssh read
This setup will simply read all your ssh keys and print them including the key, the id , name and so on. Setup would be

```
pydrop sshread
```

### ssh post
This will allow you to add a new ssh key to your existing ssh keys. The required inputs are name and the key

```
usage: pydrop sshpost [-h] --name NAME --keyfile KEYFILE

optional arguments:
  -h, --help         show this help message and exit

Required named arguments.:
  --name NAME        name for ssh key
  --keyfile KEYFILE  file with ssh key
```

### ssh delete
This will delete an ssh key, if no key id is provided, the tool first prints out all the ssh keys and their ids to choose from. Setup with a keyid would be simply

```
pydrop sshdelete
```

The above command will essentially call a sshread function to get you the key ids. If you know the key id the command then takes that as an input

```
usage: pydrop sshdelete [-h] [--keyid KEYID]

optional arguments:
  -h, --help     show this help message and exit

Optional named arguments:
  --keyid KEYID  ssh key id
```

### Droplets Delete
This deletes a droplet and you can specify either the droplet name or id. Incase you don't remember the name or id, just run the tool without any arguments and it will list out all droplet id(s) and names.
```
usage: pydrop dropdelete [-h] [--id ID] [--name NAME]

optional arguments:
  -h, --help   show this help message and exit

Optional named arguments:
  --id ID      Use an image ID to delete droplet
  --name NAME  Use an image name to delete droplet
```

### Droplets Reset
This resets the password of a droplet and you can specify either the droplet name or id. Incase you don't remember the name or id, just run the tool without any arguments and it will list out all droplet id(s) and names.
```
usage: pydrop dropreset [-h] [--id ID] [--name NAME]

optional arguments:
  -h, --help   show this help message and exit

Optional named arguments:
  --id ID      Use an image ID to delete droplet
  --name NAME  Use an image name to delete droplet
```

### Droplets Action
The droplet action tool was designed to achieve and have more control over individual droplet actions and I included actions such as shutdown, power off, power on and rename. Just like the droplet delete tool, this tool will print the name and id of all droplets if no arguments are passed and you can then choose the one on which to perform the action.

```
usage: pydrop dropaction [-h] [--id ID] [--name NAME] [--action ACTION]
                       [--rename RENAME]

optional arguments:
  -h, --help       show this help message and exit

Optional named arguments:
  --id ID          Use an image ID to perform action
  --name NAME      Use an image name to perform action
  --action ACTION  Action type |shutdown="graceful shutdown"|power_off="hard
                   shutdown"|power_on="power on"|rename="rename
  --rename RENAME  Incase you are renaming droplet you can provide new name
```

### Changelog

**v0.0.5**
* Added additional tools like sshfunctions, volume and snapshot reads
* General improvements to overall tool

**v0.0.4**
* Now calculates total cost till date based on active droplets

**v0.0.3**
* Now checks for keys and auto initializes if missing
* Includes password reset tool

