# Connect-Python-to-Datamine

The script in this repository shows how to connect to Datamine when using Python scripting from a Notebook.<br>
<br>
You will need Sean Horan's DM commands. This folder needs to be in the same folder as your Python file.  There may be other ways to set up the PATH, but creating a folder for your scripts and putting dmcommands in the folder is the easiest.<br>
<br>

This script also requires Michael Prycz's GeostatSpy to read the GSLIB data file. The installation procedure is included.

You need to have an active Datamine license, and Datamine must be open to your project.

The script can be in any file, and the data in the Datamine project folder. It is best to keep all your data and Datamine project files in the same folder; otherwise, file management becomes complicated.

The script runs in Jupyter Notebook/ Jupyter Lab on a local machine. It has not been tested on Google Colab+, Google Drive, or a network.

The Generic Connection Code notebook explains how to set up and test the connection to Datamine Studio EM/RM/RM2+.  IT contains the following:
- How to install Sean Horsn's dmstudio Processes library
- How to edit the dmstudio/initilize.py file for NumPy updates
- How to set up the Datamine connection
- How to test the Datamine connection
- Some examples of commands and processes.

This script has not been tested on all versions of Studio RM. If there are version-specific issues, please let us know.
We recommend opening Datamine manually from the Windows Start menu (not Explorer or another direct method).  The COM connection may not work if you open Studio from Explorer or by directly calling the StudioRM.exe file.

Loading DXF files from the script is possible but causes memory issues in the 3D window; it remains as the LastObjectLoaded, and I have not found a solution in the test version yet.

Not all commands are visible in the COM connection (ie vein-from-samples).  If a command is not working, try recording it as an HTML script.  If that does not work, it will not work in the Python script either.

Datamine is aware of these issues; it just takes time to find errors and fix them.

