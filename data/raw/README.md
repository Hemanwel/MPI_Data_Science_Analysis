# Raw data

The raw survey and boundary files are intentionally not included in this repository. Add only data that you are authorized to use and publish.

## Expected files

### Main MPI notebook

Place the authorized household/individual source workbook here:

```text
data/raw/nig21_National_office submit1.xlsx
```

For the geographic section, place the authorized LGA boundary shapefile and its accompanying files under:

```text
data/raw/New_Shape_File/
```

The notebook expects the shapefile:

```text
nga_admbnda_adm2_osgof_20170222.shp
```

### Gender analysis

Place the authorized gender-analysis workbook here:

```text
data/raw/Gender_MPI.xlsx
```

If these filenames differ, update the input-path variables at the beginning of the relevant notebook.
