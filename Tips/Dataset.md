# Dataset

## NLDAS / GLDAS
### Account
fkwai
19900323kK

### Document
https://disc.sci.gsfc.nasa.gov/hydrology/documentation

https://hydro1.gesdisc.eosdis.nasa.gov/data/GLDAS/GLDAS_NOAH025_3H.2.1/doc/README_GLDAS2.pdf

### Download

https://disc.sci.gsfc.nasa.gov/uui/datasets?keywords=NLDAS

https://disc.sci.gsfc.nasa.gov/datasets/GLDAS_NOAH025_3H_V2.1/summary?keywords=GLDAS

* Forcing Primary

```
wget --load-cookies ~/.urs_cookies --save-cookies ~/.urs_cookies --auth-no-challenge=on --keep-session-cookies -r -c -nH -np -A grb,xml "https://hydro1.gesdisc.eosdis.nasa.gov/data/NLDAS/NLDAS_FORA0125_H.002/2015/"
```
* Forcing Secondary

```
wget --load-cookies ~/.urs_cookies --save-cookies ~/.urs_cookies --auth-no-challenge=on --keep-session-cookies -r -c -nH -np -A grb,xml "https://hydro1.gesdisc.eosdis.nasa.gov/data/NLDAS/NLDAS_FORB0125_H.002/2015/"
```
* Noah

```
wget --load-cookies ~/.urs_cookies --save-cookies ~/.urs_cookies --auth-no-challenge=on --keep-session-cookies -r -c -nH -np -A grb,xml "https://hydro1.gesdisc.eosdis.nasa.gov/data/NLDAS/NLDAS_NOAH0125_H.002/2015/"
```

### Read using Matlab
[An official instruction](https://disc.gsfc.nasa.gov/recipes/?q=recipes/How-to-Read-GLDAS-or-NLDAS-GRIB-formatted-Data-with-MATLAB-0)


## SMAP
### Main page

[JPL and NASA page](https://smap.jpl.nasa.gov/data/) - main page

[NSIDC page](https://nsidc.org/data/smap/smap-data.html) - where SMAP soil moisture data is published

### Download
Google NSIDC SMAP. Both SMAP products and validation data are there.

* SMP L2 v4
  ```
  wget --load-cookies ~/.urs_cookies --save-cookies ~/.urs_cookies --keep-session-cookies --no-check-certificate --auth-no-challenge=on -r --reject "index.html*" -np -e robots=off "https://n5eil01u.ecs.nsidc.org/SMAP/SPL2SMP.004/"
  ```
* SMP L3 v4
  ```
  wget --load-cookies ~/.urs_cookies --save-cookies ~/.urs_cookies --keep-session-cookies --no-check-certificate --auth-no-challenge=on -r --reject "index.html*" -np -e robots=off "https://n5eil01u.ecs.nsidc.org/SMAP/SPL3SMP.004/"
  ```

### Data Description

* HDF code examples:  
  [http://hdfeos.org/zoo/index\_openNSIDC\_Examples.php\#SMAP](http://hdfeos.org/zoo/index_openNSIDC_Examples.php#SMAP)

* Data Fields:  
  [spl3smp](https://nsidc.org/data/smap/spl3smp/data-fields)
  [spl4sm](http://nsidc.org/data/smap/spl4sm/data-fields)

* L2 doc:
  [https://nsidc.org/data/docs/daac/smap/sp\_l2\_smp/](https://nsidc.org/data/docs/daac/smap/sp_l2_smp/)

### Cal/Val
[NSIDC-0666.001](https://nsidc.org/data/nsidc-0666/versions/1)
[NSIDC-0712.001](https://nsidc.org/data/nsidc-0712/versions/1)

## TRMM / GPM
https://disc.sci.gsfc.nasa.gov/datasets/GPM_3IMERGDF_V05/summary

## in-situ Soil Moisture
### SCAN
need to download from AWDB seb service. [help page](https://www.wcc.nrcs.usda.gov/web_service/awdb_web_service_landing.htm)

Download and reading code is ready.

Data example [url](https://wcc.sc.egov.usda.gov/nwcc/view?intervalType=Historic+&report=SCAN&timeseries=Daily&format=copy&sitenum=0581&year=2006&month=CY)
