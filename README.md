# Climate Time-Seires Data: CRU TS 
Date: 2022-10-18



## CRU TS version 4.05 data management

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

# geoBoundaries Global Administrative Database: geoBoundaries 

To integrate the climate variables in CRU TS into the TVSEP, vector data about administrative boundaries are needed. The vector data are derived from [geoBoundaries Global Administrative Database](http://www.geoboundaries.org).


### CRU TS version 4.05 and geoBoundaries data management
```
Relateted libraries
- library(raster)
- library(sf)
- library(dplyr)
```


### Import file
``` r 
syntax

admin <-read_sf("THA_TVSEP_revised.shp")                              # import shapefile (vector data)
temperature<-brick("tmp.cru_ts4.05.2001.2010dat.nc", varname = "tmp") # create multi-layer raster object of time-series climate data in netCDF (.nc) format
```

### Extract climate parameters (mean) into administrative lavel data

``` r 
syntax

MeanTemperature<-extract(x=tmp2001_10, y=adminTH, fun=mean, df=T, na.rm = T)  # extract values (mean, max, min, etc.) from a raster object at the locations of spatial vector data.
```

| ID_TVSEP| X2001.01.16| X2001.02.15| X2001.03.16|
|--------:|-----------:|-----------:|-----------:|
|     3101|       26.25|      27.575|      28.425|
|     3102|       26.25|      27.550|      28.550|
|     3103|       26.35|      27.600|      28.500|
|     3104|       26.25|      27.650|      28.200|
|     3105|       25.90|      27.400|      28.050|
|     3106|       26.60|      27.850|      28.400|

