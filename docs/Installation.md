# Installation

## Requirements
To run the Drought Indices tools, a recent version of Python needs to be installed on your system. First visit [Python.org](https://www.python.org/) to confirm the latest version number. 

You can check the version of Python you have installed by running the following command in Command Prompt
```
python --version
```

## Installing Python
Install Python by downloading an installer appropriate to your system from [python.org](https://www.python.org/)  and running it.

!!! Note ""

    Be sure to check the box to have Python added to your PATH.

    ![alt text](assets/win-py-install.png)

## Clone the ANIN drought indices repository
Open a Command Prompt or a terminal and change the directory to the folder where you will be working from. For this example, we are working from the drive labelled `*K*` in folder located at this directory address `K:\DroughtIndicies`. 

The following prompt will change the directory
```
k:
```
```
cd k:\DroughtIndicies
```

Now that you are in your working folder, you can clone the ANIN drought indices repository using the following prompt:
```
git clone https://github.com/VitoTAP/ANIN-drought-indices
```
All the files that are in the ANIN Drought Indices repository will be cloned to your local machine in your specified working folder. You can easily verify that in Windows Explorer. 

!!! Note ""
    ![alt text](assets/Online2Local.PNG)

In Command Prompt, change the directory again to point to the newly created `ANIN-drought-indices` folder on your PC using the following prompt:
``` 
cd \ANIN-drought-indices
```
## Create a Virtual Environment with Python
To avoid any system conflicts when running the tools, we will create a virtual environment where Python and PIP will run from by running the following prompts:

``` 
python -m venv venv
```
!!! Tip
    If you get an error when creating the virtual environment, adjust the prompt to point to the location of the latest version of the python you installed. It should look like this:
    ```
    path/to/where/python/is/installed/python.exe -m venv venv
    ```
Once the virtual environment is created, we can activate it.
``` 
venv\Scripts\activate.bat
```
## Install pip and other requirements
We can now install pip and the other requirement to run the ANIN drought indices tools.

```
python -m pip install -r requirements.txt
```
Now that all the installations are complete, we can start running the different drought indices tools.

