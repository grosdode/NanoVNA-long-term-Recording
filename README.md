# Simple recording from NanoVNA
Records data from the NanoVNA with its current settings (long term observation). Calibration, sweep frequencies etc. have to be set by hand at the NanoVNA.<br>
inspired by Github -> ttrftech/NanoVNA/python/nanovna.py

## Usage
change the settings in the file "collectData.py" to your needs:

    # settings 
    INTERVAL = 10          # measure interval in s (> 6)
    REPEAT = 3             # number of measurements, 0 = infinite
    FILE_NAME = "VNA_Data" # file name, _Y_m_d-H_M_S will be added 

<code>INTERVAL</code> is the interval (in seconds) in which the script ask the NanoVNA for new data. It takes some time to read the data from the VNA. Especially if the VNA starts a new sweep right before. If the interval is to short it will be ignored and you get irregular time intervals.<br>
<code>REPEAT</code> is the number of measurements to perform. 0 will cause *infinity* measurements. Example: <code>INTERVAL = 10</code> and <code>REPEAT = 3</code> will create a file with 3 measurement sweeps over a time of 10 <span>&#183;</span> 3 = 30 seconds. <br>
<code>FILE_NAME</code> is the name of the file to store the data. A time stamp (_Y_m_d-H_M_S) will be created and added to the file name to prevent overwriting data and for documentation purposes.

The Jupyter notebook can be used to play around: *collectData.ipynb*