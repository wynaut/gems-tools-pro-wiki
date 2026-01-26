For advice on how to configure ArcMap, [please see the relevant page on the ArcMap toolbox's wiki](https://github.com/DOI-USGS/gems-tools-arcmap/wiki/ConfigureArcMap). Note that the ArcMap version of the GeMS tools is depreciated and will no longer be updated with any regularity.

### <a name="Snapping"></a>Snapping

We **highly** recommend that all users of GeMS familiarize themselves with ArcGIS Pro's [Snapping settings](https://pro.arcgis.com/en/pro-app/latest/help/editing/enable-snapping.htm).  Turning on snapping greatly aids in complying with the topology rules prescribed by GeMS.

Snapping can be turned on and customized in the lower left-hand corner of ArcGIS Pro.

[[WikiImages/bottomLeftSnapping.png]]

[[WikiImages/snappingSettings.png]]

[[WikiImages/snappingSettings2.png]]

### Adding GeMS_Tools to ArcGIS Pro

Open ArcGIS Pro. Open any project file and navigate to the **Catalog** window.

[[WikiImages/proCatalogWindow.png]]

Click the **Favorites** tab at the top of the Catalog window. 

[[WikiImages/proFavoritesTab.png]] 

Click **Add Item**, then **Toolbox**, then **Add Toolbox**.

[[WikiImages/proAddToolbox.png]]

In the Add Toolbox window that opens, navigate to wherever you saved the unzipped GeMS Tools package* and select the **GeMS_Tools** toolbox (.tbx) file.

[[WikiImages/proAddGeMS-Tools.png]]

Now the GeMS toolbox will be in your Favorites tab whenever you open Pro! Congratulations!
Remember to repeat this process with new releases of the toolbox.

*Note: Tool performance is CONSIDERABLY improved by storing the GeMS Tools on a local drive, as opposed to a network!

### FGDC Symbology

The GeMS schema does not require the use of any particular symbols.  But we encourage you to use the symbols defined in [FGDC Digital Cartographic Standard for Geologic Map Symbolization](https://ngmdb.usgs.gov/fgdc_gds/), FGDC-STD-013-2006.

These are implemented in the [.stylx file created by the South Carolina Geological Survey](https://ngmdb.usgs.gov/Info/standards/NCGMP09/docs/FGDC_STYLX.zip), which brings the standard into a form easily digestible by ArcGIS Pro.

The file heavily features contributions from the Alaska Division of Geological and Geophysical Surveys and the Geological Survey of Canada. We thank all who had a hand in its creation!

Note that use of the style requires the user to install the following fonts, which may or may not require administrator permissions:

- [FGDCGeoAge.otf](https://ngmdb.usgs.gov/Info/standards/GeMS/docs/FGDCGeoAge.otf) — OpenType version of special geologic age characters.
- [FGDCGeoSym](https://ngmdb.usgs.gov/Info/standards/GeMS/docs/FGDCGeoSym_fonts.zip) — five TrueType font files of geologic marker symbols used for decorating line symbols and symbolizing points.