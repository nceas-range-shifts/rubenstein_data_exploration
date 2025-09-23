# Data exploration: Rubenstein et al. 2023

Exploration of the CoRE data underlying Rubenstein et al. (2023). Climate change and the global redistribution of biodiversity: Substantial variation in empirical support for expected range shifts. [Environmental Evidence, 12(1), 7](https://doi.org/10.1186/s13750-023-00296-0).

* CoRE (Contractions or Range Expansions) Database: Global Database of Species Range Shifts from 1802-2019: Data downloaded from https://www.sciencebase.gov/catalog/item/64147d6fd34eb496d1ceb497

Data are saved in .zip files, but extracted data is excluded in the `.gitignore` file. The .zip files should be unpacked in the `_raw_data` folder.  Notes:

* The original zip file, `Global Database of Species Range Shifts from 1802-2019.zip`, has been renamed to truncate and remove spaces: `db_range_shifts.zip`.
* Inside the zip file, another zip file contains shapefiles: `studyarea_shapefiles.zip`.  This has been added as a standalone .zip in the `_raw_data` directory at the same level as the original .zip.
* Extract the two zip files into corresponding directories with the same base name.

```
repo_root/
  |
  +-- _raw_data/
        +-- db_range_shifts.zip     ### EXTRACT
        +-- db_range_shifts/
        |     +-- Climate.Variables.csv
        |     +-- metadata.xml
        |     +-- PaperID.csv
        |     +-- Range.Shifts.csv
        |     +-- studyarea_shapefiles.zip  ### DO NOT EXTRACT
        |
        +-- studyarea_shapefiles.zip ### EXTRACT
        +-- studyarea_shapefiles/
              +-- studyarea.shapefiles.[cpg,dbf,prj,sbn,sbx,shp,shx]
```
    
Alternately, extract tables and then re-save to a SQL database using RSQLite.  This vastly reduces the size of the stored files (from 38 MB total to 2.2 MB).
