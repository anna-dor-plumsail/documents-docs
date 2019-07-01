How to create a document from a template in Microsoft Flow and sign it using AdobeSign
####################################################################
Nowadays many companies, regardless of their size, face a significant shift: more and more of their activities happen online. Whole businesses go online, teams raise their efficiency by changing their offline routines and communication into online ones. No wonder that document flow falls in line with the same trend. And using an electronic document flow system and e-signs is a common case.

You can make your operational life even easier and faster by integrating the workflow and electronic document flow system with the help of `Microsoft Flow`_. 

Moreover, we’ve prepared a ready-to-use solution on how to create a document (e.g. a contract) from a template and sign it using `AdobeSign`_. 

With the help of `Plumsail Documents`_, we will create a purchase agreement from a template, convert to needed extension, save in SharePoint document library and send for signing using `AdobeSign connector`_ for Microsoft Flow. 

This is how the result document will look after signing:

|signed_contract|

And also have a look at how the completed flow will appear:

|adobe_sign_flow|

Here is a step-by-step description.

**Flow trigger**

After you’ve opened `My Flows`_, create a new one and select a trigger. Actually, you can pick any, for example, trigger a Flow when an opportunity in CRM is closed, or others. We will pick *'Manually trigger a Flow'* just for demonstration purposes.

**Get file content**

Assign this action for a storage system connector. In this example, we store our documents in a SharePoint library. However, Microsoft Flow has many connectors for different systems. Here are just a few of them:

- SharePoint
- Box
- OneDrive
- Google OneDrive
- Dropbox
- SFTP
- File system

*'Get file content'* action takes the content of the specified files from a document library. We need to specify the SharePoint site URL and path to our contract template. 

|get_content|

**Create DOCX from template**

This is the action from `Plumsail Documents connector`_ for creating DOCX files from a template. You can find more information about this action by visiting `this page`_. 

If you use it for the first time, you’ll be asked for *'Connection Name'* and *'Access Key'*. You can type any name for the connection. For example, *'Plumsail Documents'*.

Then `create an API key in your Plumsail Account page`_, copy and paste it to the *'Access Key'* field.

'Create DOCX from template' action has two parameters:

1.	Document content.

2.	Template data.

|create_docx|

*'Document content'* is just an output of our previous step. 

`Download`_ the purchase agreement template we are using in our Flow. You will see that all the variables are put between :code:`{{ }}` brackets. These fields will be automatically filled after we specify Template data.

You can create your own templates using this approach, it’ very simple, see detailed information about the template engine `here`_. 

To specify Template data, we use the JSON object as a source:

.. code:: json

    {
        "Number": "432",
        "Execution.date":"2020-05-25",
        "delivery.date":"2020-05-30",
        "buyer.name":"LUCKY LLC",
        "buyer.address":"3 Main St.New York NY 97203 USA",
        "company": {
           "email": "sales@sample.com",
            "address": "3 Main St.New York NY 97203 USA",
             "phone": "202-555-0131",
             "name": "Plumsail LLC"
         },
        "items": [
            {
               "product": {
                   "name": "Monitor",
                    "price": 99
               },
               "quantity": 10,
               "cost": 990
             },
             {
                "product": {
                    "name": "Fridge",
                     "price": 4219.99
                 },
               "quantity": 1,
               "cost": 4219.99
             }
          ],
         "total": 5209.99
    }

With Plumsail Documents, you can generate documents in different formats from a template:

- `DOCX`_
- `XLXS`_
- `HTML`_ 
- `TXT`_ 

**Convert DOCX to PDF**

This is also the action available in Plumsail Documents connector for Microsoft Flow. With its help, we convert our DOCX file to PDF for further use in AdobeSign. To fill in the only field, select :code:`Result file` from the 'Create DOCX from template' step in Dynamic content.

|convert_to_pdf|

By the way, Plumsail Documents can convert other formats. For example:

- `Older MS office formats into new ones`_;
- `HTML to PDF`_;
- `Email message to PDF`_.

**Create file**

Use this action to store the completed agreement. Specify a SharePoint site URL, a library, the name of the document with :code:`.PDF` extension, and for *File content* choose :code:`Result file` – an output from the previous step of converting DOCX to PDF.

|create_file|

**Create sharing link for a file or folder**

We will need to share our contract with AdobeSign, that’s why a sharing link is needed. Pay attention to choose the right link type and scope – they should be *'View and edit'* and *'Anyone with the link, including anonymous'* respectively. 

