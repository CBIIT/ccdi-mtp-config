
<p>This repository holds the configuration file needed to modify Tables for Somatic Mutation and TPM. <p>

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
        externalLink: Boolean,                - optional
        internalLink: Boolean,                - optional
        chopFieldName: String                 - optional
      },
      {...}
      ....
    ]

  <b>id</b>: The ID name used to describe this column from FNL API.

  <b>label</b>: Column display name that will appear in the table as the column header. If label is not present, a capitalized and spaced version of id will be used.

  <b>exportLabel</b>: Column label shown on the exported file header. If not present, camelCase value from id field will be used. Camel case will also be applied to exportLabel value.

  <b>hidden</b>: If true, column will not be shown in the table. Downloaded data will still include columns that are hidden.

  <b>sortable</b>: If true, the table will allow selecting this column to sort the content rows.

  <b>externalLink</b>: If true, column will be a hyperlink to external link. 

  <b>internalLink</b>: If true, column will be a hyperlink to internal link, ex. (Disease, Target, Drug, or Evidence) page. 

  <b>chopFieldName</b>: The ID name used to describe this column from CHoP source file.
</p>

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