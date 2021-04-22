0unitLoadCases/

* T1T2T3.xlsx output by NASTRAN. The rows are the FEA nodes by ID. The nodes on M1 starts with 7, those on M3 starts with 8. The columns are: node ID, CSys ID can be ignored. X, Y, Z of each node. Then there are 156x3 columns left. For each of the 156 unit load cases, there are T1, T2, T3, which give the shift of the node in X, Y, and Z.

* T1T2T3.mat: I saved the above as a Matlab mat file so that it is faster for Matlab to load it.

* node500xxx.csv where xxx is one of the 156 actuator IDs. These give the forces for each balanced unit load cases. There is one actuator with 1000N. The rest of the actuators sum up to -1000N. Each file has two columns. First column is the 500xxx, where xxx is the actuator ID. 2nd column are the forces.

1surfaceNormalBendingModes/  
https://github.com/lsst-sitcom/M1M3_ML/blob/master/data/myUdn3norm_156.mat

* surface normal bending modes. These are obtained by projecting the T1T2T3 data onto surface normal, subtract PTT separately from M1 and M3, then SVD. The variables inside are 'Udn3norm','Vdn3norm','Gdn','x','y','c','annulus'. Udn3norm is 5256x156, each column for 1 bending mode. 5256 is number of FEA nodes. Vdn3norm is 156x156, each column is a force vector for 1 bending mode. x and y give the coordinates of each FEA node. c is the cosine of the angle between the surface normal and z for each FEA node. annulus is a mask, containing 1 or 3, indicating each FEA node is on M1 or M3. The bending modes and forces are normalized so that the each bending mode has a surface RMS of 1um.

2bendingModes/m1m3_Urt3norm.mat

* surface sag bending modes, aka, ray trace bending modes. Most of the time, for people who do not care about the difference between surface sag vs. surface normal vs z-displacement, these are simply known as bendnig modes. These are obtained using results from the surface normal modes: modes = Udn3norm./c, forces are unchanged. The varialbes inside are 'Urt3norm','Vrt3norm','x','y','XACT','YACT'. Urt3norm is 5256x156, each column for 1 bending mode. 5256 is number of FEA nodes. Vrt3norm is 156x156, each column is a force vector for 1 bending mode. x and y give the coordinates of each FEA node. XACT and YACT are the coordinates of each actuator.

The bending modes and forces after the Mirror Lab Testing are found in the M1M3_ML repo (only here, mode 20 is swapped with 27)

https://github.com/lsst-sitcom/M1M3_ML/blob/master/data/M1M3_1um_156_README.txt

m1m3ULdef.xlsx

* This is the original file from Ed Hileman on the X and Y coordinates of the actuators. I've propagated the values to my bending force files. This is just for the record.

ForceActuatorTable.csv

* csv file used to be in the ts_m1m3support repo. (Petr moved the info out of csv, but this csv may be easier to read)

