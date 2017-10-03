Documents connector
==================================

This connector helps you to automatically generate and convert documents. Before starting, ensure that you `added Plumsail Documents connector to Microsoft Flow <../getting-started/use-from-flow.html>`_.

Create document from DOCX template
----------------------------------

Creates .docx document from .docx template. You can find more examples in `this article <../how-tos/create-docx-from-template.html>`_.

Output Parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  File Content
       -  The content of the result .docx file.
       -  It is a Base64 encoded content of the result file.

Input Parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  DOCX document content
       -  The raw content of the source .docx template file. You can extract file content from other connectors like:

          - SharePoint
          - Salesforce
          - Box
          - OneDrive
          - Google Drive
          - Dropbox
          - SFTP
          - File System

          `List of Microsoft Flow connectors <https://flow.microsoft.com/en-us/connectors/>`_

       -  You can find insturctions about creation of a template file in `this article <../../advanced/create-docx-template.html>`_. 
       
          Use `this link <../../_static/files/flow/how-tos/Hiring%20Contract%20Template.docx>`_ to download the sample template.

    *  -  Template data
       -  Data to bind to the template in JSON format. You can get this data from some other Microsoft Flow connector. For example you can query SharePoint list or some other system.
       -  .. code-block:: json

            {
                "EmployerFullName": "David Navarro",
                "EmployeeFullName": "Anil Mittal",
                "CompanyName": "Contoso LLC",
                "Position": "Marketing manager",
                "SalaryAmount": 5000,
                "ListOfBenefits": "list of any benefits that come with employment",
                "BonusesPolicyDescription": "annual evaluation",
                "EffectiveDate": "10/27/2017",
                "TerminationDate": "10/27/2018",
                "State": "New York"
            }    

Example
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. image:: ../../_static/img/flow/how-tos/create-document-from-docx-template-example.png
   :alt: Create document from DOCX template Example

Create HTML from template
----------------------------------

Generates raw HTML from a raw HTML template. You can find more examples in `this article <../how-tos/create-html-from-template.html>`_.

Output Parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Result HTML
       -  Raw HTML result created from a source HTML template.
       -  .. code-block:: html

            <!doctype html>
            <html>
            <head>
                <meta charset="utf-8">
                <title>HTML from template</title>  
            </head>
            <body>
                <ul>                            
                    <li>David Navarro </li>                    
                    <li>Jessica Adams</li>                    
                    <li>Derek Clark</li>                    
                </ul>    
            </body>
            </html>                    

Input Parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Source HTML
       -  HTML content of a source template. You can specify raw HTML here or extract file content from other connectors like:

          - SharePoint
          - Salesforce
          - Box
          - OneDrive
          - Google Drive
          - Dropbox
          - SFTP
          - File System          

          `List of Microsoft Flow connectors <https://flow.microsoft.com/en-us/connectors/>`_

          This parameter can handle both raw HTML of file content from other connector.

       -  You can find description of template syntax in `this article <../../advanced/html-template-syntax.html>`_. 
       
          .. code-block:: html

            <!doctype html>
            <html>
            <head>
                <meta charset="utf-8">
                <title>HTML from template</title>  
            </head>
            <body>
                <ul>        
                    {{#each data}}
                    <li>{{name}}</li>
                    {{/each}}
                </ul>    
            </body>
            </html>

    *  -  Template data
       -  Data to bind to the template in JSON format. You can get this data from some other Microsoft Flow connector. For example you can query SharePoint list or some other system.
       -  .. code-block:: json

            {
                "data": [
                    {
                        "name": "David Navarro "
                    },
                    {
                        "name": "Jessica Adams"
                    },
                    {
                        "name": "Derek Clark"
                    }
                ]
            }  

Example
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. image:: ../../_static/img/flow/how-tos/html-from-template-raw.png
   :alt: Convert HTML document to PDF Example

Convert DOCX to PDF
----------------------------

Converts .docx document to PDF document. You can find more examples in `this article <../how-tos/convert-word-to-pdf.html>`_.

Output Parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  File Content
       -  The content of the result PDF file.
       -  It is a Base64 encoded content of the result file.

Input Parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Document content
       -  The raw content of the source .docx file. You can extract file content from other connectors like:

          - SharePoint
          - Salesforce
          - Box
          - OneDrive
          - Google Drive
          - Dropbox
          - SFTP
          - File System

          `List of Microsoft Flow connectors <https://flow.microsoft.com/en-us/connectors/>`_

       -  It is a Base64 encoded content of the source template file.          

Example
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. image:: ../../_static/img/flow/how-tos/convert-docx-to-pdf-example.png
   :alt: Convert DOCX document to PDF Example

Convert HTML to PDF
----------------------------

Converts HTML document to PDF document. You can find more examples in `this article <../how-tos/convert-html-to-pdf.html>`_.

Output Parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  File Content
       -  The content of the result PDF file.
       -  It is a Base64 encoded content of the result file.

Input Parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Source HTML
       -  HTML content of a source file. You can specify raw HTML here or extract file content from other connectors like:

          - SharePoint
          - Salesforce
          - Box
          - OneDrive
          - Google Drive
          - Dropbox
          - SFTP
          - File System          

          `List of Microsoft Flow connectors <https://flow.microsoft.com/en-us/connectors/>`_

          This parameter can handle both raw HTML and file content as an output from other action.

       -  .. code-block:: html

            <!doctype html>
            <html>

            <head>
                <meta charset="utf-8">
                <title>HTML to PDF example
                <style>
                    div {
                        border: 1px solid lightgray;
                        padding: 5px;
                        float: left;            
                    }
                </style>
            </head>
            <body>
                <div>
                    Text in box1
                </div>
                <div>
                    Text in box2
                </div>    
            </body>
            </html>

    *  -  Papper Size
       -  Paper size for output PDF file.
       -  

          - A4
          - Letter
          - LetterSmall
          - Tabloid
          - Ledger
          - Legal
          - Statement
          - Executive
          - A2
          - A3
          - A4Small
          - A5
          - B4
          - B5

    *  -  Orientation
       -  Page orientation for output PDF file.
       -  

          - Portrait
          - Landscape          

Example
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. image:: ../../_static/img/flow/how-tos/convert-html-to-pdf-example.png
   :alt: Convert HTML document to PDF Example