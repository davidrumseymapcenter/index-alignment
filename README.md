# Spatial Indexes Alignment for Insurance Atlases
This is a working repository for prepping and aligning polygons in geojson spatial index files. 


# Prepping geojson files for Alignment (Work in Progress)
1. Drag and drop the completed geojson file into [geojson.io](https://geojson.io).
2. For each outlined polygon, check that there is a corresponding vertex point relative to those of the bordering polygons. Below is an example: the orange polygon is missing a vertex at the point where it meets with the two bordering blue polygons.
<img width="424" alt="Screenshot 2024-11-07 at 9 28 43 AM" src="https://github.com/user-attachments/assets/55257055-2921-446c-b52e-4c130be27206">

3. For each of these missing verticies, use the edit tool to add a new vertex. Click the edit tool, click on the polygon you'd like to edit, click the small orange dot at the midpoint of the polygon's edge, and then drag it to align with the bordering polygons' verticies.
4. When you are finished prepping the geojson file, save it following the convention `prepped_[atlas]_[city]_vol[volume number]_[year of the atlas].geojson`
5. Upload the file to the spatial-indexes repository.



# Aligning Index Points (Work in Progress)
1. If you have not done so already, you will need to install python and Visual Studio Code. You can download the python installer from [this page](https://www.python.org/downloads/) and the Visual Studio Code installer from [this page](https://code.visualstudio.com/Download).
2. Crete a new folder on your computer named _spatial-index-alignment_.
3. Download _alignment-script.py_ and move it to your new folder.
4. Open your _spatial-index-alignment_ folder in Visual Studio Code. [^1]
5. Open the Terminal below the script (View > Terminal) and set up a virtual environment: [^2]\
`python -m venv .index-alignment-venv`
7. Open a **new** Terminal (Terminal > New Terminal) and use `pip install` to install the following packages: [^3]
  - `pip install geopandas`
  - `pip install scipy`
9. Download the spatial index .geojson file you want to align and move it to your _spatial-index-alignment_ folder.
10. Open _alignment-script.py_ in VS Code and replace *input_file_name_here.geojson* with the name of your spatial index file.
12. Replace *output_file_name_here.geojson* to name the file that will be created. Follow the convention `aligned_[atlas]_[city]_vol[volume number]_[year of the atlas].geojson`
13. Run the script and upload the resulting file to the spatial-indexes repository.

[^1]:If you haven't already, you may want to install the VS Code python extension. Upon opening the script for the first time, a popup may appear asking if you would like to install the extension. Alternatively, you can install it from the Extensions Sidebar Tab (Shift+Command+X). This is not required to run the script.
[^2]:If you get "command not found" errors using the `python` and `pip` commands, try using `python3` and `pip3` instead. This will depend on your operating system, python installation version, etc. More info can be found [here](https://www.reddit.com/r/learnpython/comments/mf7t0n/why_python3_in_command_prompt_vs_python/).
[^3]:This script requires four total packages to run properly: geopandas, shapely, numpy, and scipy. You won't need to individually install shapely and numpy as they are dependencies of geopandas and are included in your geopandas installation.
<!-- [^4]:Note about setting equivalent python versions in VS Code -->
