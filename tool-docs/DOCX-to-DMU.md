### DOCX to DMU

*[GeMS_DocxToDMU.py](https://github.com/DOI-USGS/gems-tools-pro/blob/master/Scripts/GeMS_DMUtoDocx.py)*

Reads contents of a Description Of Map Units Microsoft Word document formatted according to USGS Pubs template MapManuscript_v3-1_06-22.dotx, calculates HierarchyKey, and partially fills in a GeMS-style DescriptionOfMapUnits table. If the workspace does not have a DescriptionOfMapUnits table, one will be created. HierarchyKey values are calculated based on paragraph styling and indentation. If a table already exists, the tool will attempt to match updates with existing rows.

DMU paragraphs in the manuscript must be formatted with 'DMU' styles, for example:

* ```DMU-HeadingN``` (number, N, may up to 5)
* ```DMU Headnote - 1 line```
* ```DMU Headnote - More Than 1 line```
* ```DMU Headnote Paragraph```
* ```DMU Unit 1 (1st after heading)```
* ```DMU Unit N``` (number, N, may be up to 5)

The paragraph content will be parsed into the table in the following ways:

* Heading text will be saved in Name.
* Headnote text will be saved in Description, with or without formatting tags as desired. See below and checkbox help.
* The unit label will be saved in MapUnit and, optionally, in Label with formatting tags. See below and checkbox help.
* The unit name will be saved in Name.
* The unit age will be saved in Age.
* The unit description will be saved in Description, with or without formatting tags as desired. See below and checkbox help.

Note that not all styles in 'DMU_template.docx' in the Resources folder of this toolbox are recognized by this tool, in particular, paragraph styles such as `DMU NoIndent`, `DMU Quotation`, and `DMU - List Bullet` are ignored.

Regarding text formatting tags, ArcGIS Pro recognizes two flavors of tags depending on where the text is intended to be displayed. For labelling and annotation, [ArcGIS text formatting tags ](https://pro.arcgis.com/en/pro-app/latest/help/mapping/text/text-formatting-tags.htm)are recognized while HTML tags are used in pop-ups. The tool assumes that all text in Description would only be viewed in pop-ups whereas the text in Label will likely be used for labeling but might also appear in pop-ups. For Description there is only the choice to have character styling converted to HTML tags while both options exist for Label text. Only a small set of either [ArcGIS Text Formatting Tags](https://pro.arcgis.com/en/pro-app/latest/help/mapping/text/text-formatting-tags.htm) or HTML tags are written by the tool:

* ArcGIS only: `<fnt>`, `<bol>`, `<ita>` , `'size'` , `'italic'` , `'style'` and `'wght'` attributes in `<fnt>`
* HTML only: `<span>`, `<strong>`, `<em>`, `'font-weight'` and `'font-style'` attributes in `<span>`
* Both ArcGIS and HTML: `<sup>`, `<sub>`


| **Parameter**            | **Explanation**                                              | **Data Type** |
| ------------------------ | ------------------------------------------------------------ | ------------- |
| DMU manuscript file      | Path to the Word document. | File |
| Geologic map geodatabase | GeMS-style database. DescriptionOfMapUnitst table DMU table may be empty, partly complete or not exist at run time. | Workspace |
| Length of HierarchyKey segments | All segments less than this number will be padded to the left with zeros. It is best practice to always pad to at least 3 spaces (the default) to try to avoid the value ever being interpreted as a date datatype. | Integer |
| Add ArcGIS tags to Label (for annotation) | Convert character styling of the unit label in the Word doc into ArcGIS text formatting tags and saved in Label. | Boolean |
| Add HTML tags to Label (for pop-ups) | Convert character styling of the unit label in the Word doc into HTML formatting tags and saved in Label. | Boolean |
| Add HTML tags to Description (for pop-ups) | Convert character styling of the unit description in the Word doc into HTML formatting tags and saved in Description. | Boolean |

#####  Significant dependencies 

* docx (https://python-docx.readthedocs.io/en/latest/) included with toolbox in folder `Scripts\docx`