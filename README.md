# ae_SVG
Python-based assets for importing and exporting SVG files in Houdini

![Hi](TestImage.png)

# Installation
The importer uses the svg.path library - https://pypi.python.org/pypi/svg.path
To ensure Houdini has access to this library:
- Install Python2.7
- Install pip, the python package manager - https://bootstrap.pypa.io/get-pip.py
~~- Run 'pip install svg.path' which will install svg.path into Python27\Lib\site-packages~~
- Run 'pip install svg.path --target [path/to/houdini/home/python2.7libs] ' which will install svg.path into the Houdini custom python library director (e.g C:/Users/User/Documents/houdini16.0/python2.7libs )
- **Create an empty \_\_init\_\_.py file inside the svg/ directory of the svg/path installation**
- ~~In your houdini.env file, append the site-packages directory to the python search path, e.g `PYTHONPATH = &;C:\Python27\Lib\site-packages`~~
~~- Setting PYTHONPATH in the houdini.env file apparently breaks some python modules that come with Houdini.~~

# Importer
A digital asset which can load SVG files into SOPs.
Features:
- Supports Line, Polyline, Polygon, Circle, Rect and Path elements (Cubic bezier paths - open or closed)
- Supports Compound shapes
- Loads Fill, Stroke, Stroke-Weight and Opacity data and stores these as Primitive attributes
- Options for outlining strokes, hole-ing compound shapes and converting bezier curves to polygons

Current Limitations:
- Does not support clipping paths (Produces Error)
- Does not support group tags <g>

# Exporter
A digital asset which can save the contents of a Houdini scene to SVG format
- A work-in-progress which is currently limited to polygons and polylines. Usable but not guaranteed stable.
- 2 digital assets: SVG_Export and SVG_ProcessAndExport. The latter performs geometry cleanup, camera projection and culling before as well as exports. 
