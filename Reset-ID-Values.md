### (re)Set ID Values

*[GeMS_reID.py](https://github.com/DOI-USGS/gems-tools-pro/blob/master/Scripts/GeMS_reID.py)*

GeMS-style databases use _ID values as primary keys; these values are repeated as ID values in other tables where they serve as foreign keys to tie tables together. **(re)Set ID values** generates _ID values while preserving any links established by existing _ID and ID values. As an option, GUIDs may be substituted for plain-text _ID and ID values.

This script modifies the input geodatabase. Make a backup copy (with **Compact and Backup**) before you run it! 

| **Parameter**                | **Explanation**                                              | **Data Type** |
| ---------------------------- | ------------------------------------------------------------ | ------------- |
| Input_GeMS-style_geodatabase | The geodatabase for which _ID values are to be created or recreated. Must exist. May be file geodatabase (.gdb) or personal geodatabase (.mdb). | Workspace     |
| Use_GUIDs (Optional)         | Default is unchecked (false),which creates _ID values as several characters which denote the table (e.g., MUP for MapUnitPolys) followed by consecutive zero-padded integers: MUP0001, MUP0002, MUP0003, etc. If checked, creates GUIDs (Globally-Unique IDs which are many-byte nonsense strings) for _ID values. | Boolean       |
| Do_not_reset_DataSource_IDs  | If unchecked, resets values of DataSources_ID and all DataSourcesID, LocationSourceID, AnalysisSourceID and similar that refer to DataSources_ID. Default is checked, which leaves these values unchanged. | Boolean       |