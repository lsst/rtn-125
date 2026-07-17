# Photometric Transformation Relations for the LSST Data Preview 2

```{abstract}
This technical note provides photometric transformation relations between the Vera C. Rubin Observatory’s Data Preview 2 (DP2) and other photometric systems. These transformations are derived using both synthetic and empirical data and are intended to support calibration and comparison across survey systems. We present both polynomial equations and lookup-table-based methods, depending on the available data and desired accuracy. The transformations are generally valid for stars with typical spectral energy distributions (SEDs), and caution should be used when applying them to objects with strong emission lines or atypical colors.
```


**DOI:** insert when published


## 0. General Overview

These transformations were derived by matching data from other surveys with the Rubin LSST DP2 {cite}`RTN-095` (UPDATE).  This technical note provides a general overview of the results from the calculation of transformations to and from the Rubin LSST DP2 photometric system.  Details of the process will be presented in one or more future journal articles (Porter et al., _in preparation_, etc.).

This technical note should be considered a living document:  as additional photometric systems are analyzed and/or current transformations are updated, this document will be updated to include the new material.

## 1. Polynomial Fit Transformations

### 1.1. Overview

A simple and popular method of performing photometric transformations between two photometric systems is to perform a polynomial fit between the difference in magnitudes between a filter band in one system (say, the LSSTCam $i$ band) and another system (say, the DES $i$ band) and one or more color indices in one of the two sytstems (say, the $(g-i)$ color in the DES system).  These fits can be low-order (say, a first-degree polynomial) or high-order (say, a third or higher degree polynomial).  They can be a single fit over the full color range, or they can be solved "piece-wise", with breaks in the fit at one or more values of the color index.  Here, a balance between simplicity and accuracy is attempted, aiming for the lowest-order fit that still gives a reasonable level of accuracy (typically with RMS'es of a few hundredths to a few tenths of a magnitude.)  If higher accuracy is required -- to the extent that complexity is not a major factor -- use of the Lookup Table (Interpolation) Transformations in Section 2 is recommended.


### 1.2. Synthetic LSSTCam Transformations

Synthetic magnitudes were derived by integrating spectrophotometric spectra from the Pickles Stellar Spectra Library {cite}`1998PASP..110..863P` with filter passband transmission curves for LSSTCam and other photometric systems. These magnitudes were calculated using broad-band absolute magnitude definitions and processed using a Python-based fitting code to generate transformation equations. Due to the limited number of stars in the Pickles library (~100), the resulting plots are sparse but provide a consistent reference.

#### 1.2.1 LSST <--> DES



#### 1.2.2 LSST <--> TESS




#### 1.2.3 LSST DP2 <--> SDSS




### 1.3. LSST DP2 Transformations

#### 1.3.1 LSST DP2 <--> DES

| Conversion             | Transformation Equation                        |   RMS | Applicable Color Range      | QA Plot                                                                                       |
|:-----------------------|:-----------------------------------------------|------:|:----------------------------|:----------------------------------------------------------------------------------------------|
| $g_{LSST} \to g_{des}$ | $g_{des} - g_{LSST} = +0.011 (g−i)LSST -0.013$ | 0.015 | $-1.0 < (g−i)LSST \leq 2.3$ | [link](_static/plots/qaPlot.LSST_DP2_to_DESDR2.fit.dmag_g_des-g_LSST.gi_LSST.norder1.qa1.png) |
| $g_{LSST} \to g_{des}$ | $g_{des} - g_{LSST} = -0.032 (g−i)LSST +0.080$ | 0.026 | $2.3 < (g−i)LSST \leq 3.8$  | [link](_static/plots/qaPlot.LSST_DP2_to_DESDR2.fit.dmag_g_des-g_LSST.gi_LSST.norder1.qa1.png) |
|                        |                                                |       |                             |                                                                                               |
| $r_{LSST} \to r_{des}$ | $r_{des} - r_{LSST} = -0.058 (g−i)LSST +0.005$ | 0.008 | $-0.8 < (g−i)LSST \leq 2.0$ | [link](_static/plots/qaPlot.LSST_DP2_to_DESDR2.fit.dmag_r_des-r_LSST.gi_LSST.norder1.qa1.png) |
| $r_{LSST} \to r_{des}$ | $r_{des} - r_{LSST} = -0.122 (g−i)LSST +0.133$ | 0.016 | $2.0 < (g−i)LSST \leq 3.8$  | [link](_static/plots/qaPlot.LSST_DP2_to_DESDR2.fit.dmag_r_des-r_LSST.gi_LSST.norder1.qa1.png) |
|                        |                                                |       |                             |                                                                                               |
| $i_{LSST} \to i_{des}$ | $i_{des} - i_{LSST} = -0.049 (g−i)LSST +0.018$ | 0.01  | $-0.8 < (g−i)LSST \leq 1.8$ | [link](_static/plots/qaPlot.LSST_DP2_to_DESDR2.fit.dmag_i_des-i_LSST.gi_LSST.norder1.qa1.png) |
| $i_{LSST} \to i_{des}$ | $i_{des} - i_{LSST} = -0.121 (g−i)LSST +0.144$ | 0.012 | $1.8 < (g−i)LSST \leq 3.8$  | [link](_static/plots/qaPlot.LSST_DP2_to_DESDR2.fit.dmag_i_des-i_LSST.gi_LSST.norder1.qa1.png) |
|                        |                                                |       |                             |                                                                                               |
| $z_{LSST} \to z_{des}$ | $z_{des} - z_{LSST} = -0.328 (i−z)LSST -0.002$ | 0.009 | $-0.3 < (i−z)LSST \leq 0.2$ | [link](_static/plots/qaPlot.LSST_DP2_to_DESDR2.fit.dmag_z_des-z_LSST.iz_LSST.norder1.qa1.png) |
| $z_{LSST} \to z_{des}$ | $z_{des} - z_{LSST} = -0.217 (i−z)LSST -0.021$ | 0.01  | $0.2 < (i−z)LSST \leq 1.3$  | [link](_static/plots/qaPlot.LSST_DP2_to_DESDR2.fit.dmag_z_des-z_LSST.iz_LSST.norder1.qa1.png) |
|                        |                                                |       |                             |                                                                                               |
| $y_{LSST} \to Y_{des}$ | $Y_{des} - y_{LSST} = -0.119 (i−z)LSST +0.018$ | 0.02  | $-0.6 < (i−z)LSST \leq 0.2$ | [link](_static/plots/qaPlot.LSST_DP2_to_DESDR2.fit.dmag_Y_des-y_LSST.iz_LSST.norder1.qa1.png) |
| $y_{LSST} \to Y_{des}$ | $Y_{des} - y_{LSST} = -0.051 (i−z)LSST +0.007$ | 0.018 | $0.2 < (i−z)LSST \leq 2.5$  | [link](_static/plots/qaPlot.LSST_DP2_to_DESDR2.fit.dmag_Y_des-y_LSST.iz_LSST.norder1.qa1.png) |


| Conversion             | Transformation Equation                       |   RMS | Applicable Color Range     | QA Plot                                                                                      |
|:-----------------------|:----------------------------------------------|------:|:---------------------------|:---------------------------------------------------------------------------------------------|
| $g_{des} \to g_{LSST}$ | $g_{LSST} - g_{des} = -0.011 (g−i)des +0.014$ | 0.014 | $-0.8 < (g−i)des \leq 2.3$ | [link](_static/plots/qaPlot.DESDR2_to_LSST_DP2.fit.dmag_g_LSST-g_des.gi_des.norder1.qa1.png) |
| $g_{des} \to g_{LSST}$ | $g_{LSST} - g_{des} = +0.020 (g−i)des -0.054$ | 0.025 | $2.3 < (g−i)des \leq 4.0$  | [link](_static/plots/qaPlot.DESDR2_to_LSST_DP2.fit.dmag_g_LSST-g_des.gi_des.norder1.qa1.png) |
|                        |                                               |       |                            |                                                                                              |
| $r_{des} \to r_{LSST}$ | $r_{LSST} - r_{des} = +0.054 (g−i)des -0.003$ | 0.008 | $-0.8 < (g−i)des \leq 2.0$ | [link](_static/plots/qaPlot.DESDR2_to_LSST_DP2.fit.dmag_r_LSST-r_des.gi_des.norder1.qa1.png) |
| $r_{des} \to r_{LSST}$ | $r_{LSST} - r_{des} = +0.108 (g−i)des -0.116$ | 0.015 | $2.0 < (g−i)des \leq 4.0$  | [link](_static/plots/qaPlot.DESDR2_to_LSST_DP2.fit.dmag_r_LSST-r_des.gi_des.norder1.qa1.png) |
|                        |                                               |       |                            |                                                                                              |
| $i_{des} \to i_{LSST}$ | $i_{LSST} - i_{des} = +0.045 (g−i)des -0.016$ | 0.009 | $-0.8 < (g−i)des \leq 1.8$ | [link](_static/plots/qaPlot.DESDR2_to_LSST_DP2.fit.dmag_i_LSST-i_des.gi_des.norder1.qa1.png) |
| $i_{des} \to i_{LSST}$ | $i_{LSST} - i_{des} = +0.109 (g−i)des -0.132$ | 0.012 | $1.8 < (g−i)des \leq 4.0$  | [link](_static/plots/qaPlot.DESDR2_to_LSST_DP2.fit.dmag_i_LSST-i_des.gi_des.norder1.qa1.png) |
|                        |                                               |       |                            |                                                                                              |
| $z_{des} \to z_{LSST}$ | $z_{LSST} - z_{des} = +0.319 (i−z)des -0.001$ | 0.007 | $-0.3 < (i−z)des \leq 0.2$ | [link](_static/plots/qaPlot.DESDR2_to_LSST_DP2.fit.dmag_z_LSST-z_des.iz_des.norder1.qa1.png) |
| $z_{des} \to z_{LSST}$ | $z_{LSST} - z_{des} = +0.241 (i−z)des +0.013$ | 0.008 | $0.2 < (i−z)des \leq 1.0$  | [link](_static/plots/qaPlot.DESDR2_to_LSST_DP2.fit.dmag_z_LSST-z_des.iz_des.norder1.qa1.png) |
|                        |                                               |       |                            |                                                                                              |
| $Y_{des} \to y_{LSST}$ | $y_{LSST} - Y_{des} = +0.120 (i−z)des -0.019$ | 0.019 | $-0.3 < (i−z)des \leq 0.2$ | [link](_static/plots/qaPlot.DESDR2_to_LSST_DP2.fit.dmag_y_LSST-Y_des.iz_des.norder1.qa1.png) |
| $Y_{des} \to y_{LSST}$ | $y_{LSST} - Y_{des} = +0.056 (i−z)des -0.009$ | 0.018 | $0.2 < (i−z)des \leq 1.1$  | [link](_static/plots/qaPlot.DESDR2_to_LSST_DP2.fit.dmag_y_LSST-Y_des.iz_des.norder1.qa1.png) |



#### 1.3.2 LSST DP2 <--> Euclid


#### 1.3.3 LSST DP2 <--> Johnson-Cousins UBVRcIc

#### 1.3.4 LSST DP2 <--> GAIA DR3

| Conversion               | Transformation Equation                                                   |   RMS | Applicable Color Range        | QA Plot                                                                                           |
|:-------------------------|:--------------------------------------------------------------------------|------:|:------------------------------|:--------------------------------------------------------------------------------------------------|
| $g_{LSST} \to G_{gaia}$  | $G_{gaia} - g_{LSST} = -0.037 (g-i)_{LSST}^2 -0.600 (g-i)_{LSST} -0.056$  | 0.01  | $0.2 < (g-i)_{LSST} \leq 2.9$ | [link](_static/plots/qaPlot.LSST_DP2_to_Gaia_DR3.fit.dmag_G_gaia-g_LSST.gi_LSST.norder2.qa1.png)  |
|                          |                                                                           |       |                               |                                                                                                   |
| $g_{LSST} \to BP_{gaia}$ | $BP_{gaia} - g_{LSST} = +0.096 (g-i)_{LSST}^2 -0.487 (g-i)_{LSST} +0.194$ | 0.037 | $0.3 < (g-i)_{LSST} \leq 3.2$ | [link](_static/plots/qaPlot.LSST_DP2_to_Gaia_DR3.fit.dmag_BP_gaia-g_LSST.gi_LSST.norder2.qa1.png) |
|                          |                                                                           |       |                               |                                                                                                   |
| $r_{LSST} \to RP_{gaia}$ | $RP_{gaia} - r_{LSST} = -0.267 (g-i)_{LSST}^2 +0.242 (g-i)_{LSST} -0.563$ | 0.043 | $0.3 < (g-i)_{LSST} \leq 3.2$ | [link](_static/plots/qaPlot.LSST_DP2_to_Gaia_DR3.fit.dmag_RP_gaia-r_LSST.gi_LSST.norder2.qa1.png) |


| Conversion              | Transformation Equation                                                      |   RMS | Applicable Color Range           | QA Plot                                                                                             |
|:------------------------|:-----------------------------------------------------------------------------|------:|:---------------------------------|:----------------------------------------------------------------------------------------------------|
| $G_{gaia} \to g_{LSST}$ | $g_{LSST} - G_{gaia} = -0.099 (BP-RP)_{gaia}^2 +1.172 (BP-RP)_{gaia} -0.527$ | 0.036 | $0.6 < (BP-RP)_{gaia} \leq 3.1$  | [link](_static/plots/qaPlot.Gaia_DR3_to_LSST_DP2.fit.dmag_g_LSST-G_gaia.BP_RP_gaia.norder2.qa1.png) |
|                         |                                                                              |       |                                  |                                                                                                                                  |
| $G_{gaia} \to r_{LSST}$ | $r_{LSST} - G_{gaia} = +0.286 (BP-RP)_{gaia}^2 -0.650 (BP-RP)_{gaia} +0.325$ | 0.024 | $0.5 < (BP-RP)_{gaia} \leq 3.1$  | [link](_static/plots/qaPlot.Gaia_DR3_to_LSST_DP2.fit.dmag_r_LSST-G_gaia.BP_RP_gaia.norder2.qa1.png) |
|                         |                                                                              |       |                                  |                                                                                                                                  |
| $G_{gaia} \to i_{LSST}$ | $i_{LSST} - G_{gaia} = +0.104 (BP-RP)_{gaia}^2 -0.683 (BP-RP)_{gaia} +0.347$ | 0.01  | $-0.2 < (BP-RP)_{gaia} \leq 3.3$ | [link](_static/plots/qaPlot.Gaia_DR3_to_LSST_DP2.fit.dmag_i_LSST-G_gaia.BP_RP_gaia.norder2.qa1.png) |
|                         |                                                                              |       |                                  |                                                                                                                                  |
| $G_{gaia} \to z_{LSST}$ | $z_{LSST} - G_{gaia} = +0.055 (BP-RP)_{gaia}^2 -0.817 (BP-RP)_{gaia} +0.464$ | 0.021 | $-0.4 < (BP-RP)_{gaia} \leq 3.3$ | [link](_static/plots/qaPlot.Gaia_DR3_to_LSST_DP2.fit.dmag_z_LSST-G_gaia.BP_RP_gaia.norder2.qa1.png) |
|                         |                                                                              |       |                                  |                                                                                                                                  |
| $G_{gaia} \to y_{LSST}$ | $y_{LSST} - G_{gaia} = +0.044 (BP-RP)_{gaia}^2 -0.914 (BP-RP)_{gaia} +0.533$ | 0.026 | $0.3 < (BP-RP)_{gaia} \leq 3.3$  | [link](_static/plots/qaPlot.Gaia_DR3_to_LSST_DP2.fit.dmag_y_LSST-G_gaia.BP_RP_gaia.norder2.qa1.png) |



#### 1.3.5 LSST DP2 <--> SDSS DR18

| Conversion                | Transformation Equation                           |   RMS | Applicable Color Range      | QA Plot                                                                                           |
|:--------------------------|:--------------------------------------------------|------:|:----------------------------|:--------------------------------------------------------------------------------------------------|
| $u_{LSST} \to u_{sdss}$   | $u_{sdss} - u_{LSST} = -0.029 (g−i)LSST +0.148$   | 0.075 | $-0.9 < (g−i)LSST \leq 2.1$ | [link](_static/plots/qaPlot.LSSTDP2_to_SDSSDR18.fit.dmag_u_sdss-u_LSST.gi_LSST.norder1.qa1.png)   |
|                           |                                                   |       |                             |                                                                                                   |
| $g_{LSST} \to g_{sdss}$   | $g_{sdss} - g_{LSST} = +0.064 (g−i)LSST -0.013$   | 0.021 | $-1.3 < (g−i)LSST \leq 2.2$ | [link](_static/plots/qaPlot.LSSTDP2_to_SDSSDR18.fit.dmag_g_sdss-g_LSST.gi_LSST.norder1.qa1.png)   |
|                           |                                                   |       |                             |                                                                                                   |
| $r_{LSST} \to r_{sdss}$   | $r_{sdss} - r_{LSST} = +0.008 (g−i)LSST -0.008$   | 0.019 | $-1.3 < (g−i)LSST \leq 2.2$ | [link](_static/plots/qaPlot.LSSTDP2_to_SDSSDR18.fit.dmag_r_sdss-r_LSST.gi_LSST.norder1.qa1.png)   |
|                           |                                                   |       |                             |                                                                                                   |
| $i_{LSST} \to i_{sdss}$   | $i_{sdss} - i_{LSST} = +0.010 (g−i)LSST -0.021$   | 0.02  | $-0.9 < (g−i)LSST \leq 2.2$ | [link](_static/plots/qaPlot.LSSTDP2_to_SDSSDR18.fit.dmag_i_sdss-i_LSST.gi_LSST.norder1.qa1.png)   |
|                           |                                                   |       |                             |                                                                                                   |
| $z_{LSST} \to z_{sdss}$   | $z_{sdss} - z_{LSST} = -0.029 (g−i)LSST -0.021$   | 0.03  | $-1.3 < (g−i)LSST \leq 2.2$ | [link](_static/plots/qaPlot.LSSTDP2_to_SDSSDR18.fit.dmag_z_sdss-z_LSST.gi_LSST.norder1.qa1.png)   |
|                           |                                                   |       |                             |                                                                                                   |
| $gi_{LSST} \to gi_{sdss}$ | $gi_{sdss} - gi_{LSST} = +0.053 (g−i)LSST +0.008$ | 0.03  | $-0.9 < (g−i)LSST \leq 2.2$ | [link](_static/plots/qaPlot.LSSTDP2_to_SDSSDR18.fit.dmag_gi_sdss-gi_LSST.gi_LSST.norder1.qa1.png) |

| Conversion                | Transformation Equation                              |   RMS | Applicable Color Range         | QA Plot                                                                                           |
|:--------------------------|:-----------------------------------------------------|------:|:-------------------------------|:--------------------------------------------------------------------------------------------------|
| $u_{sdss} \to u_{LSST}$   | $u_{LSST} - u_{sdss} = +0.027 (g-i)_{sdss} -0.148$   | 0.075 | $-0.9 < (g-i)_{sdss} \leq 2.2$ | [link](_static/plots/qaPlot.SDSSDR18_to_LSSTDP2.fit.dmag_u_LSST-u_sdss.gi_sdss.norder1.qa1.png)   |
|                           |                                                      |       |                                |                                                                                                   |
| $g_{sdss} \to g_{LSST}$   | $g_{LSST} - g_{sdss} = -0.065 (g-i)_{sdss} +0.017$   | 0.02  | $-0.9 < (g-i)_{sdss} \leq 2.3$ | [link](_static/plots/qaPlot.SDSSDR18_to_LSSTDP2.fit.dmag_g_LSST-g_sdss.gi_sdss.norder1.qa1.png)   |
|                           |                                                      |       |                                |                                                                                                   |
| $r_{sdss} \to r_{LSST}$   | $r_{LSST} - r_{sdss} = -0.007 (g-i)_{sdss} +0.008$   | 0.019 | $-0.9 < (g-i)_{sdss} \leq 2.3$ | [link](_static/plots/qaPlot.SDSSDR18_to_LSSTDP2.fit.dmag_r_LSST-r_sdss.gi_sdss.norder1.qa1.png)   |
|                           |                                                      |       |                                |                                                                                                   |
| $i_{sdss} \to i_{LSST}$   | $i_{LSST} - i_{sdss} = -0.004 (g-i)_{sdss} +0.017$   | 0.02  | $-0.9 < (g-i)_{sdss} \leq 2.3$ | [link](_static/plots/qaPlot.SDSSDR18_to_LSSTDP2.fit.dmag_i_LSST-i_sdss.gi_sdss.norder1.qa1.png)   |
|                           |                                                      |       |                                |                                                                                                   |
| $z_{sdss} \to z_{LSST}$   | $z_{LSST} - z_{sdss} = +0.028 (g-i)_{sdss} +0.021$   | 0.03  | $-0.9 < (g-i)_{sdss} \leq 2.3$ | [link](_static/plots/qaPlot.SDSSDR18_to_LSSTDP2.fit.dmag_z_LSST-z_sdss.gi_sdss.norder1.qa1.png)   |
|                           |                                                      |       |                                |                                                                                                   |
| $z_{sdss} \to y_{LSST}$   | $y_{LSST} - z_{sdss} = -0.099 (g-i)_{sdss} +0.082$   | 0.035 | $-0.9 < (g-i)_{sdss} \leq 2.3$ | [link](_static/plots/qaPlot.SDSSDR18_to_LSSTDP2.fit.dmag_y_LSST-z_sdss.gi_sdss.norder1.qa1.png)   |
|                           |                                                      |       |                                |                                                                                                   |
| $gi_{sdss} \to gi_{LSST}$ | $gi_{LSST} - gi_{sdss} = -0.062 (g-i)_{sdss} +0.002$ | 0.029 | $-0.9 < (g-i)_{sdss} \leq 2.3$ | [link](_static/plots/qaPlot.SDSSDR18_to_LSSTDP2.fit.dmag_gi_LSST-gi_sdss.gi_sdss.norder1.qa1.png) |


#### 1.3.6 LSST DP2 <--> PanStarrs1 DR2


| Conversion             | Transformation Equation                           |   RMS | Applicable Color Range         | QA Plot                                                                                        |
|:-----------------------|:--------------------------------------------------|------:|:-------------------------------|:-----------------------------------------------------------------------------------------------|
| $g_{LSST} \to g_{ps1}$ | $g_{ps1} - g_{LSST} = -0.029 (g-i)_{LSST} -0.028$ | 0.03  | $-0.7 < (g-i)_{LSST} \leq 3.7$ | [link](_static/plots/qaPlot.LSST_DP2_to_PS1_DR2.fit.dmag_g_ps1-g_LSST.gi_LSST.norder1.qa1.png) |
|                        |                                                   |       |                                |                                                                                                |
| $r_{LSST} \to r_{ps1}$ | $r_{ps1} - r_{LSST} = +0.000 (g-i)_{LSST} -0.002$ | 0.017 | $-0.7 < (g-i)_{LSST} \leq 3.7$ | [link](_static/plots/qaPlot.LSST_DP2_to_PS1_DR2.fit.dmag_r_ps1-r_LSST.gi_LSST.norder1.qa1.png) |
|                        |                                                   |       |                                |                                                                                                |
| $i_{LSST} \to i_{ps1}$ | $i_{ps1} - i_{LSST} = +0.007 (g-i)_{LSST} -0.006$ | 0.012 | $-0.7 < (g-i)_{LSST} \leq 3.7$ | [link](_static/plots/qaPlot.LSST_DP2_to_PS1_DR2.fit.dmag_i_ps1-i_LSST.gi_LSST.norder1.qa1.png) |
|                        |                                                   |       |                                |                                                                                                |
| $z_{LSST} \to z_{ps1}$ | $z_{ps1} - z_{LSST} = +0.007 (i-z)_{LSST} +0.004$ | 0.012 | $-0.2 < (i-z)_{LSST} \leq 1.3$ | [link](_static/plots/qaPlot.LSST_DP2_to_PS1_DR2.fit.dmag_z_ps1-z_LSST.iz_LSST.norder1.qa1.png) |
|                        |                                                   |       |                                |                                                                                                |
| $y_{LSST} \to y_{ps1}$ | $y_{ps1} - y_{LSST} = +0.060 (z-y)_{LSST} -0.025$ | 0.025 | $-0.5 < (z-y)_{LSST} \leq 1.0$ | [link](_static/plots/qaPlot.LSST_DP2_to_PS1_DR2.fit.dmag_y_ps1-y_LSST.zy_LSST.norder1.qa1.png) |


| Conversion             | Transformation Equation                          |   RMS | Applicable Color Range        | QA Plot                                                                                       |
|:-----------------------|:-------------------------------------------------|------:|:------------------------------|:----------------------------------------------------------------------------------------------|
| $g_{ps1} \to g_{LSST}$ | $g_{LSST} - g_{ps1} = +0.028 (g-i)_{ps1} +0.031$ | 0.031 | $-0.7 < (g-i)_{ps1} \leq 3.3$ | [link](_static/plots/qaPlot.PS1_DR2_to_LSST_DP2.fit.dmag_g_LSST-g_ps1.gi_ps1.norder1.qa1.png) |
|                        |                                                  |       |                               |                                                                                               |
| $r_{ps1} \to r_{LSST}$ | $r_{LSST} - r_{ps1} = -0.001 (g-i)_{ps1} +0.002$ | 0.017 | $-0.7 < (g-i)_{ps1} \leq 3.4$ | [link](_static/plots/qaPlot.PS1_DR2_to_LSST_DP2.fit.dmag_r_LSST-r_ps1.gi_ps1.norder1.qa1.png) |
|                        |                                                  |       |                               |                                                                                               |
| $i_{ps1} \to i_{LSST}$ | $i_{LSST} - i_{ps1} = -0.007 (g-i)_{ps1} +0.006$ | 0.012 | $-0.7 < (g-i)_{ps1} \leq 3.4$ | [link](_static/plots/qaPlot.PS1_DR2_to_LSST_DP2.fit.dmag_i_LSST-i_ps1.gi_ps1.norder1.qa1.png) |
|                        |                                                  |       |                               |                                                                                               |
| $z_{ps1} \to z_{LSST}$ | $z_{LSST} - z_{ps1} = -0.004 (i-z)_{ps1} -0.005$ | 0.012 | $-0.3 < (i-z)_{ps1} \leq 1.0$ | [link](_static/plots/qaPlot.PS1_DR2_to_LSST_DP2.fit.dmag_z_LSST-z_ps1.iz_ps1.norder1.qa1.png) |
|                        |                                                  |       |                               |                                                                                               |
| $y_{ps1} \to y_{LSST}$ | $y_{LSST} - y_{ps1} = +0.013 (z-y)_{ps1} +0.015$ | 0.026 | $-0.2 < (z-y)_{ps1} \leq 0.5$ | [link](_static/plots/qaPlot.PS1_DR2_to_LSST_DP2.fit.dmag_y_LSST-y_ps1.zy_ps1.norder1.qa1.png) |


## 2. Lookup Table (Interpolation) Transformations

### 2.1. Overview

Interpolation methods were used to model complex or non-linear relationships between survey measurements.
These methods rely on binning color indices and computing median magnitude differences.

The lookup tables included in the tables below can be used to convert data from one photometric system to the other via interpolation methods.
The files contain the delta_mag vs color locus in bins of (typically) 0.1-mag binsize along the color axis.
Here is a python code that takes the lookup table CSV file for the transformation from LSST DP2 $g$-band and $(g-i)$ color to DES $g$-band. The code makes use of the `scipy` `interpolate` routine.

```python
import pandas as pd
from scipy import interpolate

# Read in lookup table CSV file...
lut_name = 'transInterp.ComCam_to_des.g_gi_ComCam.csv'
df_interp = pd.read_csv(lut_name)

# Create linear interpolation of the median dmag vs. color
#  bin calculated above...
response = interpolate.interp1d(\
                  df_interp.bin_label.values.astype(float), \
                  df_interp.bin_median.values, \
                  bounds_error=False, fill_value=0., \
                  kind='linear')

# Read in file with data to be transformed...
df = pd.read_csv(inputFile)
# The following assumes a column with LSST DP2 g and
# a column with LSST DP2 (g-i) in this file...
df['offset'] = response(df['gi_ComCam'].values)
df['g_des'] = df['g_ComCam'] + df['offset']
```



### 2.2 LSST DP2 Transformations

#### 2.2.1 LSST DP2 <--> DES DR2

##### 2.2.1.1 Original



##### 2.2.1.2 Updated







#### 2.2.2 LSST DP2 <--> Euclid



#### 2.2.3 LSST DP2 <--> GAIA DR3

| Conversion               |   RMS | Applicable Color Range     | QA Plot                                                                          | Lookup Table                                                             |
|:-------------------------|------:|:---------------------------|:---------------------------------------------------------------------------------|:-------------------------------------------------------------------------|
| $r_{LSST} \to G_{gaia}$  | 0.02  | $0.3 < (g-i)_{LSST} < 2.9$ | [link](_static/plots/qaPlot_transInterp.LSST_DR2_to_GaiaDR3.G_gaia_gi_LSST.png)  | [link](_static/data/transInterp.LSST_DR2_to_GaiaDR3.G_gaia_gi_LSST.csv)  |
| $g_{LSST} \to BP_{gaia}$ | 0.025 | $0.3 < (g-i)_{LSST} < 2.9$ | [link](_static/plots/qaPlot_transInterp.LSST_DR2_to_GaiaDR3.BP_gaia_gi_LSST.png) | [link](_static/data/transInterp.LSST_DR2_to_GaiaDR3.BP_gaia_gi_LSST.csv) |
| $r_{LSST} \to RP_{gaia}$ | 0.028 | $0.3 < (g-i)_{LSST} < 2.9$ | [link](_static/plots/qaPlot_transInterp.LSST_DR2_to_GaiaDR3.RP_gaia_gi_LSST.png) | [link](_static/data/transInterp.LSST_DR2_to_GaiaDR3.RP_gaia_gi_LSST.csv) |


| Conversion              |   RMS | Applicable Color Range       | QA Plot                                                                            | Lookup Table                                                               |
|:------------------------|------:|:-----------------------------|:-----------------------------------------------------------------------------------|:---------------------------------------------------------------------------|
| $G_{gaia} \to g_{LSST}$ | 0.027 | $0.6 < (BP-RP)_{gaia} < 2.9$ | [link](_static/plots/qaPlot_transInterp.GaiaDR3_to_LSST_DR2.g_LSST_BP_RP_gaia.png) | [link](_static/data/transInterp.GaiaDR3_to_LSST_DR2.g_LSST_BP_RP_gaia.csv) |
| $G_{gaia} \to r_{LSST}$ | 0.018 | $0.6 < (BP-RP)_{gaia} < 2.9$ | [link](_static/plots/qaPlot_transInterp.GaiaDR3_to_LSST_DR2.r_LSST_BP_RP_gaia.png) | [link](_static/data/transInterp.GaiaDR3_to_LSST_DR2.r_LSST_BP_RP_gaia.csv) |
| $G_{gaia} \to i_{LSST}$ | 0.01  | $0.6 < (BP-RP)_{gaia} < 2.9$ | [link](_static/plots/qaPlot_transInterp.GaiaDR3_to_LSST_DR2.i_LSST_BP_RP_gaia.png) | [link](_static/data/transInterp.GaiaDR3_to_LSST_DR2.i_LSST_BP_RP_gaia.csv) |
| $G_{gaia} \to z_{LSST}$ | 0.018 | $0.6 < (BP-RP)_{gaia} < 2.9$ | [link](_static/plots/qaPlot_transInterp.GaiaDR3_to_LSST_DR2.z_LSST_BP_RP_gaia.png) | [link](_static/data/transInterp.GaiaDR3_to_LSST_DR2.z_LSST_BP_RP_gaia.csv) |
| $G_{gaia} \to y_{LSST}$ | 0.024 | $0.6 < (BP-RP)_{gaia} < 2.9$ | [link](_static/plots/qaPlot_transInterp.GaiaDR3_to_LSST_DR2.y_LSST_BP_RP_gaia.png) | [link](_static/data/transInterp.GaiaDR3_to_LSST_DR2.y_LSST_BP_RP_gaia.csv) |


#### 2.2.4 LSST DP2 <--> PS1 DR2



#### 2.2.5 LSST DP2 <--> SDSS DR18




#### 2.2.5 LSST DP2 <--> Stetson UBVRcIc




## References

```{bibliography}
```
