
<p>This repository holds the configuration file needed to modify Tables for Somatic Alterations and Gene Expression. </p>

<br>
<h2>Guidelines to create configuration file:</h2> <br>

<p>
For every key in the JSON object, provide a detailed description by creating the following:

    [
      {  
        id: String,                           - required 
        label: String,                        - optional
        exportLabel: String,                  - optional 
        sortable: Boolean,                    - optional
        hidden: Boolean,                      - optional
        exportValue: String | Boolean,        - optional
        externalLink: {                       - optional
          url: String,                          - required
          linkText: String,                     - required
        },
        internalLink: {                       - optional
          url: String,                          - required
          linkText: String,                     - required
        },
        chopFieldName: String                 - optional
      },
      {...},
      ....
    ]
</p>
<h1>Overview:</h1>

Every Column object must be provided with the `id` property. The `id` must match with the fields defined from MTP GraphQl schema and will be used to extract the value. That value will be used for comparison, file exporting, sorting and cell rendering. Alternatively, the value used by those features can be overridden by the following properties:
    <ul>
      <li>String exported to a file by the downloader: `exportValue`.</li>
      <li>Link rendered in the table cell: `internalLink` & `externalLink`.</li>
    </ul>
If any of those fields are present, they will take priority over `id`.

<h1>Definition:</h1>

`id`: The ID name used to describe this column from FNL API.

`label`: Column display name that will appear in the table as the column header. If `label` is not present, a capitalized and spaced version of `id` will be used.

`exportLabel`: Column label shown on the exported file header. If not present, camelCase value from `id` field will be used.

`hidden`: If true, column will not be shown in the table. To hide column in the exported file refer to `exportValue`

`sortable`: If true, the table will allow selecting this column to sort the content rows.

`exportValue`: If present, the value will be used for exporting this column. Otherwise, it will use the data associated with column `id`. If set to false, the column will not be present in the export.

`externalLink`: If present, column will be a hyperlink to external link.<sup>`**`</sup>
 
`internalLink`: If present, column will be a hyperlink to internal link, ex. (Disease, Target, Drug, or Evidence) page.<sup>`**`</sup>

`chopFieldName`: The ID name used to describe this column from CHoP source file.

  <sup>`**`</sup> If `internalLink` or `externalLink` are present in a column, `url` and `linkText` are required to be provided. Following the format below, Link desination and text can be configurable <br> 
  &nbsp;&nbsp;&nbsp;&nbsp;`url`: Link's destination <br>
  &nbsp;&nbsp;&nbsp;&nbsp;`linkText`: Link text that will be visible to the reader.
  
 <b>(Note)</b> When inserting non static value, the `id` associated with the value need to be provided inside `${}`. An Example of creating PedcBio PedOT mutations plot URL:
  ```
    {
      "id": "pedcbioPedotMutationsPlotURL",
      ...
      "externalLink": {
        "url": "${pedcbioPedotMutationsPlotURL}",
        "linkText": "mutations"
      },
      ...
    }
  ```

<br><hr><br>

Example URLs to MTP pages: <br>
<ul>
  Target Page (page_target):
  <ul>
    <li> https://ppdc-otp-qa.bento-tools.org/target/ENSG00000171094 </li>
    <li> https://ppdc-otp-qa.bento-tools.org/target/ENSG00000097007 </li>
    <li> https://ppdc-otp-qa.bento-tools.org/target/ENSG00000157764 </li>
  </ul>

  <br>
  Evidence Page (page_evidence):
  <ul>
    <li> https://ppdc-otp-qa.bento-tools.org/evidence/ENSG00000171094/EFO_0000621 </li>
    <li> https://ppdc-otp-qa.bento-tools.org/evidence/ENSG00000171094/EFO_0000616 </li>
    <li> https://ppdc-otp-qa.bento-tools.org/evidence/ENSG00000157764/EFO_0000616 </li>
  </ul>
</ul>
