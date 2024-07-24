# Quick Overview
Here is a simple workflow using examples locations and dates, that will aid you to access the ANIN drought indicies through Jupyter Notebook. After completing the steps below, you should be able to adjust the location with your own coordinates and date ranges where applicable.

### Clone the repository into Jupyter Notebook

Begin by importing the ANIN-drought-indices into Jupyter Notebook using the `Git Clone` button.

!!! tip ""
      
    ![alt text](assets/JN_CloneRepo.PNG)

A folder containing the ANIN-drought-indices will be created. 

### Setup and Testing

Open the respository and double click `setup_and_test.ipynb`. It will open in a new tab and require you to 'Restart the kernal and run all cells (under `Run` in the menu).
Jupyter Notebook will install all the requirements to run the code followed by a sample test query, which requests a Sentinel-2 image over The Innovation Hub in Pretoria, South Africa.

!!! tip ""
      
    ![alt text](assets/JN_TestResults.PNG)

### Edit the spatial and temporal extent

Within the code block, you can change the location to that of your chosing and adjust the date range for the image search by changing the values in the highlighted lines shown below.

``` py hl_lines="7 8 9 10 11 18"
import openeo
from openeo.processes import process

url = "https://openeo.cloud"
connection = openeo.connect(url).authenticate_oidc()

spatial_extent_sansa = {
    "east": 28.275,
    "north": -25.740,
    "south": -25.755,
    "west": 28.260,
}

datacube = connection.load_collection(
    collection_id="SENTINEL2_L2A",
    bands=["B04", "B03", "B02"],
    spatial_extent=spatial_extent_sansa,
    temporal_extent=["2024-03-05", "2024-03-07"],
)
# Scale values for better visualisation
datacube = datacube / 2500

datacube.download("out-Pretoria.tiff")
```