|sharing_link|

There is a tricky moment for SharePoint site collection – you may be not allowed to share files from libraries of your SP site. In the case of such a setting, the Flow will fail on this step. We need to change the settings.

For that, go to SharePoint Admin Center, navigate to Active sites, choose yours and click on the button *'Sharing'* to edit the settings. 

|active_sites|

For our purpose, the site content can be shared with anyone.

|anyone|

You may be worried about sensitive information while sharing files, but there is no reason for it; nobody can use the link, but the AdobeSign application for getting content to create an agreement for further usage in AdobeSign. 

Moreover, there is another action in AdobeSign connector for Microsoft Flow to upload documents directly, but unfortunately, it doesn’t work now because of a lack of code integration. We believe that it will be fixed in the future.

**Create an agreement from a document URL, and send for signature**

This action creates an agreement, saves it in the AbobeSign account and sends it to your partner for signature. 

You can put any name for *'Agreement name'*. 

For Document URL field select an output from the previous step, and add :code:`?download=1` to make the link direct. Otherwise, it won’t work.

Don’t forget to specify a file extension with :code:`.PDF`

|adobesign_action|

The flow is ready. Now you know how to simplify your workflow processes using Microsoft Flow. `See here`_ some other cases how Plumsail Documents can be helpful for you. And if you are new to it, feel free to `sign up for an account`_ and get a 30-Day free trial. 





.. |signed_contract| image:: /_static/img/flow/how-tos/signed_contract.png
.. |adobe_sign_flow| image:: /_static/img/flow/how-tos/adobe_sign_flow.png
.. |get_content| image:: /_static/img/flow/how-tos/get_content_as.png
.. |create_docx| image:: /_static/img/flow/how-tos/docx_from_template_as.png
.. |convert_to_pdf| image:: /_static/img/flow/how-tos/convert_to_pdf_as.png
.. |create_file| image:: /_static/img/flow/how-tos/create_file_as.png
.. |sharing_link| image:: /_static/img/flow/how-tos/create_share_link.png
.. |active_sites| image:: /_static/img/flow/how-tos/sharing_button.png
.. |anyone| image:: /_static/img/flow/how-tos/anyone_can_edit.png
.. |adobesign_action| image:: /_static/img/flow/how-tos/adobe_sign_action.png





.. _Microsoft Flow: https://flow.microsoft.com/en-us/
.. _AdobeSign: https://acrobat.adobe.com/us/en/sign.html
.. _Plumsail Documents: https://plumsail.com/documents/
.. _AdobeSign connector: https://docs.microsoft.com/en-us/connectors/adobesign/
.. _My Flows: https://emea.flow.microsoft.com/manage/flows
.. _this page: https://plumsail.com/docs/documents/v1.x/flow/actions/document-processing.html#create-docx-document-from-template
.. _Plumsail Documents connector: https://plumsail.com/actions/documents/
.. _create an API key in your Plumsail Account page: https://plumsail.com/docs/documents/v1.x/getting-started/sign-up.html
.. _Download: https://plumsailonline.sharepoint.com/:w:/s/Anjelika/EWJQZezSnjNJtrX5CkhDZ4oB6yHZ3bsxZfcO3nbYzwqleA?e=0eD1iR
.. _here: https://plumsail.com/docs/documents/v1.x/document-generation/docx/how-it-works.html
.. _DOCX: https://plumsail.com/docs/documents/v1.x/flow/how-tos/documents/create-docx-from-template.html
.. _XLXS: https://plumsail.com/docs/documents/v1.x/flow/how-tos/documents/create-xlsx-from-template.html
.. _HTML: https://plumsail.com/docs/documents/v1.x/flow/how-tos/documents/create-html-from-template.html
.. _TXT: https://plumsail.com/docs/documents/v1.x/flow/how-tos/documents/create-text-from-template.html
.. _Older MS office formats into new ones: https://plumsail.com/docs/documents/v1.x/flow/how-tos/documents/convert-doc-to-docx-xls-to-xlsx-ppt-to-pptx.html
.. _HTML to PDF: https://plumsail.com/docs/documents/v1.x/flow/how-tos/documents/convert-html-to-pdf.html
.. _Email message to PDF: https://plumsail.com/docs/documents/v1.x/flow/how-tos/documents/convert-email-to-pdf.html
.. _sign up for an account: https://account.plumsail.com/
.. _See here: https://plumsail.com/docs/documents/v1.x/flow/how-tos/documents/index.html

