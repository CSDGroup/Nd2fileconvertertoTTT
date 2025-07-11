# Nd2fileconvertertoTTT
A tool that converts nd2 file format in to a tTt readable file for manual tracking

**Repository Structure**

environment.yml           # Conda environment specification

gitignore                # Files and folders to ignore in Git

README.md                 # Project overview and instructions

Metadataextractionnd2.py  # Metadata extraction and CSV generation

ND2imageextraction.py     # Extract images using ND2 plugin

ND2filecreatecomposite.py # Create composite images across channels

nd2to8bitpng.py           # Convert images to 8-bit PNGs with adjustable black/white points

Adjustblackwhitepoints.py # GUI for interactively setting black/white points

TATexp.py                 # Generate TATexp XML for downstream analysis

ImportOpenBIS.py          # Authenticate and upload data to OpenBIS

Masterscript.py           # Qt5-based master application wrapping the full pipeline

myscript.bat              # Windows batch file for launching the pipeline

Features

Metadata Extraction: Parse and flatten ND2 metadata into CSV and HTML summaries.
Image Extraction: Extract middle Z-stack and first/last timepoints per position.
Composite Generation: Automatically tile position images per channel.
Contrast Adjustment: Interactive GUI to set black/white points per channel.
8-bit Conversion: Batch convert high-bit images to PNG with compression options.
OpenBIS Integration: Authenticate, create experimental steps, and upload datasets.
Master Application: Qt5 interface guiding through each pipeline step.

Requirements

Python 3.8+
nd2reader
tifffile
scikit-image
Pillow
OpenBIS Python API (pybis)
PyQt5
All dependencies are listed in environment.yml for Conda.

Installation

git clone https://github.com/CSDGroup/Nd2fileconvertertoTTTgit
cd nd2-processing-pipeline

conda env create -f environment.yml
conda activate nd2-pipeline


Usage

**1. Metadata Extraction**
python Metadataextractionnd2.py
Follow the file dialog to select an ND2 file; metadata CSV and HTML description will be saved in an _analysis folder.

**2. Image Extraction**
python ND2imageextraction.py
Extracts grayscale TIFFs for each position and channel.

**3. Composite Images**
python ND2filecreatecomposite.py
Tiles one representative image per position into a grid for each channel.

**4. Adjust Black/White Points**
python Adjustblackwhitepoints.py
Interactively set min/max for each channel; results saved to black_white_points.json.

**5. 8-bit PNG Conversion**
python nd2to8bitpng.py
Batch converts ND2 frames to 8-bit PNGs using specified black/white points.

**6. Generate TATexp XML**
python TATexp.py
Creates *_TATexp.xml for downstream analysis pipelines.

**7. Upload to OpenBIS**
python ImportOpenBIS.py
Authenticates and uploads metadata CSV and composite images to your OpenBIS server.

**8. Master GUI Application**
python Masterscript.py
Launch the Qt5-based interface for end-to-end pipeline control.

**Contributing**
Fork the repository
Create a feature branch
Commit your changes
Open a Pull Request
