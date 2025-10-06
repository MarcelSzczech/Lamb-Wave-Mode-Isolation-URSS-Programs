readme file written on 06/10/2025

These python Jupyter notebooks were written by me (Marcel Szczech) during my 2025 summer URSS project on isolating Lamb waves in an aluminiun plate. Each notebook is thoroughly commented should be 
self explanatory, although here I'll list some important things:

### Brief descsription of each Jupyter notebook ###

'stft testing' 
-> applies a STFT onto a dummy signal made up of a sinusoidal pulse, which I made for proof of concept.

'Mode Isolation' is made up of two cells
-> running the first applies an STFT to a specified signal .txt file, which is assumed to be made up of a time column and then a value column, with no strings. The output is plotted as heatmap. It works for signals of any length.
-> make sure the signal file is accessible by the notebook!

-> the second cell applies an STFT to all the files in a folder (assuming the same structure as was mentioned before) and adds them all together, plotting them onto one heatmap.
-> this cell only works if STFT_array = np.zeros((A,B)) on line 20 is defined as having the same shape as the 'Zxx' array from the first cell, which can be printed from the first cell. I have left it
   for the 'Zxx' array shape I was working with which ultimately depends on the length of your signals. All the signals have to have the same number of data points for this cell to work.

'Rose CH19 heatmap' is made up of two cells
-> running the first plots the FT of a linearly phased EMAT array, the dimensions of which are specified by sliders (equation 19.20 from 'Ultrasonic Guided Waves in Solid Media', J.L. Rose (2014)).
   this cell also calculates the values for the heatmaps of in-plane vs. out-of-plane displacement ratio, but does not plot them yet.

-> running the second cell plots the in-plane vs. out-of-plane displacement ratio heatmaps, with sliders so you can adjust wether you want to consider symmetric or antisymmetric modes.
-> This cell still causes errors such as 'invalid value encountered' and 'overflow' but still plots a heatmap.

### Tips for the use of the programs ###

-> The cursors on the heatmaps can be disabled by comeenting out 'ax.axvline' and 'ax.axhline' lines
-> The scale of the heatmaps can be adjusted by the 'vmax' argument of sb.heatmap
-> The thickness of the plate can be adjusted on line 94 of the first cell of the 'Rose CH19 heatmap' notebook
-> The phase velocity - frequency curves for the modes in the notebooks are FOR ALUMINIUM!
