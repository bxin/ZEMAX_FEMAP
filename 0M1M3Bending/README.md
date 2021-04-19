0M1M3Bending/0unitLoadCase

* T1T2T3.xlsx output by NASTRAN. The rows are the FEA nodes by ID. The columns are: node ID, CSys ID can be ignored. X, Y, Z of each node. Then there are 156x3 columns left. For each of the 156 unit load cases, there are T1, T2, T3, which give the shift of the node in X, Y, and Z.

* node500xxx.csv where xxx is one of the 156 actuator IDs. These give the forces for each balanced unit load cases. There is one actuator with 1000N. The rest of the actuators sum up to -1000N. Each file has two columns. First column is the 500xxx, where xxx is the actuator ID. 2nd column are the forces.

