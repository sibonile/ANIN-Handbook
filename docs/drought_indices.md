## General Overview
All the tools developed in this project can be deployed and executed using Command Prompt, Jupyter Notebooks, or Docker. This section of the Handbook follows the previous section and presents a simple workflow for computing the drought indices from Command Prompt. For a more in-depth explanation of the underlying code, see the User Guide. 

The table below shows the drought indices and their corresponding Python prompt.  Except for CDI, the other layers will overwrite the temporal extent.

| Index         | Python Code                                     | Requirements    | 
| :------------ | :---------------------------------------------- | :---------------|
| SMA           | `python -m SMA.SMA_openeo`                      | None            |
| SPI           | `python -m SPI.SPI_openeo`                      | None            |
| SPEI          | `python -m SPEI.SPEI_openeo`                    | None            |
| FAPAR Anomaly | `python -m FAPAR_Anomaly.FAPAR_Anomaly_openeo`  | None            |
| VCI           | `python -m VCI.VCI_openeo`                      | None            |
| CDI           | `python -m CDI.CDI_openeo`                      | Temporal extent |

## Example 1: Standardised Precipitation Index (SPI)
The SPI tool provides monthly time-series information based on precipitation data. It is computed at a national scale at a resolution of 1° x 1° and requires no temporal extent as an input. To run SPI, input the Python code below into the command prompt.
``` py
python -m SPI.SPI_openeo
```
The script will create the output TIFFs in folders labelled `out-xxx` in the SPI folder, which can be visualised in any GIS software.
!!! note ""
    ![alt text](<assets/SPI_ Results_Map.PNG>)

## Example 2: Combined Drought Indicator (CDI)
The CDI tool provides near-monthly time-series information based on Standardised Precipitation Index (SPI), Soil Moisture Anomaly (SMA) and FAPAR anomaly, resulting in maps that can be used for drought watch, warning and alert. This tool does require a temporal extent for performance. To run CDI, input the Python code below into the command prompt. In this example, we use June to December 2022 as our temporal extent.
``` py
python -m CDI.CDI_openeo "2022-06-01" "2022-12-01"
```
As with Example 1, an `out-xxx` folder will be created in the CDI folder, which contains six TIFFs, as shown below. These can be visualised in any GIS software.
!!! note ""
    ![alt text](assets/CDI_Outputs.PNG)   
