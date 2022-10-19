# CRU TS version 4.05 data management

[CRU TS](https://crudata.uea.ac.uk/cru/data/hrg/cru_ts_4.05/) are month-by-month variations in climate over the period 1901-2020 (time-series), provided on high-resolution (0.5x0.5 degree) grids, produced by CRU at the University of East Anglia and funded by the UK National Centre for Atmospheric Science (NCAS), a NERC collaborative centre. The CRU TS4.05 data were produced using angular-distance weighting (ADW) interpolation. All versions prior to 4.00 used triangulation routines in IDL. Please see the release notes for full details of this version update.

Variables include;
- cloud cover
- diurnal temperature range
- frost day frequency 
- wet day frequency
- potential evapotranspiration (PET)
- precipitation, daily mean temperature
- monthly average daily maximum and minimum temperature
- vapour pressure 

To integrate the climate variables in CRU TS into the TVSEP, vector data about administrative boundaries are needed. The vector data are derived from [geoBoundaries Global Administrative Database](http://www.geoboundaries.org).

# CRU TS version 4.05 data management

```
Relateted libraries
- library(raster)
- library(sf)
- library(dplyr)
```

