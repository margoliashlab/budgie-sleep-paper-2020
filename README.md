# budgie-sleep-paper-2020

Code used to generate analyses and figures for the 2020 paper *Budgerigars have complex sleep structure similar to that of mammals* (Canavan & Margoliash, PLoS Biology):

https://journals.plos.org/plosbiology/article/authors?id=10.1371/journal.pbio.3000929


## Code format
Written in Python 3.7.1.

Jupyter notebooks (.ipynb).

The add-on "Table of Contents" is recommended for optimal viewing.

## To install required packages:
* *Note: not all packages needed for all scripts.*
1. Create a new conda environment (optional but recommended):
```
conda create -n budgies
conda activate budgies
```

2. Use pip to install libraries in downloaded requirements.txt file:
```
pip install -r requirements.txt
```

3. Install the *resin* library (https://github.com/margoliashlab/resin):
```
git clone https://github.com/margoliashlab/resin
cd resin
pip install .
```

4. *(If ephys data are in .arf format)*

Install the *arf* library following instructions at https://github.com/margoliashlab/arf


## Input formats
* **EEG/EOG data**: .arf files
  * a form of hdf5 container
  * specifications at https://github.com/margoliashlab/arf)
  * each channel as a separate subfile
* **Video and sleep scores**: .csv files with the following headers:
  * ***(blank column name)***: date/timestamp
  * **Video Label**: m = moving wake, q = quiet wake, d = drowsy, s = sleep (including unihemispheric), u = unclear
  * **Label**: w = wake, d = drowsy, u = unihem sleep, i = intermediate sleep, s = SWS, r = REM, l = left unihemispheric sleep, g = right unihemispheric sleep
  * **Label (#)**: 0 = wake, 1 = drowsy, 2 = unihem sleep, 3 = intermediate sleep, 4 = SWS, 5 = REM
  * **Time (s)**: time from beginning of recording in seconds
  * **Time (h)**: time from beginning of recording in hours
  * **Zeitgeber time (s)**: time relative to lights on in seconds
  * **Zeitgeber time (h)**: time relative to lights on in hours
  * **Zeitgeber time (ep)**: time relative to lights on in number of epochs (3-second epochs used)
  * **Epoch #**: number of epochs relative to beginning of recording (3-second epochs used)
