# r²SCANX-D4


## Functional Implementation

- r²SCANX-D4 is available in Orca
- r²SCAN can be used with [libxc version 5.1.0](https://www.tddft.org/programs/libxc/changes/#510---2021-01-19) as `MGGA_X_R2SCAN` (id=497), `MGGA_C_R2SCAN` (id=498)
- [XCFun 2.1.0](https://github.com/dftlibs/xcfun/releases/tag/v2.1.0) also implements support for the r²SCAN functional
- routines for r²SCAN functional implementation can be found at https://gitlab.com/dhamil/r2scan-subroutines (Fortran), routines for Vasp are included
- Libraries implementing DFT-D4 can be found at https://github.com/dftd4/dftd4 (Fortran) and https://github.com/dftd4/cpp-d4 (C++)


## Functional parameters

| method | s6 | s8 | s9 | a1 | a2/Bohr |
| --- | --- | --- | --- | --- | --- |
| r²SCANh-D4(EEQ)-ATM/def2-QZVP | 1 | 0.8324 | 1 | 0.4944 | 5.9019|
| r²SCAN0-D4(EEQ)-ATM/def2-QZVP | 1 | 0.8992 | 1 | 0.4778 | 5.8779 |
| r²SCAN50-D4(EEQ)-ATM/def2-QZVP | 1 | 1.0471 | 1 | 0.4574 | 5.8969 |
| r²SCANh-D4(EEQ)-ATM/def2-TZVPP | 1 | 0.9119 | 1 | 0.4832 | 6.2073 |
| r²SCAN0-D4(EEQ)-ATM/def2-TZVPP | 1 | 0.9397 | 1 | 0.4578 | 6.1864 |
| r²SCAN50-D4(EEQ)-ATM/def2-TZVPP | 1 | 1.0576 | 1 | 0.4232 | 6.2378 |


| method | b |
| --- | --- |
| r²SCANh-VV10 | - |
| r²SCAN0-VV10 | - |
| r²SCAN50-VV10 | - |

## Benchmark Results

### NCIBLIND ToDO

Statistics in kcal/mol, Gini coefficients are dimensionless.

| method | MD | MAD | RMSD | SD | Gini |
| --- | ---:| ---:| ---:| ---:| ---: |
| r²SCAN-D4-ATM/def2-QZVP | –0.05 | 0.17 | 0.29 | 0.29 | 0.64 |
| r²SCANh-D4-ATM/def2-QZVP | -0.059 | 0.179 | 0.316 | 0.313 | |
| r²SCAN0-D4-ATM/def2-QZVP | -0.071 | 0.200 | 0.357 | 0.353 | |
| r²SCAN50-D4-ATM/def2-QZVP | -0.102 | 0.256 | 0.460 | 0.451 | |


### S22x5 ToDO

Statistics in kcal/mol, Gini coefficients are dimensionless.

| method | MD | MAD | RMSD | SD | Gini |
| --- | ---:| ---:| ---:| ---:| ---: |
| r²SCAN-D4-ATM/def2-QZVP | –0.12 | 0.28 | 0.51 | 0.50 | 0.65 |
| r²SCANh | -0.155 | 0.303 | 0.565 | 0.546 | |
| r²SCAN0 | -0.199 | 0.353 | 0.658 | 0.630 | |
| r²SCAN50 | -0.282 | 0.466 | 0.859 | 0.815 | |

### S66x8 ToDO

Statistics in kcal/mol, Gini coefficients are dimensionless.

| method | MD | MAD | RMSD | SD | Gini |
| --- | ---:| ---:| ---:| ---:| ---: |
| r²SCAN-D4-ATM/def2-QZVP | –0.09 | 0.23 | 0.38 | 0.36 | 0.56 |
| r²SCANh | -0.112 | 0.244 | 0.406 | 0.391 | |
| r²SCAN0 | -0.133 | 0.274 | 0.463 | 0.444 | |
| r²SCAN50 | -0.180 | 0.352 | 0.600 | 0.573 | |


### GMTKN55

Statistics in kcal/mol.

| method | WTMAD-2 | basic | react. | barriers | inter. NCI | intra. NCI | NCI |
| --- | ---:| ---:| ---:| ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVP | 7.54 | 5.55 | 8.26 | 14.29 | 7.46 | 5.74 | 6.62 |
| r²SCANh-D4/def2-QZVP | 6.23 | 4.42 | 7.26 | 11.10 | 6.34 | 4.97 | 5.67 |
| r²SCAN0-D4/def2-QZVP | 5.67 | 5.04 | 6.80 | 7.60 | 5.63 | 4.53 | 5.09 |
| r²SCAN50-D4/def2-QZVP  | 6.28 | 6.60 | 8.49 | 5.97 | 5.32 | 5.14 | 5.23 |


| method | WTMAD-1 | basic | react. | barriers | inter. NCI | intra. NCI | NCI |
| --- | ---:| ---:| ---:| ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVP | 4.43 | 4.46 | 4.85 | 6.15 | 3.87 | 3.33 | 3.64 |
| r²SCANh-D4/def2-QZVP | 3.80 | 3.89 | 4.21 | 4.95 | 3.41 | 2.82 | 3.15 |
| r²SCAN0-D4/def2-QZVP | 3.51 | 3.92 | 3.94 | 3.73 | 3.19 | 2.48 | 2.89 |
| r²SCAN50-D4/def2-QZVP  | 3.81 | 4.40 | 4.86 | 3.10 | 3.22 | 2.91 | 3.09 |

The MADs of all GMTKN55 subsets in kcal/mol are given here.
Values for TPSS-D4, PBE-D4 and PBE0-D4 are taken from Caldeweyher et al. *J. Chem Phys*, **2019**, 150, 154122. DOI: [10.1063/1.5090222](https://doi.org/10.1063/1.5090222). Values for r²SCAN-D4 are taken from Ehlert et al. *J. Chem. Phys.* **2021**, 154, 061101. DOI: [10.1063/5.0041008](https://doi.org/10.1063/5.0041008)

| subset | r²SCAN-D4 | r²SCANh-D4 | r²SCAN0-D4 | r²SCAN50-D4  | TPSS-D4 | PBE-D4 | PBE0-D4 | 
| --- | ---:| ---:| ----:| ---:| ---:| ---:| ---:|
| W4-11 | 3.86 | 4.58 | 11.35 | 22.62 | 5.89 | 15.62 | 3.67 | 
| G21EA | 5.64 | 3.93 | 4.61 | 6.00 | 2.12 | 3.59 | 2.57 | 
| G21IP | 4.77 | 4.57 | 4.76 | 5.32 | 3.87 | 3.80 | 3.64 | 
| DIPCS10 | 5.05 | 4.64 | 4.55 | 5.71 | 3.28 | 4.22 | 2.84 | 
| PA26 | 2.51 | 2.46 | 2.49 | 2.73 | 4.08 | 1.85 | 2.42 | 
| SIE4x4 | 18.13 | 15.19 | 10.93 | 4.56 | 21.81 | 23.62 | 14.31 | 
| ALKBDE10 | 5.93 | 5.42 | 7.17 | 14.35 | 4.22 | 6.36 | 5.69 | 
| YBDE18 | 3.34 | 3.11 | 3.41 | 5.99 | 4.49 | 4.87 | 0.99 | 
| AL2X6 | 1.59 | 1.64 | 1.79 | 2.05 | 2.28 | 1.59 | 1.33 | 
| HEAVYSB11 | 3.24 | 3.82 | 4.93 | 6.60 | 2.59 | 3.53 | 1.4 | 
| NBPRC | 1.55 | 1.80 | 4.43 | 3.38 | 1.37 | 2.41 | 3.08 | 
| ALK8 | 2.84 | 2.79 | 2.70 | 2.90 | 0.80 | 2.21 | 2.36 | 
| RC21 | 4.85 | 4.65 | 4.51 | 4.83 | 4.41 | 6.75 | 5.37 | 
| G2RC | 5.65 | 5.37 | 5.93 | 8.13 | 7.23 | 6.94 | 6.71 | 
| BH76RC | 3.17 | 2.83 | 2.94 | 4.19 | 3.59 | 4.17 | 2.45 | 
| FH51 | 4.58 | 2.12 | 2.67 | 4.11 | 6.34 | 5.07 | 4.68 | 
| TAUT15 | 1.57 | 1.34 | 1.09 | 1.07 | 1.60 | 1.80 | 1.13 | 
| DC13 | 7.85 | 7.18 | 7.91 | 10.69 | 8.11 | 8.93 | 8.43 | 
| MB16-43 | 14.62 | 13.56 | 14.77 | 22.17 | 25.84 | 25.10 | 15.99 | 
| DARC | 2.72 | 2.06 | 2.90 | 7.40 | 4.64 | 3.13 | 3.94 | 
| RSE43 | 1.6 | 1.29 | 0.94 | 0.80 | 2.08 | 2.93 | 1.57 | 
| BSR36 | 0.44 | 0.96 | 1.65 | 2.76 | 3.09 | 2.30 | 2.73 | 
| CDIE20 | 1.62 | 1.44 | 1.20 | 0.93 | 1.72 | 1.70 | 1.29 | 
| ISO34 | 1.3 | 1.19 | 1.31 | 1.83 | 2.31 | 1.49 | 1.43 | 
| ISOL24 | 4.04 | 3.16 | 2.46 | 3.46 | 5.30 | 4.19 | 2.08 | 
| C60ISO | 5.56 | 3.14 | 4.16 | 12.84 | 9.74 | 11.80 | 2.11 | 
| PArel | 1.54 | 1.32 | 1.23 | 1.47 | 1.53 | 1.77 | 1.2 | 
| BH76 | 7.34 | 2.83 | 2.94 | 4.19 | 9.25 | 9.61 | 4.99 | 
| BHPERI | 4.67 | 3.44 | 2.01 | 1.86 | 5.89 | 6.82 | 3.3 | 
| BHDIV10 | 6.12 | 4.89 | 3.17 | 1.71 | 7.00 | 8.89 | 4.81 | 
| INV24 | 2.33 | 1.03 | 1.52 | 2.53 | 1.89 | 2.06 | 1.14 | 
| BHROT27 | 0.76 | 0.77 | 0.80 | 0.87 | 0.53 | 0.47 | 0.58 | 
| PX13 | 8.93 | 7.28 | 4.97 | 1.94 | 8.91 | 11.95 | 6.49 | 
| WCPT18 | 6.11 | 4.66 | 2.87 | 2.58 | 6.36 | 9.29 | 4.29 | 
| RG18 | 0.17 | 0.15 | 0.11 | 0.09 | 0.13 | 0.26 | 0.09 | 
| ADIM6 | 0.36 | 0.35 | 0.36 | 0.32 | 0.38 | 0.09 | 0.19 | 
| S22 | 0.29 | 0.31 | 0.38 | 0.57 | 0.33 | 0.42 | 0.41 | 
| S66 | 0.3 | 0.32 | 0.35 | 0.44 | 0.33 | 0.38 | 0.36 | 
| HEAVY28 | 0.29 | 0.27 | 0.26 | 0.22 | 0.38 | 0.47 | 0.28 | 
| WATER27 | 6.72 | 6.27 | 5.57 | 5.10 | 4.16 | 8.28 | 5.35 | 
| CARBHB12 | 1.13 | 1.07 | 0.99 | 0.96 | 1.36 | 1.84 | 1.36 | 
| PNICO23 | 0.82 | 0.73 | 0.62 | 0.55 | 1.15 | 1.36 | 0.89 | 
| HAL59 | 0.81 | 0.65 | 0.47 | 0.33 | 1.07 | 1.29 | 0.62 | 
| AHB21 | 3.5 | 1.37 | 1.51 | 1.83 | 0.73 | 1.24 | 1.31 | 
| CHB6 | 0.46 | 0.49 | 0.83 | 1.44 | 0.71 | 0.67 | 1.13 | 
| IL16 | 0.76 | 0.43 | 0.32 | 0.42 | 0.35 | 0.96 | 0.5 | 
| IDISP | 2.56 | 2.42 | 2.16 | 2.71 | 2.77 | 2.55 | 1.47 | 
| ICONF | 0.3 | 0.30 | 0.34 | 0.46 | 0.16 | 0.31 | 0.27 | 
| ACONF | 0.18 | 0.20 | 0.21 | 0.22 | 0.12 | 0.08 | 0.06 | 
| AMINO20x4 | 0.19 | 0.20 | 0.23 | 0.31 | 0.36 | 0.33 | 0.25 | 
| PCONF21 | 0.42 | 0.30 | 0.28 | 0.37 | 0.83 | 0.99 | 0.74 | 
| MCONF | 0.45 | 0.38 | 0.29 | 0.21 | 0.44 | 0.47 | 0.27 | 
| SCONF | 0.54 | 0.36 | 0.14 | 0.18 | 1.22 | 0.88 | 0.32 | 
| UPU23 | 0.39 | 0.34 | 0.39 | 0.52 | 0.45 | 0.51 | 0.54 | 
| BUT14DIOL | 0.27 | 0.21 | 0.13 | 0.08 | 0.47 | 0.59 | 0.31 | 

### GMTKN55 - TZVPP (HN 08.11.2021)

Statistics in kcal/mol.

| method | WTMAD-2 | basic | react. | barriers | inter. NCI | intra. NCI | NCI |
| --- | ---:| ---:| ---:| ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | 7.12 | 4.90 | 7.43 | 11.72 | 8.64 | 5.81 | 7.26 |
| r²SCAN0-D4/def2-TZVPP | 6.42 | 5.39 | 6.94 | 8.17 | 7.66 | 5.20 | 6.46 |
| r²SCAN50-D4/def2-TZVPP  | 6.78 | 6.88 | 8.65 | 5.98 | 6.78 | 5.58 | 6.20 |


| method | WTMAD-1 | basic | react. | barriers | inter. NCI | intra. NCI | NCI |
| --- | ---:| ---:| ---:| ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | 4.22 | 4.19 | 4.28 | 5.18 | 4.38 | 3.24 | 3.89 |
| r²SCAN0-D4/def2-TZVPP | 3.85 | 4.10 | 3.98 | 3.93 | 4.09 | 2.83 | 3.55 |
| r²SCAN50-D4/def2-TZVPP  | 4.04 | 4.57 | 4.86 | 3.10 | 3.80 | 3.22 | 3.55 |


### L7 (MBU 03.11.2021)

Statistics in kcal/mol.

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN | 0.36 | 1.59 | 1.70 | 1.66 |
| r²SCANh | 0.34 | 1.54 | 1.69 | 1.66 |
| r²SCAN0 | 0.45 | 1.60 | 1.82 | 1.76 |
| r²SCAN50 | 0.73 | 1.86 | 2.20 | 2.08 |
| wB97X-V |  |  |  |  |
| PBE0-D4 | –0.27 | 0.56 | 0.63 | 0.61 |
| PW6B95-D4 | 0.95 | 1.11 | 1.52 | 1.28 |


### S30L (MBU 03.11.2021)

Statistics in kcal/mol. def2-QZVPP and def2-TZVPP

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN | -1.83 | 1.92 | 2.60 | 1.84 |
| r²SCANh |  |  |  |  |
| r²SCAN0 |  |  |  |  |
| r²SCAN50 |  |  |  |  |
| PW6B95-D4 | 1.53 | 2.45 | 2.87 | 2.47 |

### X40x10 (2018) (MBU 03.11.2021)

Statistics in kcal/mol.

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN | -0.09 | 0.30 | 0.57 | 0.56 |
| r²SCANh | -0.07 | 0.30 | 0.57 | 0.56 |
| r²SCAN0 | -0.06 | 0.31 | 0.58 | 0.57 |
| r²SCAN50 | -0.07 | 0.34 | 0.62 | 0.62 |

### HB300SPX (MBU 10.11.2021)

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN | -0.58 | 0.62 | 1.03 | 0.85 |
| r²SCANh | -0.54 | 0.57 | 0.95 | 0.78 |
| r²SCAN0 | -0.50 | 0.53 | 0.87 | 0.72 |
| r²SCAN50 | -0.49 | 0.52 | 0.85 | 0.70 |
| wB97X-V |  |  |  |  |
| PBE0-D4 | -0.69 | 0.70 | 0.99 | 0.72 |
| PW6B95-D4 |  |  |  |  |

### R160x6 (MBU 10.11.2021)

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN | -0.02 | 0.24 | 0.35 | 0.35 |
| r²SCANh | -0.00 | 0.22 | 0.31 | 0.31 |
| r²SCAN0 | 0.02 | 0.20 | 0.28 | 0.28 |
| r²SCAN50 | 0.04 | 0.22 | 0.32 | 0.32 |
| wB97X-V |  |  |  |  |
| PBE0-D4 |  |  |  |  |
| PW6B95-D4 |  |  |  |  |


### LMGB35

Statistics in pm.

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4-ATM/def2-QZVP | –0.12 | 0.68 | 1.01 | 1.02 |
| r²SCANh-D4-ATM/def2-QZVP | –0.07 | 1.28 | 2.26 | 2.29 |
| r²SCAN0-D4-ATM/def2-QZVP | –0.59 | 1.59 | 2.33 | 2.29 |
| r²SCAN50-D4-ATM/def2-QZVP | –1.35 | 2.09 | 2.77 | 2.45 |


### HMGB11

Statistics in pm.

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4-ATM/def2-QZVP | 0.51 | 1.17 | 1.34 | 1.29 |
| r²SCANh-D4-ATM/def2-QZVP | –0.13 | 1.02 | 1.18 | 1.23 |
| r²SCAN0-D4-ATM/def2-QZVP | –1.16 | 1.16 | 1.55 | 1.07 |
| r²SCAN50-D4-ATM/def2-QZVP | –2.70 | 2.70 | 2.91 | 1.15 |


### TMC32

Statistics in pm.

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4-ATM/def2-QZVP | –1.57 | 1.89 | 2.35 | 1.77 |
| r²SCANh-D4-ATM/def2-QZVP | –1.90 | 2.18 | 2.61 | 1.80 |
| r²SCAN0-D4-ATM/def2-QZVP | –2.43 | 2.71 | 3.11 | 1.96 |
| r²SCAN50-D4-ATM/def2-QZVP | –2.91 | 3.36 | 3.97 | 2.73 |

### ROT34

Statistics in MHz.

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4-ATM/def2-QZVP | –3.22 | 4.64 | 5.88 | 4.99 |
| r²SCANh-D4-ATM/def2-QZVP | –1.92 | 3.00 | 4.33 | 3.94 |
| r²SCAN0-D4-ATM/def2-QZVP | –10.46 | 10.46 | 12.76 | 7.40 |
| r²SCAN50-D4-ATM/def2-QZVP | –24.15 | 14.15 | 28.99 | 16.28 |

### LB12

Statistics in pm.

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4-ATM/def2-QZVP | 1.81 | 3.57 | 5.67 | 5.61 |
| r²SCANh-D4-ATM/def2-QZVP | 2.33 | 3.88 | 6.00 | 5.77 |
| r²SCAN0-D4-ATM/def2-QZVP | 0.67 | 3.16 | 4.89 | 5.05 |
| r²SCAN50-D4-ATM/def2-QZVP | –2.24 | 5.48 | 9.03 | 9.14 |

### CCse21

Bond lengths. Statistics in pm.

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4-ATM/def2-QZVP | 0.03 | 0.38 | 0.56 | 0.57 |
| r²SCANh-D4-ATM/def2-QZVP | –0.26 | 0.43 | 0.62 | 0.57 |
| r²SCAN0-D4-ATM/def2-QZVP | –0.69 | 0.70 | 0.99 | 0.71 |
| r²SCAN50-D4-ATM/def2-QZVP | –1.34 | 1.34 | 1.68 | 1.02 |


Bond angles. Statistics in deg.

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4-ATM/def2-QZVP | 0.01 | 0.29 | 0.37 | 0.37 |
| r²SCANh-D4-ATM/def2-QZVP | 0.00 | 0.24 | 0.28 | 0.29 |
| r²SCAN0-D4-ATM/def2-QZVP | 0.02 | 0.22 | 0.28 | 0.28 |
| r²SCAN50-D4-ATM/def2-QZVP | 0.07 | 0.28 | 0.38 | 0.38 |

### MOR41 (MBU 01.11.2021)

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN | -0.13 | 3.32 | 4.29 | 4.29 |
| r²SCANh | -0.52 | 2.54 | 3.47 | 3.47 |
| r²SCAN0 | 0.09 | 2.31 | 2.91 | 2.90 |
| r²SCAN50 | 0.19 | 3.19 | 4.20 | 4.20 |
| wB97X-V |  | 2.21	 |  |  |  (MOR41 paper)
| PBE0-D4 | –0.25 | 2.28 | 3.08 | 3.11 | <-- def2-QZVPP from DFT-D4 paper -->
| PW6B95-D4 | 2.68 | 3.20 | 3.99 | 2.98 |

<!-- MOR41 energies mit neu gerechnetem D4, erstaunlicherweise wesentlich schlechter als D3 (2.70 laut webtable -->

### ROST61 (MBU 08.11.2021)

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN | 0.89 | 3.33 | 4.48 | 4.38 |
| r²SCANh | 0.31 | 2.64 | 3.61 | 3.59 |
| r²SCAN0 | -0.53 | 2.96 | 3.98 | 3.95 |
| r²SCAN50 | -1.94 | 4.84 | 7.12 | 6.87 |
| wB97X-V |  | 2.8 |  |  |
| PBE0-D4 |  | 2.6 |  |  |
| PW6B95-D4 |  | 2.5 |  |  |

### WCCR10  (MBU 01.11.2021)

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN | 1.22 | 2.74 | 3.78 | 3.57 |
| r²SCANh | 0.91 | 1.96 | 2.69 | 2.53 |
| r²SCAN0 | 0.44 | 0.88 | 1.22 | 1.14 |
| r²SCAN50 | -0.21 | 1.30 | 1.58 | 1.57 |
| wB97X-V |  |  |  |  |
| PBE0-D4 |  |  |  |  |
| PW6B95-D4 |  |  |  |  |

### MOBH35 (MBU 01.11.2021)

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN | -2.97 | 3.71 | 4.86 | 3.85 |
| r²SCANh |  |  |  |  |
| r²SCAN0 | -0.56 | 2.07 | 2.81 | 2.75 |
| r²SCAN50 |  |  |  |  |
| wB97X-V |  |  |  |  |
| PBE0-D4 |  |  |  |  |
| PW6B95-D4 |  |  |  |  |


### TMBH (MBU 03.11.2021)

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN | -2.59 | 3.24 | 4.04 | 3.10 |
| r²SCANh | -1.60 | 2.33 | 2.92 | 2.46 |
| r²SCAN0 | -0.10 | 1.88 | 2.43 | 2.43 |
| r²SCAN50 | 2.13 | 2.89 | 4.64 | 4.12 |
| wB97X-V | 1.85 | 2.11 | 3.40 | 2.85 |
| PBE0-D4 | -0.87 | 2.32 | 2.87 | 2.74 |
| PW6B95-D4 | 0.10 | 1.26 | 1.66 | 1.65 |

### MLA24 (MBU 03.11.2021) former name: PExMPEx

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN | 1.37 | 4.81 | 5.42 | 5.24 |
| r²SCANh | 1.95 | 4.48 | 5.19 | 4.81 |
| r²SCAN0 | 2.73 | 4.09 | 5.08 | 4.28 |
| r²SCAN50 | 3.88 | 4.21 | 5.32 | 3.64 |
| wB97X-V | -1.49 | 1.69 | 2.23 | 1.65 |
| PBE0-D4 | 0.92 | 3.24 | 3.69 | 3.57 |
| PW6B95-D4 | 0.08 | 2.62 | 2.87 | 2.87 |


### IONPI19 (MBU 03.11.2021)

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN | -0.06 | 0.72 | 0.85 | 0.85 | (MAD 0.71 im paper)
| r²SCANh | -0.07 | 0.67 | 0.80 | 0.80 |
| r²SCAN0 | -0.13 | 0.71 | 0.82 | 0.81 |
| r²SCAN50 | -0.27 | 0.84 | 1.12 | 1.09 |
| wB97X-V |  | 0.73 |  |  |
| PBE0-D4 |  | 0.88 |  |  |
| PW6B95-D4 |  | 0.83 |  |  | (IONPI paper SI Tab S15 Korrekt? Spichi fragen!)

### ACONF12 (MBU 08.11.2021)

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN | 0.19 | 0.19 | 0.20 | 0.07 |
| r²SCANh | 0.18 | 0.18 | 0.20 | 0.07 |
| r²SCAN0 | 0.16 | 0.16 | 0.17 | 0.07 |
| r²SCAN50 | 0.11 | 0.12 | 0.14 | 0.08 |

### MPCONF196 (MBU 08.11.2021)

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN | 0.40 | 0.75 | 1.06 | 0.99 |
| r²SCANh | 0.49 | 0.77 | 1.09 | 0.97 |
| r²SCAN0 | 0.61 | 0.83 | 1.19 | 1.02 |
| r²SCAN50 | 0.59 | 1.34 | 2.40 | 2.33 |

### 37CONF8 (MBU 08.11.2021)

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN | 0.09 | 0.50 | 0.69 | 0.69 |
| r²SCANh | 0.11 | 0.46 | 0.64 | 0.63 |
| r²SCAN0 | 0.13 | 0.46 | 0.62 | 0.61 |
| r²SCAN50 | 0.18 | 0.54 | 0.72 | 0.70 |

### TMCONF16  (MBU 01.11.2021)

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN | -0.10 | 0.22 | 0.30 | 0.28 |
| r²SCANh | -0.13 | 0.22 | 0.29 | 0.26 |
| r²SCAN0 | -0.17 | 0.23 | 0.31 | 0.26 |
| r²SCAN50 | -0.25 | 0.28 | 0.39 | 0.31 |
| wB97X-V | -0.47 | 0.50 | 0.68 | 0.48 |
| PBE0-D4 | -0.39 | 0.39 | 0.49 | 0.29 |
| PW6B95-D4 | -0.40 | 0.43 | 0.54 | 0.36 |



| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN |  |  |  |  |
| r²SCANh |  |  |  |  |
| r²SCAN0 |  |  |  |  |
| r²SCAN50 |  |  |  |  |
| wB97X-V |  |  |  |  |
| PBE0-D4 |  |  |  |  |
| PW6B95-D4 |  |  |  |  |
