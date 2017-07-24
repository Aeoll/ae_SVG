# ae_SVG
Python-based assets for importing and exporting SVG files in Houdini

![Hi](TestImage.png)

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
