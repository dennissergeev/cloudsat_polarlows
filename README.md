# Scripts for reading CloudSat data and PL climatology

## CloudSat data
* Data in HDF4 format can be downloaded from [http://www.cloudsat.cira.colostate.edu/](http://www.cloudsat.cira.colostate.edu/)

* HDF4 interface is ugly, so it's better to convert CloudSat files to HDF5 format using the free command line utility [h4h5tools](https://support.hdfgroup.org/products/hdf5_tools/h4toh5/download.html).

For example, running this command:
```bash
h4toh5 2013085084411_36761_CS_2B-GEOPROF_GRANULE_P_R04_E06.hdf
```
produces a file with the same name, but with `.h5` extension.
This file can now be opened by `h5py` library which the scripts in this repository are based on.

* A sample HDF5 file is given in the `data/` directory


## Setting up Python environment
### 1. Install Python distribution using Anaconda
1.1. [Download Anaconda with Python 3.6 for your OS](https://www.anaconda.com/download/)

1.2. Install it following [these instructions](https://docs.anaconda.com/anaconda/install/)

### 2. Get this repository

#### Option 1: Using Git
##### 2.1. Install Git
If you don't have git version control system installed, you can install it following these instructions:
###### Linux
Use your package manager. For example, using aptitude you would run the following terminal command: `sudo apt-get install git`
###### Mac
* The XCode command line tools need to be installed.
* Install XCode if it isn’t already. XCode is available in the Mac App Store for free.
* Launch XCode and accept the license agreement.
* Quit XCode.
* Open a new terminal and run the command xcode-select --install
* Select install on the pop-up menu.

##### 2.2. Clone the repository
2.2.1. Open the command line (terminal or cmd.exe)

2.2.2. (Linux or Mac, optional) Change to a suitable directory (e.g. `/home/yourname/Documents`)

2.2.3. Clone the repo by typing

```
git clone https://github.com/dennissergeev/cloudsat_polarlows.git
```
This should create a local copy of the course materials in the current directory.


#### Option 2: Download ZIP file
Download the materials as a [zip file](https://github.com/dennissergeev/cloudsat_polarlows/archive/master.zip) and unpack it in a suitable directory, for example, in `Downloads` folder.


### 3. Create the environment
3.1. Make sure Anaconda is installed and the course materials are downloaded

3.2. Open the command line (e.g., OS X terminal on Mac; **Anaconda prompt** on Windows)

3.3. Navigate to the cloned / downloaded folder (using `cd` command), for example:

```
cd C:\Users\myname\Downloads\cloudsat_polarlows\
```

3.4. Create the environment using `conda` package manager:

```bash
conda env create -f environment.yml
```
This will take some time depending on your Internet speed (<15 minutes).

### 4. Activate the environment
If your default shell is NOT bash, first type `bash`. Activate the relevant environment by typing:
```bash
source activate cloudsat
```

### 5. Launch Jupyter
Once the environment is activated, type 
```
jupyter notebook
```
in the command line. This should open Jupyter Notebook in your browser. 
