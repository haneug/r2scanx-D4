# r²SCANX-D4


## Functional Implementation

- r²SCANX-D4 functionals can be build in Orca and Turbomole via the LibXC
- r²SCAN can be used with [libxc version 5.1.0](https://www.tddft.org/programs/libxc/changes/#510---2021-01-19) as `MGGA_X_R2SCAN` (id=497), `MGGA_C_R2SCAN` (id=498)
- [XCFun 2.1.0](https://github.com/dftlibs/xcfun/releases/tag/v2.1.0) also implements support for the r²SCAN functional
- routines for r²SCAN functional implementation can be found at https://gitlab.com/dhamil/r2scan-subroutines (Fortran), routines for Vasp are included
- Libraries implementing DFT-D4 can be found at https://github.com/dftd4/dftd4 (Fortran) and https://github.com/dftd4/cpp-d4 (C++)


In the following * indicates that D4 Parameters from https://doi.org/10.3390/molecules27010141 were employed.

## Functional parameters

| method | s6 | s8 | s9 | a1 | a2/Bohr |
| --- | --- | --- | --- | --- | --- |
| r²SCANh-D4(EEQ)-ATM/def2-QZVP | 1 | 0.8324 | 1 | 0.4944 | 5.9019 |
| r²SCANh-D3(BJ)-ATM/def2-QZVP | 1 | 1.1236 | 1 | 0.4709 | 5.9157 |
| r²SCAN0-D4(EEQ)-ATM/def2-QZVP | 1 | 0.8992 | 1 | 0.4778 | 5.8779 |
| r²SCAN0-D3(BJ)-ATM/def2-QZVP | 1 | 1.1846 | 1 | 0.4534 | 5.8972 |
| r²SCAN50-D4(EEQ)-ATM/def2-QZVP | 1 | 1.0471 | 1 | 0.4574 | 5.8969 |
| r²SCAN50-D3(BJ)-ATM/def2-QZVP | 1 | 1.3294 | 1 | 0.4311 | 5.9240 |

| method | s6 | s8 | s9 | a1 | a2/Bohr |
| --- | --- | --- | --- | --- | --- |
| r²SCANh-D4(EEQ)-ATM/def2-TZVPP | 1 | 0.9119 | 1 | 0.4832 | 6.2073 |
| r²SCANh-D3(BJ)-ATM/def2-TZVPP | 1 | 1.1493 | 1 | 0.4761 | 6.0947 |
| r²SCAN0-D4(EEQ)-ATM/def2-TZVPP | 1 | 0.9397 | 1 | 0.4578 | 6.1864 |
| r²SCAN0-D3(BJ)-ATM/def2-TZVPP | 1 | 1.1859 | 1 | 0.4567 | 6.0583 |
| r²SCAN50-D4(EEQ)-ATM/def2-TZVPP | 1 | 1.0576 | 1 | 0.4232 | 6.2378 |
| r²SCAN50-D3(BJ)-ATM/def2-TZVPP | 1 | 1.2980 | 1 | 0.4314 | 6.0662 |

| method | b |
| --- | --- |
| r²SCANh-VV10 | 11.9 |
| r²SCAN0-VV10 | 11.4 |
| r²SCAN50-VV10 | 10.8 |

## Benchmark Results

### NCIBLIND10
Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4-ATM/def2-QZVP | –0.05 | 0.17 | 0.29 | 0.29 |
| r²SCANh-D4-ATM/def2-QZVP | -0.06 | 0.18 | 0.32 | 0.31  |
| r²SCAN0-D4-ATM/def2-QZVP | -0.07 | 0.20 | 0.36 | 0.35  |
| r²SCAN50-D4-ATM/def2-QZVP | -0.10 | 0.26 | 0.46 | 0.45  |


### S22x5
Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4-ATM/def2-QZVP | –0.12 | 0.28 | 0.51 | 0.50 |
| r²SCANh-D4-ATM/def2-QZVP | -0.16 | 0.30 | 0.57 | 0.55 |
| r²SCAN0-D4-ATM/def2-QZVP | -0.20 | 0.35 | 0.66 | 0.63 |
| r²SCAN50-D4-ATM/def2-QZVP | -0.28 | 0.47 | 0.86 | 0.82 |

### S66x8
Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4-ATM/def2-QZVP | –0.09 | 0.23 | 0.38 | 0.36 |
| r²SCANh-D4-ATM/def2-QZVP | -0.11 | 0.24 | 0.41 | 0.39 |
| r²SCAN0-D4-ATM/def2-QZVP | -0.13 | 0.27 | 0.46 | 0.44 |
| r²SCAN50-D4-ATM/def2-QZVP | -0.18 | 0.35 | 0.60 | 0.57 |

----------------------------------------------------------------

### GMTKN55 / def2-QZVP

Statistics in kcal/mol.

| method | WTMAD-2 | basic | react. | barriers | inter. NCI | intra. NCI | NCI |
| --- | ---:| ---:| ---:| ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVP | 7.54 | 5.55 | 8.26 | 14.29 | 7.46 | 5.74 | 6.62 |
| r²SCANh-D4/def2-QZVP | 6.23 | 4.42 | 7.26 | 11.10 | 6.34 | 4.97 | 5.67 |
| r²SCAN0-D4/def2-QZVP | 5.64 | 4.93 | 6.80 | 7.60 | 5.63 | 4.53 | 5.09 |
| r²SCAN50-D4/def2-QZVP  | 6.28 | 6.60 | 8.49 | 5.97 | 5.32 | 5.14 | 5.23 |


| method | WTMAD-1 | basic | react. | barriers | inter. NCI | intra. NCI | NCI |
| --- | ---:| ---:| ---:| ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVP | 4.43 | 4.46 | 4.85 | 6.15 | 3.87 | 3.33 | 3.64 |
| r²SCANh-D4/def2-QZVP | 3.80 | 3.89 | 4.21 | 4.95 | 3.41 | 2.82 | 3.15 |
| r²SCAN0-D4/def2-QZVP | 3.47 | 3.81 | 3.94 | 3.73 | 3.19 | 2.48 | 2.89 |
| r²SCAN50-D4/def2-QZVP  | 3.81 | 4.40 | 4.86 | 3.10 | 3.22 | 2.91 | 3.09 |

*With D4 Parameters from https://doi.org/10.3390/molecules27010141

| method | WTMAD-2 | basic | react. | barriers | inter. NCI | intra. NCI | NCI |
| --- | ---:| ---:| ---:| ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-QZVP* | 6.04 | 4.4 | 7.44 | 10.99 | 5.46 | 4.86 | 5.17 |
| r²SCAN0-D4/def2-QZVP* | 5.45 | 4.91 | 6.86 | 7.53 | 4.75 | 4.51 | 4.63 |
| r²SCAN50-D4/def2-QZVP* | 6.17 | 6.6 | 8.42 | 5.97 | 4.76 | 5.22 | 4.99 |


| method | WTMAD-1 | basic | react. | barriers | inter. NCI | intra. NCI | NCI |
| --- | ---:| ---:| ---:| ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-QZVP* | 3.77 | 3.88 | 4.27 | 4.91 | 3.32 | 2.78 | 3.09 |
| r²SCAN0-D4/def2-QZVP* | 3.43 | 3.8 | 3.94 | 3.7 | 3.05 | 2.48 | 2.8 |
| r²SCAN50-D4/def2-QZVP* | 3.79 | 4.41 | 4.86 | 3.1 | 3.1 | 2.94 | 3.03 |

The MADs of all GMTKN55 subsets in kcal/mol are given here.
Values for TPSS-D4, PBE-D4 and PBE0-D4/def2-QZVPP are taken from Caldeweyher et al. *J. Chem Phys*, **2019**, 150, 154122. DOI: [10.1063/1.5090222](https://doi.org/10.1063/1.5090222). Values for r²SCAN-D4 are taken from Ehlert et al. *J. Chem. Phys.* **2021**, 154, 061101. DOI: [10.1063/5.0041008](https://doi.org/10.1063/5.0041008)

| subset | r²SCAN-D4 | r²SCANh-D4 | r²SCAN0-D4 | r²SCAN50-D4  | TPSS-D4 | PBE-D4 | PBE0-D4/def2-QZVPP |
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
| NBPRC | 1.55 | 1.80 | 2.34 | 3.38 | 1.37 | 2.41 | 3.08 |
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

### GMTKN55 / def2-TZVPP 

Statistics in kcal/mol.

| method | WTMAD-2 | basic | react. | barriers | inter. NCI | intra. NCI | NCI |
| --- | ---:| ---:| ---:| ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | 6.81 | 4.54 | 7.43 | 11.72 | 7.64 | 5.81 | 6.75 |
| r²SCAN0-D4/def2-TZVPP | 6.13 | 5.04 | 6.94 | 8.17 | 6.76 | 5.20 | 6.00 |
| r²SCAN50-D4/def2-TZVPP | 6.52 | 6.56 | 8.65 | 5.98 | 6.02 | 5.58 | 5.81 |



| method | WTMAD-1 | basic | react. | barriers | inter. NCI | intra. NCI | NCI |
| --- | ---:| ---:| ---:| ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | 4.07 | 3.97 | 4.28 | 5.18 | 4.06 | 3.24 | 3.71 |
| r²SCAN0-D4/def2-TZVPP | 3.72 | 3.88 | 3.98 | 3.93 | 3.8 | 2.83 | 3.38 |
| r²SCAN50-D4/def2-TZVPP | 3.92 | 4.36 | 4.86 | 3.1 | 3.56 | 3.22 | 3.41 |

----------------------------------------------------------------

### L7 / def2-QZVPP 

Statistics in kcal/mol.

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP | 0.36 | 1.59 | 1.70 | 1.66 |
| r²SCANh-D4/def2-QZVPP | 0.34 | 1.54 | 1.69 | 1.66 |
| r²SCAN0-D4/def2-QZVPP | 0.45 | 1.60 | 1.82 | 1.76 |
| r²SCAN50-D4/def2-QZVPP | 0.73 | 1.86 | 2.20 | 2.08 |
| ωB97X-V/def2-QZVPP | -0.86 | 0.86 | 1.31 | 0.99 |
| PBE0-D4/def2-QZVPP | –0.27 | 0.56 | 0.63 | 0.61 |
| PW6B95-D4/def2-QZVPP | 0.95 | 1.11 | 1.52 | 1.28 |
| r²SCANh-D4/def2-QZVPP* | -0.33 | 1.05 | 1.46 | 1.42 |
| r²SCAN0-D4/def2-QZVPP* | -0.65 | 1.10 | 1.59 | 1.45 |
| r²SCAN50-D4/def2-QZVPP* | -0.35 | 1.15 | 1.75 | 1.72 |


### L7 / def2-TZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | 0.62 | 1.90 | 2.07 | 1.97 |
| r²SCAN0-D4/def2-TZVPP | 0.71 | 1.93 | 2.17 | 2.05 |
| r²SCAN50-D4/def2-TZVPP | 0.99 | 2.17 | 2.54 | 2.35 |

----------------------------------------------------------------

### S30L / def2-QZVPP 

ωB97X-D3 taken from https://doi.org/10.1021/acs.jctc.5b00296

Statistics in kcal/mol. 

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP | -1.83 | 1.92 | 2.60 | 1.84 |
| r²SCANh-D4/def2-QZVPP | -1.93 | 2.01 | 2.61 | 1.76 |
| r²SCAN0-D4/def2-QZVPP | -1.78 | 2.01 | 2.50 | 1.75 |
| r²SCAN50-D4/def2-QZVPP | -1.58 | 2.04 | 2.46 | 1.88 |
| wB97X-D3/def2-QZVPP |  | 2.6 |  |  |      ACHTUNG!!! D3 value from original publication as calcs still running
| PBE0-D4/def2-QZVPP | -1.81 | 2.59 | 3.34 | 2.81 |  => RIJCOSX
| PW6B95-D4/def2-QZVPP | 1.53 | 2.45 | 2.87 | 2.47 |
| r²SCANh-D4/def2-QZVPP* | -3.86 | 3.86 | 4.78 | 2.82 |
| r²SCAN0-D4/def2-QZVPP* | -4.36 | 4.36 | 5.29 | 2.99 |
| r²SCAN50-D4/def2-QZVPP* | -3.62 | 3.74 | 4.33 | 2.38 |


### S30L / def2-TZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | -1.67 | 1.87 | 2.45 | 1.79 |
| r²SCAN0-D4/def2-TZVPP | -1.57 | 1.85 | 2.35 | 1.76 |
| r²SCAN50-D4/def2-TZVPP | -1.35 | 1.89 | 2.41 | 2.00 |

----------------------------------------------------------------

### X40x10(2018) / def2-QZVPP 

Statistics in kcal/mol.

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP | -0.09 | 0.30 | 0.57 | 0.56 |
| r²SCANh-D4/def2-QZVPP | -0.07 | 0.30 | 0.57 | 0.56 |
| r²SCAN0-D4/def2-QZVPP | -0.06 | 0.31 | 0.58 | 0.57 |
| r²SCAN50-D4/def2-QZVPP | -0.07 | 0.34 | 0.62 | 0.62 |
| ωB97X-V/def2-QZVPP | 0.17 | 0.26 | 0.47 | 0.44 |
| PBE0-D4/def2-QZVPP | -0.16 | 0.32 | 0.55 | 0.52 |
| PW6B95-D4/def2-QZVPP | 0.07 | 0.21 | 0.31 | 0.30 |
| r²SCANh-D4/def2-QZVPP* | -0.13 | 0.30 | 0.56 | 0.54 |
| r²SCAN0-D4/def2-QZVPP* | -0.13 | 0.30 | 0.56 | 0.54 |
| r²SCAN50-D4/def2-QZVPP* | -0.15 | 0.32 | 0.60 | 0.59 |



### X40x10(2018) / def2-TZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | -0.17 | 0.35 | 0.66 | 0.63 |
| r²SCAN0-D4/def2-TZVPP | -0.15 | 0.35 | 0.66 | 0.64 |
| r²SCAN50-D4/def2-TZVPP | -0.16 | 0.37 | 0.70 | 0.68 |

----------------------------------------------------------------

### CHAL336 / def2-QZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP | -1.67 | 1.90 | 2.81 | 2.25 |
| r²SCANh-D4/def2-QZVPP | -1.54 | 1.75 | 2.62 | 2.12 |
| r²SCAN0-D4/def2-QZVPP | -1.48 | 1.67 | 2.54 | 2.06 |
| r²SCAN50-D4/def2-QZVPP | -1.50 | 1.69 | 2.70 | 2.24 |
| ωB97X-V/def2-QZVPP | -0.11 | 0.89 | 1.31 | 1.31 |
| PBE0-D4/def2-QZVPP | -2.01 | 2.05 | 2.80 | 1.95 |
| PW6B95-D4/def2-QZVPP | -0.93 | 1.28 | 1.90 | 1.65 |
| r²SCANh-D4/def2-QZVPP* | -1.77 | 1.85 | 2.71 | 2.06 |
| r²SCAN0-D4/def2-QZVPP* | -1.72 | 1.78 | 2.64 | 2.00 |
| r²SCAN50-D4/def2-QZVPP* | -1.73 | 1.80 | 2.82 | 2.22 |



### CHAL336 / ma-def2-QZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP* | |  |  |  |
| r²SCANh-D4/def2-QZVPP |  |  |  |  |
| r²SCAN0-D4/def2-QZVPP | -0.97 | 1.31 | 2.03 | 1.78 |
| r²SCAN50-D4/def2-QZVPP |  |  |  |  |
| ωB97X-V/def2-QZVPP |  |  |  |  |
| PBE0-D4/def2-QZVPP |  |  |  |  |
| PW6B95-D4/def2-QZVPP |  |  |  |  |

### CHAL336 / def2-TZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | -2.23 | 2.42 | 3.82 | 3.09 |
| r²SCAN0-D4/def2-TZVPP | -2.09 | 2.26 | 3.51 | 2.82 |
| r²SCAN50-D4/def2-TZVPP | -2.06 | 2.20 | 3.36 | 2.66 |

----------------------------------------------------------------

### HB300SPX / def2-QZVPP 

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP | -0.58 | 0.62 | 1.03 | 0.85 |
| r²SCANh-D4/def2-QZVPP | -0.54 | 0.57 | 0.95 | 0.78 |
| r²SCAN0-D4/def2-QZVPP | -0.50 | 0.53 | 0.87 | 0.72 |
| r²SCAN50-D4/def2-QZVPP | -0.49 | 0.52 | 0.85 | 0.70 |
| ωB97X-V/def2-QZVPP | 0.01 | 0.23 | 0.34 | 0.34 |
| PBE0-D4/def2-QZVPP | -0.69 | 0.70 | 0.99 | 0.72 |
| PW6B95-D4/def2-QZVPP | -0.08 | 0.24 | 0.33 | 0.32 |
| r²SCANh-D4/def2-QZVPP* | -0.60 | 0.61 | 0.98 | 0.78 |
| r²SCAN0-D4/def2-QZVPP* | -0.57 | 0.58 | 0.91 | 0.71 |
| r²SCAN50-D4/def2-QZVPP* | -0.57 | 0.58 | 0.90 | 0.70 |


### HB300SPX / def2-TZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | -0.67 | 0.69 | 1.07 | 0.83 |
| r²SCAN0-D4/def2-TZVPP | -0.63 | 0.65 | 0.99 | 0.76 |
| r²SCAN50-D4/def2-TZVPP | -0.61 | 0.64 | 0.96 | 0.74 |

----------------------------------------------------------------

### R160x6 / def2-QZVPP 

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP | -0.02 | 0.24 | 0.35 | 0.35 |
| r²SCANh-D4/def2-QZVPP | -0.00 | 0.22 | 0.31 | 0.31 |
| r²SCAN0-D4/def2-QZVPP | 0.02 | 0.20 | 0.28 | 0.28 |
| r²SCAN50-D4/def2-QZVPP | 0.04 | 0.22 | 0.32 | 0.32 |
| ωB97X-V/def2-QZVPP | 0.11 | 0.18 | 0.26 | 0.24 |
| PBE0-D4/def2-QZVPP | -0.19 | 0.27 | 0.39 | 0.34 |
| PW6B95-D4/def2-QZVPP | 0.02 | 0.18 | 0.25 | 0.25 |
| r²SCANh-D4/def2-QZVPP* | 0.03 | 0.22 | 0.30 | 0.30 |
| r²SCAN0-D4/def2-QZVPP* | 0.04 | 0.20 | 0.28 | 0.27 |
| r²SCAN50-D4/def2-QZVPP* | 0.02 | 0.20 | 0.31 | 0.30 |



### R160x6 / def2-TZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | -0.04 | 0.25 | 0.35 | 0.35 |
| r²SCAN0-D4/def2-TZVPP | -0.01 | 0.23 | 0.32 | 0.32 |
| r²SCAN50-D4/def2-TZVPP | 0.01 | 0.24 | 0.35 | 0.35 |

----------------------------------------------------------------

### MOR41 / def2-QZVPP 

Statistics in kcal/mol

ωB97X-V data taken from https://doi.org/10.1021/acs.jctc.7b01183

PBE0-D4 data taken from https://doi.org/10.1063/1.5090222


| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP | -0.13 | 3.32 | 4.29 | 4.29 |
| r²SCANh-D4/def2-QZVPP | -0.52 | 2.54 | 3.47 | 3.47 |
| r²SCAN0-D4/def2-QZVPP | 0.09 | 2.31 | 2.91 | 2.90 |
| r²SCAN50-D4/def2-QZVPP | 0.19 | 3.19 | 4.20 | 4.20 |
| ωB97X-V/def2-QZVPP |  | 2.21	 |  |  |
| PBE0-D4/def2-QZVPP | –0.25 | 2.28 | 3.08 | 3.11 | 
| PW6B95-D4/def2-QZVPP | 2.68 | 3.20 | 3.99 | 2.98 |
| r²SCANh-D4/def2-QZVPP* | -0.74 | 2.26 | 3.26 | 3.18 |
| r²SCAN0-D4/def2-QZVPP* | -0.64 | 2.10 | 2.81 | 2.74 |
| r²SCAN50-D4/def2-QZVPP* | -0.42 | 3.22 | 4.23 | 4.21 |




### MOR41 / def2-TZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | -0.04 | 2.59 | 3.55 | 3.55 |
| r²SCAN0-D4/def2-TZVPP | 0.08 | 2.26 | 2.90 | 2.90 |
| r²SCAN50-D4/def2-TZVPP | 0.12 | 3.10 | 4.11 | 4.11 |

----------------------------------------------------------------

### ROST61 / def2-QZVPP 

Statistics in kcal/mol

ωB97X-V, PW6B95-D4, and PBE0-D4 data taken from https://doi.org/10.1021/acs.jctc.1c00659


| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP | 0.89 | 3.33 | 4.48 | 4.38 |
| r²SCANh-D4/def2-QZVPP | 0.31 | 2.64 | 3.61 | 3.59 |
| r²SCAN0-D4/def2-QZVPP | -0.53 | 2.96 | 3.98 | 3.95 |
| r²SCAN50-D4/def2-QZVPP | -1.94 | 4.84 | 7.12 | 6.87 |
| ωB97X-V/def2-QZVPP |  | 2.8 |  |  |
| PBE0-D4/def2-QZVPP |  | 2.6 |  |  |
| PW6B95-D4/def2-QZVPP |  | 2.5 |  |  |
| r²SCANh-D4/def2-QZVPP* | 0.05 | 2.57 | 3.49 | 3.49 |
| r²SCAN0-D4/def2-QZVPP* | -0.84 | 2.94 | 3.93 | 3.84 |
| r²SCAN50-D4/def2-QZVPP* | -2.21 | 4.88 | 7.11 | 6.76 |



### ROST61 / def2-TZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | 0.23 | 3.17 | 4.29 | 4.28 |
| r²SCAN0-D4/def2-TZVPP | -0.62 | 3.42 | 4.72 | 4.68 |
| r²SCAN50-D4/def2-TZVPP |  |  |  |  |                          MISSING

----------------------------------------------------------------

### WCCR10 / def2-QZVPP 

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP | 1.22 | 2.74 | 3.78 | 3.57 |
| r²SCANh-D4/def2-QZVPP | 0.91 | 1.96 | 2.69 | 2.53 |
| r²SCAN0-D4/def2-QZVPP | 0.44 | 0.88 | 1.22 | 1.14 |
| r²SCAN50-D4/def2-QZVPP | -0.21 | 1.30 | 1.58 | 1.57 |
| ωB97X-V/def2-QZVPP | 0.49 | 1.18 | 1.49 | 1.41 |
| PBE0-D4/def2-QZVPP | -0.11 | 0.83 | 0.96 | 0.95 |
| PW6B95-D4/def2-QZVPP | -1.82 | 1.82 | 2.13 | 1.11 |
| r²SCANh-D4/def2-QZVPP* | 1.77 | 2.24 | 2.85 | 2.23 |
| r²SCAN0-D4/def2-QZVPP* | 1.50 | 1.53 | 1.82 | 1.04 |
| r²SCAN50-D4/def2-QZVPP* | 0.66 | 1.53 | 2.11 | 2.00 |


### WCCR10 / def2-TZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | 1.05 | 1.20 | 2.82 | 2.61 |
| r²SCAN0-D4/def2-TZVPP | 0.60 | 1.05 | 1.36 | 1.22 |
| r²SCAN50-D4/def2-TZVPP | -0.04 | 1.26 | 1.57 | 1.57 |

----------------------------------------------------------------

### MOBH35 / def2-QZVPP 

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP | -2.97 | 3.71 | 4.86 | 3.85 |
| r²SCANh-D4/def2-QZVPP | -1.97 | 2.79 | 3.76 | 3.21 |
| r²SCAN0-D4/def2-QZVPP | -0.56 | 2.07 | 2.81 | 2.75 |
| r²SCAN50-D4/def2-QZVPP | 1.57 | 2.86 | 4.03 | 3.71 |
| ωB97X-V/def2-QZVPP | 1.09 | 2.00 | 2.60 | 2.36 |
| PBE0-D4/def2-QZVPP | -1.24 | 2.38 | 3.20 | 2.95 |
| PW6B95-D4/def2-QZVPP | -1.06 | 2.07 | 2.84 | 2.63 |
| r²SCANh-D4/def2-QZVPP* | -2.06 | 2.89 | 3.98 | 3.41 |
| r²SCAN0-D4/def2-QZVPP* | -0.67 | 2.18 | 3.01 | 2.93 |
| r²SCAN50-D4/def2-QZVPP* | 1.46 | 2.78 | 4.00 | 3.72 |



### MOBH35 / def2-TZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | -1.97 | 2.78 | 3.76 | 3.21 |
| r²SCAN0-D4/def2-TZVPP | -0.56 | 2.06 | 2.80 | 2.74 |
| r²SCAN50-D4/def2-TZVPP | 1.57 | 2.87 | 4.01 | 3.69 |

----------------------------------------------------------------

### TMBH / def2-QZVPP 

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP | -2.59 | 3.24 | 4.04 | 3.10 |
| r²SCANh-D4/def2-QZVPP | -1.60 | 2.33 | 2.92 | 2.46 |
| r²SCAN0-D4/def2-QZVPP | -0.10 | 1.88 | 2.43 | 2.43 |
| r²SCAN50-D4/def2-QZVPP | 2.13 | 2.89 | 4.64 | 4.12 |
| ωB97X-V/def2-QZVPP | 1.85 | 2.11 | 3.40 | 2.85 |
| PBE0-D4/def2-QZVPP | -0.87 | 2.32 | 2.87 | 2.74 |
| PW6B95-D4/def2-QZVPP | 0.10 | 1.26 | 1.66 | 1.65 |
| r²SCANh-D4/def2-QZVPP* | -1.56 | 2.33 | 2.90 | 2.45 |
| r²SCAN0-D4/def2-QZVPP* | -0.10 | 1.89 | 2.43 | 2.43 |
| r²SCAN50-D4/def2-QZVPP* | 2.08 | 2.89 | 4.63 | 4.14 |

### TMBH / def2-TZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | -1.63 | 2.39 | 3.00 | 2.52 |
| r²SCAN0-D4/def2-TZVPP | -0.16 | 1.92 | 2.49 | 2.48 |
| r²SCAN50-D4/def2-TZVPP | 2.07 | 2.93 | 4.65 | 4.16 |

----------------------------------------------------------------

### MLA24 / def2-QZVPP 

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP | 1.37 | 4.81 | 5.42 | 5.24 |
| r²SCANh-D4/def2-QZVPP | 1.95 | 4.48 | 5.19 | 4.81 |
| r²SCAN0-D4/def2-QZVPP | 2.73 | 4.09 | 5.08 | 4.28 |
| r²SCAN50-D4/def2-QZVPP | 3.88 | 4.21 | 5.32 | 3.64 |
| ωB97X-V/def2-QZVPP | -1.49 | 1.69 | 2.23 | 1.65 |
| PBE0-D4/def2-QZVPP | 0.92 | 3.24 | 3.69 | 3.57 |
| PW6B95-D4/def2-QZVPP | 0.08 | 2.62 | 2.87 | 2.87 |
| r²SCANh-D4/def2-QZVPP* | 1.77 | 4.50 | 5.15 | 4.84 |
| r²SCAN0-D4/def2-QZVPP* | 2.46 | 4.12 | 4.96 | 4.31 |
| r²SCAN50-D4/def2-QZVPP* | 3.61 | 4.03 | 5.16 | 3.69 |


### MLA24 / def2-TZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | 2.15 | 4.82 | 5.27 | 4.81 |
| r²SCAN0-D4/def2-TZVPP | 2.91 | 4.09 | 5.17 | 4.27 |
| r²SCAN50-D4/def2-TZVPP | 4.03 | 4.29 | 5.42 | 3.62 |

----------------------------------------------------------------


### IONPI19 / def2-QZVPP 

Statistics in kcal/mol

ωB97X-V, PW6B95-D4, and PBE0-D4 data taken from https://pubs.rsc.org/en/content/articlelanding/2021/CP/D1CP01333E

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP | -0.06 | 0.72 | 0.85 | 0.85 | (MAD 0.71 im paper)
| r²SCANh-D4/def2-QZVPP | -0.07 | 0.67 | 0.80 | 0.80 |
| r²SCAN0-D4/def2-QZVPP | -0.13 | 0.71 | 0.82 | 0.81 |
| r²SCAN50-D4/def2-QZVPP | -0.27 | 0.84 | 1.12 | 1.09 |
| ωB97X-V/def2-QZVPP |  | 0.73 |  |  |
| PBE0-D4/def2-QZVPP |  | 0.88 |  |  |
| PW6B95-D4/def2-QZVPP |  | 0.83 |  |  | (IONPI paper SI Tab S15 Korrekt? Spichi fragen!)
| r²SCANh-D4/def2-QZVPP* | -0.18 | 0.77 | 0.93 | 0.91 |
| r²SCAN0-D4/def2-QZVPP* | -0.33 | 0.85 | 1.04 | 0.99 |
| r²SCAN50-D4/def2-QZVPP* | -0.54 | 0.95 | 1.26 | 1.14 |


### IONPI19 / def2-TZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | -0.92 | 1.14 | 1.38 | 1.03 |
| r²SCAN0-D4/def2-TZVPP | -0.95 | 1.04 | 1.28 | 0.86 |
| r²SCAN50-D4/def2-TZVPP | -1.02 | 1.04 | 1.35 | 0.88 |

----------------------------------------------------------------

### ACONF12 / def2-QZVPP 

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP | 0.19 | 0.19 | 0.20 | 0.07 |
| r²SCANh-D4/def2-QZVPP | 0.18 | 0.18 | 0.20 | 0.07 |
| r²SCAN0-D4/def2-QZVPP | 0.16 | 0.16 | 0.17 | 0.07 |
| r²SCAN50-D4/def2-QZVPP | 0.11 | 0.12 | 0.14 | 0.08 |
| ωB97X-V/def2-QZVPP | -0.26 | 0.26 | 0.28 | 0.12 |
| PBE0-D4/def2-QZVPP | -0.19 | 0.19 | 0.19 | 0.05 |
| PW6B95-D4/def2-QZVPP | -0.67 | 0.67 | 0.70 | 0.17 |
| r²SCANh-D4/def2-QZVPP* | 0.25 | 0.25 | 0.27 | 0.09 |
| r²SCAN0-D4/def2-QZVPP* | 0.19 | 0.19 | 0.20 | 0.09 |
| r²SCAN50-D4/def2-QZVPP* | 0.05 | 0.09 | 0.10 | 0.09 |


### ACONF12 / def2-TZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | 0.24 | 0.24 | 0.25 | 0.07 |
| r²SCAN0-D4/def2-TZVPP | 0.20 | 0.20 | 0.21 | 0.07 |
| r²SCAN50-D4/def2-TZVPP | 0.13 | 0.15 | 0.16 | 0.09 |

----------------------------------------------------------------

### MPCONF196 / def2-QZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP | 0.40 | 0.75 | 1.06 | 0.99 |
| r²SCANh-D4/def2-QZVPP | 0.49 | 0.77 | 1.09 | 0.97 |
| r²SCAN0-D4/def2-QZVPP | 0.61 | 0.83 | 1.19 | 1.02 |
| r²SCAN50-D4/def2-QZVPP | 0.59 | 1.34 | 2.40 | 2.33 |
| ωB97X-V/def2-QZVPP | 0.43 | 0.62 | 1.00 | 0.91 |
| PBE0-D4/def2-QZVPP | 0.53 | 0.85 | 1.16 | 1.03 |
| PW6B95-D4/def2-QZVPP | -0.01 | 0.90 | 1.31 | 1.31 |
| r²SCANh-D4/def2-QZVPP* | 0.52 | 0.80 | 1.12 | 0.99 |
| r²SCAN0-D4/def2-QZVPP* | 0.68 | 0.89 | 1.26 | 1.06 |
| r²SCAN50-D4/def2-QZVPP* | 0.67 | 1.37 | 2.44 | 2.35 |


### MPCONF196 / def2-TZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | 0.53 | 0.81 | 1.15 | 1.02 |
| r²SCAN0-D4/def2-TZVPP | 0.66 | 0.88 | 1.25 | 1.07 |
| r²SCAN50-D4/def2-TZVPP | 0.87 | 1.06 | 1.52 | 1.25 |

----------------------------------------------------------------

### 37CONF8 / def2-QZVPP 

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP | 0.09 | 0.50 | 0.69 | 0.69 |
| r²SCANh-D4/def2-QZVPP | 0.11 | 0.46 | 0.64 | 0.63 |
| r²SCAN0-D4/def2-QZVPP | 0.13 | 0.46 | 0.62 | 0.61 |
| r²SCAN50-D4/def2-QZVPP | 0.18 | 0.54 | 0.72 | 0.70 |
| ωB97X-V/def2-QZVPP | -0.13 | 0.31 | 0.41 | 0.39 |
| PBE0-D4/def2-QZVPP | 0.03 | 0.52 | 0.67 | 0.67 |
| PW6B95-D4/def2-QZVPP | -0.28 | 0.64 | 0.82 | 0.77 |
| r²SCANh-D4/def2-QZVPP* | 0.12 | 0.46 | 0.64 | 0.63 |
| r²SCAN0-D4/def2-QZVPP* | 0.14 | 0.46 | 0.61 | 0.59 |
| r²SCAN50-D4/def2-QZVPP* | 0.18 | 0.53 | 0.70 | 0.68 |


### 37CONF8 / def2-TZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | 0.16 | 0.47 | 0.64 | 0.62 |
| r²SCAN0-D4/def2-TZVPP | 0.18 | 0.46 | 0.61 | 0.58 |
| r²SCAN50-D4/def2-TZVPP | 0.22 | 0.54 | 0.71 | 0.67 |

----------------------------------------------------------------

### TMCONF16 / def2-QZVPP 

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP | -0.10 | 0.22 | 0.30 | 0.28 |
| r²SCANh-D4/def2-QZVPP | -0.13 | 0.22 | 0.29 | 0.26 |
| r²SCAN0-D4/def2-QZVPP | -0.17 | 0.23 | 0.31 | 0.26 |
| r²SCAN50-D4/def2-QZVPP | -0.25 | 0.28 | 0.39 | 0.31 |
| ωB97X-V/def2-QZVPP | -0.47 | 0.50 | 0.68 | 0.48 |
| PBE0-D4/def2-QZVPP | -0.39 | 0.39 | 0.49 | 0.29 |
| PW6B95-D4/def2-QZVPP | -0.40 | 0.43 | 0.54 | 0.36 |
| r²SCANh-D4/def2-QZVPP* | -0.15 | 0.22 | 0.30 | 0.26 |
| r²SCAN0-D4/def2-QZVPP* | -0.20 | 0.25 | 0.33 | 0.27 |
| r²SCAN50-D4/def2-QZVPP* | -0.27 | 0.31 | 0.42 | 0.32 |


### TMCONF16 / def2-TZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | -0.09 | 0.19 | 0.27 | 0.25 |
| r²SCAN0-D4/def2-TZVPP | -0.14 | 0.21 | 0.28 | 0.24 |
| r²SCAN50-D4/def2-TZVPP | -0.22 | 0.26 | 0.37 | 0.30 |

----------------------------------------------------------------

### SIE8 / def2-QZVPP (remaining systems of old GMTKN SIE11 subset)

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4/def2-QZVPP | 9.24 | 9.79 | 13.44 | 9.75 |
| r²SCANh-D4/def2-QZVPP | 7.76 | 8.26 | 11.23 | 8.15 |
| r²SCAN0-D4/def2-QZVPP | 7.08 | 7.48 | 10.14 | 7.23 |
| r²SCAN50-D4/def2-QZVPP | 5.15 | 5.58 | 8.73 | 7.06 |
| ωB97X-V/def2-QZVPP | 1.70 | 6.20 | 8.64 | 8.48 |
| PBE0-D4/def2-QZVPP | 6.70 | 7.75 | 9.79 | 9.79 |
| PW6B95-D4/def2-QZVPP | 6.13 | 7.26 | 9.91 | 7.79 |
| r²SCANh-D4/def2-QZVPP* | 7.76 | 8.24 | 11.26 | 8.15 |
| r²SCAN0-D4/def2-QZVPP* | 7.08 | 7.47 | 10.15 | 7.28 |
| r²SCAN50-D4/def2-QZVPP* | 5.17 | 5.60 | 8.77 | 7.08 |

### SIE8 / def2-TZVPP

Statistics in kcal/mol

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCANh-D4/def2-TZVPP | 7.54 | 8.24 | 10.93 | 7.91 |
| r²SCAN0-D4/def2-TZVPP | 6.86 | 7.46 | 9.87 | 7.10 |
| r²SCAN50-D4/def2-TZVPP | 4.96 | 5.68 | 8.66 | 7.11 |

----------------------------------------------------------------

## Geometry Benchmark Results

### LMGB35

Statistics in pm.

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4-ATM/def2-QZVP | –0.12 | 0.68 | 1.01 | 1.02 |
| r²SCANh-D4-ATM/def2-QZVP | –0.07 | 1.29 | 2.27 | 2.30 |
| r²SCANh-D4-ATM/def2-QZVP* | –0.07 | 1.29 | 2.27 | 2.30 |
| r²SCANh-D4-ATM/def2-TZVPP | 0.01 | 1.25 | 2.27 | 2.30 |
| r²SCAN0-D4-ATM/def2-QZVP | –0.59 | 1.59 | 2.33 | 2.28 |
| r²SCAN0-D4-ATM/def2-QZVP* | –0.59 | 1.59 | 2.33 | 2.28 |
| r²SCAN0-D4-ATM/def2-TZVPP | –0.59 | 1.59 | 2.33 | 2.28 |
| r²SCAN50-D4-ATM/def2-QZVP | –1.36 | 2.09 | 2.78 | 2.45 |
| r²SCAN50-D4-ATM/def2-QZVP* | –1.36 | 2.09 | 2.78 | 2.45 |
| r²SCAN50-D4-ATM/def2-TZVPP | –1.36 | 2.09 | 2.78 | 2.45 |
| PBE0-D4/def2-QZVP | –0.55 | 0.92 | 1.41 | 1.31 |
| PW6B95-D4/def2-QZVP | –0.34 | 1.41 | 2.24 | 2.25 |
| ωB97X-V/def2-QZVP | 0.01 | 1.33 | 2.27 | 2.30 |

### HMGB11

Statistics in pm.

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4-ATM/def2-QZVP | 0.51 | 1.17 | 1.34 | 1.29 |
| r²SCANh-D4-ATM/def2-QZVP | –0.11 | 1.01 | 1.16 | 1.21 |
| r²SCANh-D4-ATM/def2-QZVP* | –0.11 | 1.01 | 1.16 | 1.21 |
| r²SCANh-D4-ATM/def2-TZVPP | 0.11 | 0.97 | 1.14 | 1.19 |
| r²SCAN0-D4-ATM/def2-QZVP | –1.16 | 1.16 | 1.53 | 1.06 |
| r²SCAN0-D4-ATM/def2-QZVP* | –1.15 | 1.15 | 1.53 | 1.06 |
| r²SCAN0-D4-ATM/def2-TZVPP | –1.14 | 1.15 | 1.53 | 1.07 |
| r²SCAN50-D4-ATM/def2-QZVP | –2.71 | 2.71 | 2.92 | 1.15 |
| r²SCAN50-D4-ATM/def2-QZVP* | –2.73 | 2.73 | 2.94 | 1.15 |
| r²SCAN50-D4-ATM/def2-TZVPP | –2.69 | 2.69 | 2.91 | 1.15 |
| PBE0-D4/def2-QZVP | –0.49 | 1.07 | 1.21 | 1.16 |
| PW6B95-D4/def2-QZVP | –0.09 | 1.09 | 1.22 | 1.27 |
| ωB97X-V/def2-QZVP | –1.44 | 1.54 | 1.77 | 1.09


### TMC32

Statistics in pm.

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4-ATM/def2-QZVP | –1.57 | 1.89 | 2.35 | 1.77 |
| r²SCANh-D4-ATM/def2-QZVP | –1.90 | 2.18 | 2.61 | 1.80 |
| r²SCANh-D4-ATM/def2-QZVP* | –1.89 | 2.17 | 2.60 | 1.80 |
| r²SCANh-D4-ATM/def2-TZVPP | –1.94 | 2.22 | 2.65 | 1.82 |
| r²SCAN0-D4-ATM/def2-QZVP | –2.43 | 2.71 | 3.11 | 1.96 |
| r²SCAN0-D4-ATM/def2-QZVP* | –2.42 | 2.70 | 3.10 | 1.96 |
| r²SCAN0-D4-ATM/def2-TZVPP | –2.42 | 2.70 | 3.10 | 1.96 |
| r²SCAN50-D4-ATM/def2-QZVP | –2.91 | 3.37 | 3.97 | 2.73 |
| r²SCAN50-D4-ATM/def2-QZVP* | –2.92 | 3.37 | 3.97 | 2.73 |
| r²SCAN50-D4-ATM/def2-TZVPP | –2.90 | 3.36 | 3.97 | 2.73 |
| PBE0-D4/def2-QZVP | –2.04 | 2.40 | 2.78 | 1.90 |
| PW6B95-D4/def2-QZVP | –1.11 | 2.60 | 4.53 | 4.44 |
| ωB97X-V/def2-QZVP | –1.56 | 2.09 | 2.56 | 2.05 |


### ROT34

Statistics in MHz.

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4-ATM/def2-QZVP | –3.22 | 4.64 | 5.88 | 4.99 |
| r²SCANh-D4-ATM/def2-QZVP | 1.92 | 3.00 | 4.33 | 3.94 |
| r²SCANh-D4-ATM/def2-QZVP* | 1.39 | 2.81 | 3.98 | 3.78 |
| r²SCANh-D4-ATM/def2-TZVPP | 1.10 | 2.53 | 3.58 | 3.46 |
| r²SCAN0-D4-ATM/def2-QZVP | 10.46 | 10.46 | 12.76 | 7.40 |
| r²SCAN0-D4-ATM/def2-QZVP* | 10.10 | 10.10 | 12.45 | 7.39 |
| r²SCAN0-D4-ATM/def2-TZVPP | 10.28 | 10.28 | 12.63 | 7.46 |
| r²SCAN50-D4-ATM/def2-QZVP | 24.15 | 24.15 | 28.99 | 16.28 |
| r²SCAN50-D4-ATM/def2-QZVP* | 24.13 | 24.13 | 28.94 | 16.21 |
| r²SCAN50-D4-ATM/def2-TZVPP | 23.96 | 23.96 | 28.87 | 16.35 |
| PBE0-D4/def2-QZVP | 2.66 | 3.86 | 5.79 | 5.22 |
| PW6B95-D4/def2-QZVP | 11.71 | 11.71 | 14.92 | 9.38 |
| ωB97X-V/def2-QZVP | –7.71 | 7.71 | 10.40 | 7.09 |


### LB12

Statistics in pm.

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4-ATM/def2-QZVP | 1.81 | 3.57 | 5.67 | 5.61 |
| r²SCANh-D4-ATM/def2-QZVP | 2.33 | 3.88 | 6.00 | 5.77 |
| r²SCANh-D4-ATM/def2-QZVP* | 2.68 | 4.11 | 6.19 | 5.82 |
| r²SCANh-D4-ATM/def2-TZVPP | 1.92 | 4.29 | 6.07 | 6.01 |
| r²SCAN0-D4-ATM/def2-QZVP | 0.67 | 3.16 | 4.89 | 5.05 |
| r²SCAN0-D4-ATM/def2-QZVP* | 0.75 | 3.22 | 5.01 | 5.15 |
| r²SCAN0-D4-ATM/def2-TZVPP | 0.90 | 3.22 | 5.02 | 5.15 |
| r²SCAN50-D4-ATM/def2-QZVP | –2.24 | 5.48 | 9.03 | 9.14 |
| r²SCAN50-D4-ATM/def2-QZVP* | –2.48 | 5.45 | 9.00 | 9.03 |
| r²SCAN50-D4-ATM/def2-TZVPP | –2.05 | 5.98 | 9.08 | 9.24 |
| PBE0-D4/def2-QZVP | –0.17 | 3.16 | 5.09 | 5.31 |
| PW6B95-D4/def2-QZVP | –3.05 | 5.96 | 8.25 | 8.00 |
| ωB97X-V/def2-QZVP | –0.67 | 6.33 | 10.56 | 11.01 |

### CCse21

Bond lengths. Statistics in pm.

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4-ATM/def2-QZVP | 0.03 | 0.38 | 0.56 | 0.57 |
| r²SCANh-D4-ATM/def2-QZVP | –0.26 | 0.43 | 0.62 | 0.57 |
| r²SCANh-D4-ATM/def2-QZVP* | –0.26 | 0.43 | 0.62 | 0.57 |
| r²SCANh-D4-ATM/def2-TZVPP | –0.18 | 0.41 | 0.58 | 0.56 |
| r²SCAN0-D4-ATM/def2-QZVP | –0.69 | 0.70 | 0.99 | 0.71 |
| r²SCAN0-D4-ATM/def2-QZVP* | –0.69 | 0.70 | 0.98 | 0.71 |
| r²SCAN0-D4-ATM/def2-TZVPP | –0.69 | 0.70 | 0.99 | 0.71 |
| r²SCAN50-D4-ATM/def2-QZVP | –1.34 | 1.34 | 1.68 | 1.02 |
| r²SCAN50-D4-ATM/def2-QZVP* | –1.34 | 1.34 | 1.68 | 1.02 |
| r²SCAN50-D4-ATM/def2-TZVPP | –1.34 | 1.34 | 1.68 | 1.02 |
| PBE0-D4/def2-QZVP | –0.23 | 0.53 | 0.75 | 0.72 |
| PW6B95-D4/def2-QZVP | –0.60 | 0.60 | 0.81 | 0.56 |
| ωB97X-V/def2-QZVP | 0.01 | 0.51 | 0.73 | 9.74 |


Bond angles. Statistics in deg.

| method | MD | MAD | RMSD | SD |
| --- | ---:| ---:| ---:| ---:|
| r²SCAN-D4-ATM/def2-QZVP | 0.01 | 0.29 | 0.37 | 0.37 |
| r²SCANh-D4-ATM/def2-QZVP | 0.00 | 0.24 | 0.28 | 0.29 |
| r²SCANh-D4-ATM/def2-QZVP | 0.00 | 0.24 | 0.28 | 0.29 |
| r²SCANh-D4-ATM/def2-TZVPP | –0.01 | 0.24 | 0.29 | 0.30 |
| r²SCAN0-D4-ATM/def2-QZVP | 0.02 | 0.22 | 0.28 | 0.28 |
| r²SCAN0-D4-ATM/def2-QZVP* | 0.02 | 0.22 | 0.28 | 0.29 |
| r²SCAN0-D4-ATM/def2-TZVPP | 0.02 | 0.22 | 0.28 | 0.29 |
| r²SCAN50-D4-ATM/def2-QZVP | 0.07 | 0.28 | 0.38 | 0.38 |
| r²SCAN50-D4-ATM/def2-QZVP* | 0.07 | 0.28 | 0.38 | 0.38 |
| r²SCAN50-D4-ATM/def2-TZVPP | 0.07 | 0.28 | 0.38 | 0.38 |
| PBE0-D4/def2-QZVP | 0.03 | 0.31 | 0.38 | 0.38 |
| PW6B95-D4/def2-QZVP | 0.03 | 0.24 | 0.29 | 0.29 |
| ωB97X-V/def2-QZVP | 0.06 | 0.18 | 0.23 | 0.22 |



