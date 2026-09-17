# Connect Python to Datamine

This repository provides example code for connecting Python to **Datamine Studio** from a Jupyter Notebook, JupyterLab, or VS Code environment.

The connection uses Sean Horan's **dmstudio** Python library:

https://github.com/seanhoran/dmstudio

Once installed correctly, `dmstudio` can be imported into Python scripts or notebooks and does **not** need to be located in the same folder as your Python files.

## Requirements

You will need:

- A valid Datamine licence.
- Datamine Studio installed locally.
- An active Datamine project open in Studio.
- Python running locally on the same Windows machine.
- Sean Horan's `dmstudio` library.

We recommend opening **Datamine Studio manually from the Windows Start menu**, then opening the required project before running the Python connection.

During testing, the COM connection has not always worked correctly when Studio was opened from Windows Explorer, by opening a `.rmproj` file directly, or by calling `StudioRM.exe` programmatically.

## File Locations

The Python script or notebook can be stored in any folder.

For simplicity, it is recommended that the Datamine project and associated data files are kept together in the Datamine project folder. Using files distributed across multiple folders is possible, but file and path management becomes more complicated.

## Tested Environments

The connection has been tested locally using:

* Jupyter Notebook
* JupyterLab
* VS Code

It has **not** been tested with:

* Google Colab
* Google Drive-based workflows
* Network-based Python environments

Because the connection uses Windows COM automation, it is intended primarily for Python running locally on the same computer as Datamine Studio.

## Generic Connection Code

The **Generic Connection Code** notebook explains how to configure, connect to, and test Datamine Studio from Python.

It includes:

* Installing Sean Horan's `dmstudio` library.
* Accessing Datamine processes such as `MGSORT`, `HOLES3D`, and others.
* Updating the `dmstudio/initialize.py` file where required for newer NumPy versions.
* Establishing the Datamine COM connection.
* Checking that an active Datamine project is available.
* Testing the connection.
* Examples of Datamine commands and processes called from Python.

The connection approach is intended for use with Studio RM / RM2+ and related Studio applications, subject to the interfaces available in each Datamine version.

## Version Compatibility

The scripts have not been tested against every version of Datamine Studio.

COM behaviour and available commands may differ between Studio versions. If you encounter a version-specific problem, please report the Datamine version and the command or process that is failing.

## Known Limitations

### DXF Files

DXF files can be loaded from Python, but testing has identified problems with subsequent handling of the loaded 3D object.

The DXF may remain as the last object added (LastOBjectAdded) to the Studio 3D environment, and operations such as `SaveAsDatamineFile()` may not behave as expected. Additional problems with object state and memory within the 3D window have also been observed.

A reliable solution has not yet been identified for the versions tested.

### Commands Not Exposed Through COM

Not every Datamine command is available through the Studio COM interface.

For example, some commands such as `vein-from-samples` may not be accessible from Python.

If a command does not work through the COM connection, try recording and running the operation as a Datamine HTML script. If the command cannot be executed through the HTML scripting interface, it is unlikely to be accessible from the Python COM connection.

## Important

This repository demonstrates a practical working connection between Python and Datamine Studio. It should not be assumed that every Studio command, object type, or workflow can be automated through COM.

Datamine is aware of a number of scripting and COM-related limitations. These interfaces continue to evolve, and behaviour may change between software versions.

If you identify a problem, workaround, or version-specific issue, please raise it through the repository so that the information can be shared with other users.


