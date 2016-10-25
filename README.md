# landsatmtlparser

Parser for Landsat metadata files.

## Installation

This package can be installed using pip:

    pip install landsatmtlparser

or directly from source:

    python setup.py install


## Usage

```python
from landsatmtlparser import LandsatMetadataParser

# initialize parser
parser = LandsatMetadataParser()

# load file
parser.read("landsat_scene_MTL.txt")

# load ORIGIN parameter from group L1_METADATA_FILE -> METADATA_FILE_INFO
origin = parser.getstring(["L1_METADATA_FILE", "METADATA_FILE_INFO"], "ORIGIN")

# load CLOUD_COVER parameter from group L1_METADATA_FILE -> IMAGE_ATTRIBUTES
cloud_cover = parser.getfloat(["L1_METADATA_FILE", "IMAGE_ATTRIBUTES"], "CLOUD_COVER")

# return a list of (name, value) pairs for each parameter in a group
items = parser.items(["L1_METADATA_FILE", "PRODUCT_METADATA"])

```