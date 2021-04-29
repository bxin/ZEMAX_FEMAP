0unitLoadCases/

* T1T2T3.csv output by NASTRAN. The rows are the FEA nodes by ID. The columns are: node ID, CSys ID can be ignored. X, Y, Z of each node. Then there are 72x3 columns left. For each of the 72 unit load cases, there are T1, T2, T3, which give the shift of the node in X, Y, and Z.

* T1T2T3.mat: I saved the above as a Matlab mat file so that it is faster for Matlab to load it.

* nodex00000yy.csv where the x and yy indicate which actuator. For the B,C,and D ringes, x=2,3,4 respectively. Then yy goes from 1 to the total number of actuators on that ring. For example, the unit load case for B5 can be found in node20000005.csv. These give the forces for each balanced unit load cases. There is one actuator with 1000N. The rest of the actuators sum up to -1000N. Each file has two columns. First column is the x00000yy, like in the file name. 2nd column are the forces.

1surfaceNormalBendingModes/  
https://github.com/lsst-sitcom/M2_FEA/blob/master/data/M2_Udn3norm.mat

* surface normal bending modes. These are obtained by projecting the T1T2T3 data onto surface normal, subtract PTT, then SVD. The variables inside are 'Udn3norm','Vdn3norm','Gdn','x','y','c','actID','XACT','YACT','nodeID'. Udn3norm is 15984x72, each column for 1 bending mode. 15984 is number of FEA nodes. Vdn3norm is 72x72, each column is a force vector for 1 bending mode. x and y give the coordinates of each FEA node. c is the cosine of the angle between the surface normal and z for each FEA node. actID are the actuator ID numbers, in the format of x00000yy (see above). XACT and YACT are actuator coordinates in M2 CS, in meters. nodeID are the FEA node ID numbers. The bending modes and forces are normalized so that the each bending mode has a surface RMS of 1um.

2bendingModes/M2_Urt3norm.mat

* surface sag bending modes, aka, ray trace bending modes. Most of the time, for people who do not care about the difference between surface sag vs. surface normal vs z-displacement, these are simply known as bending modes. These are obtained using results from the surface normal modes: modes = Udn3norm./c, forces are unchanged. The varialbes inside are 'Urt3norm','Vrt3norm','x','y','XACT','YACT'. Urt3norm is 15984x72, each column for 1 bending mode. 15984 is number of FEA nodes. Vrt3norm is 72x72, each column is a force vector for 1 bending mode. x and y give the coordinates of each FEA node, in M2 CS. XACT and YACT are the coordinates of each actuator.

The bending modes and forces in txt format are found in the M2_FEA repo (only here, we swapped 18,19,20 for 26,27,28, out of symmetry considerations.)

https://github.com/lsst-sitcom/M2_FEA/blob/master/data/M2_1um_72_README.txt

M2actuatorNodesXY_M2_FEA_CS.txt

* This is the original file on the X and Y coordinates of the actuators, directly out of FEMAP. The unit is inches. I've propagated the values (in meters) to my bending force files. This is just for the record.


