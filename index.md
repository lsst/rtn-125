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




#### 1.2.3 LSST DP2 <--> SDSS (u-band)

Unfortunately, none of the LSST DP2 u-band science exposures overlap SDSS.  Therefore, for transformations between LSST DP2 u-band and SDSS u-band, we make use of synthetic photometry for stellar spectral energy distributions in the Pickles Stellar Spectra Library {cite}`1998PASP..110..863P` for the time being.  For other filters, we recommend the observed relations listed in Section 1.3.5 below.

:::{note}
The Pickles atlas does not include white dwarfs; it is not recommended to use these Pickles-based transformations for white dwarfs, especially in u-band, where white dwarfs differ significantly from other stellar types.



### 1.3. LSST DP2 Transformations

#### 1.3.1 LSST DP2 <--> DES

#### 1.3.1.1 Original

ComCam data were used to derive empirical transformations between DES and LSST LSST DP2 filters. All $S/N >$ 5 point sources in the DES footprint were selected, including quasars and non-standard stars.

#### 1.3.1.2 Updated




#### 1.3.2 LSST DP2 <--> Euclid


#### 1.3.3 LSST DP2 <--> Johnson-Cousins UBVRcIc

#### 1.3.4 LSST DP2 <--> GAIA DR3






#### 1.3.5 LSST DP2 <--> SDSS DR18



#### 1.3.6 LSST DP2 <--> PanStarrs1 DR2


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



#### 2.2.4 LSST DP2 <--> PS1 DR2



#### 2.2.5 LSST DP2 <--> SDSS DR18




#### 2.2.5 LSST DP2 <--> Stetson UBVRcIc




## References

```{bibliography}
```
