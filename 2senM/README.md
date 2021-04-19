0bendingModeGridFiles/

*  120 DAT files =   3 (M1, M3, M2) x 20 (modes) x 2 (+ and -)

*  80 gridz files =   2 (M13, M2) x 20 (modes) x 2 (+ and -)

1ZEMAX/LSSTv33_1c1w_As_CornerNoComp_x3_gridSag.zmx

* Zemax file (v3.3, modified to g-band, 500nm only, multi-config for 1.5mm, -1.5mm, and in focus); match to ZEMAX/ZernikeAnnularCoeff.txt before use.

1ZEMAX/LSSTv33_1c1w_As_CornerNoComp_x3_gridSag.CFG

* config file for the above ZEMAX file

1ZEMAX/ZernikeAnnularCoeff.txt

* Zernike Annular Coefficients for 500nm g-band design. Used for verifying the Zemax model has been configured correctly.

2perturbedZernikes/comcam/

* 101 files = 50 (DOFs) x 2 (+ and -) + intrinsic

* each file has 9 rows, for 9 fields, and 24 columns, for z1-z22 then residual RMS and PV RMS

2perturbedZernikes/senM35/

* 101 files = 50 (DOFs) x 2 (+ and -) + intrinsic

* each file has 35 rows, for 9 fields, and 24 columns, for z1-z22 then residual RMS and PV RMS

2perturbedZernikes/senM189/

* 101 files = 50 (DOFs) x 2 (+ and -) + intrinsic

* each file has 189 rows, for 9 fields, and 24 columns, for z1-z22 then residual RMS and PV RMS

3senM/

* sensitivity matrices for comcam, lsst, lsstfam, in both txt and yaml formats


