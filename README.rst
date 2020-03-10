Shoulder Physiotherapy Activity Recognition (SPAR) Data Set
===========================================================

AUTHORS
-------
David Burns, Nathan Leung, Michael Hardisty, Cari Whyne, Stewart McLachlin

University of Toronto
Toronto, Ontario, Canada.

University of Waterloo
Waterloo, Ontario, Canada


CONTACT INFO
------------
David Burns
d.burns@utoronto.ca


DESCRIPTION
-----------
Consists of 6-axis inertial sensor data (accelerometer and gyroscope) collected 
using an Apple Watch 2 and Apple Watch 3 from 20 healthy subjects (40 shoulders), 
as they perform 7 shoulder physiotherapy exercises. 

The activities are: 
0 - Pendulum (PEN)
1 - Abduction (ABD)
2 - Forward elevation (FEL)
3 - Internal rotation with resistance band (IR)
4 - External rotation with resistance band (ER) 
5 - Lower trapezius row with resistance band (TRAP) 
6 - Bent over row with 3 lb dumbell (ROW)

The subjects repeat each activity 20 times on each side (left and right).

The data is available in csv format in the csv folder. Each file represents a single
activity being repeated 20 times. The files are named to convey: 

S1_E0_R : indicated subject 1, activity 0 (PEN), right side

Each file contains 6 axis inertial data collected at 50 Hz. The columns are:

ax, ay, az: 3-axis accelerometer data measured in G
wx, wy, wz: 3-axis gyroscope data measured in rad/s

The data is also available in binary format as a pickled python dictionary in the bin folder.
The binary data can be loaded as follows in python

import numpy as np

d = np.load("SPAR.npy", allow_pickle=True).item()
X, y, subject, side = d['X'], d['y'], d['subject'], d['side']
X_labels, y_labels = d['X_labels'], d['y_labels']


DEMO
----
Demo.ipynb contains python code for loading the data and classifying it using the seglearn library.


CITATION REQUEST
----------------
If using this data in academic publication, please cite the following manuscript: 

D. M. Burns, N. Leung, M. Hardisty, C. M. Whyne, P. Henry, and S. McLachlin, “Shoulder physiotherapy exercise recognition: machine learning the inertial signals from a smartwatch,” Physiol. Meas., vol. 39, no. 7, p. 075007, 2018.

@article{burns_shoulder_2018,
	title = {Shoulder physiotherapy exercise recognition: machine learning the inertial signals from a smartwatch},
	volume = {39},
	issn = {0967-3334},
	shorttitle = {Shoulder physiotherapy exercise recognition},
	doi = {10.1088/1361-6579/aacfd9},	
	language = {en},
	number = {7},
	journal = {Physiological Measurement},
	author = {Burns, David M. and Leung, Nathan and Hardisty, Michael and Whyne, Cari M. and Henry, Patrick and McLachlin, Stewart},
	year = {2018},
	pages = {075007}
}





