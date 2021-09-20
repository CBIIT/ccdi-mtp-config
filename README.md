
<p>This repository holds the configuration file needed to modify Tables for Somatic Mutation and TPM. <p>

<br>
<h2>Guidelines to create configuration file:</h2> <br>

<p>
For every key in the JSON object, provide a detailed description by creating the following:

    [
      {  
        id: String,                           - required 
        label: String,                        - optional 
        sortable: Boolean,                    - optional
        hidden: Boolean,                      - optional
        externalLink: Boolean,                - optional
        internalLink: Boolean                 - optional
      },
      {...}
      ....
    ]

  <b>id</b>: JSON object key name.

  <b>label</b>: Column display name that will appear in the table as the column header. If label is not present, a capitalized and spaced version of id will be used.

  <b>hidden</b>: If true, column will not be shown in the table. Downloaded data will still include columns that are hidden.

  <b>sortable</b>: If true, the table will allow selecting this column to sort the content rows.

  <b>externalLink</b>: If true, column will be a hyperlink to external link. 

  <b>internalLink</b>: If true, column will be a hyperlink to internal link, ex. (Disease, Target, Drug, or Evidence) page. 
</p>