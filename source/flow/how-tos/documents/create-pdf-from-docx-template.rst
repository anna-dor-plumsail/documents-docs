Create PDF from DOCX template
==================================

This article demonstrates how to generate PDF document from a DOCX template with the help of `Microsoft Flow <https://flow.microsoft.com>`_. 

Before starting, ensure that you `added Plumsail Documents connector to Microsoft Flow <../../../getting-started/use-from-flow.html>`_.

We will firstly generate DOCX document from a template. Then we will convert it to PDF. In this article, we will generate PDF invoice based on some data. This is how our final PDF file looks:

.. image:: ../../../_static/img/flow/how-tos/docx-sample-doc.png
   :alt: PDF sample document

Our template and result document have to be stored somewhere. Microsoft Flow has a lot of connectors for different systems. Here are just a few of them:

- SharePoint
- Salesforce
- Box
- OneDrive
- Google Drive
- Dropbox
- SFTP
- File System

You can store your source file anywhere. In this example, we will store our documents in SharePoint. Our Flow will get a template from a SharePoint document library, generate a new document based on this template and on some data. The resulting document will be stored back to SharePoint document library.

Firstly, we have to prepare the template file. Please follow `this instruction to prepare your template <../../../advanced/create-docx-template.html>`_.

Now we need to create a Microsoft Flow that will get the template from the SharePoint document library, apply data to this template, convert a document to PDF and save it back to the document library. This is how complete flow looks:

.. image:: ../../../_static/img/flow/how-tos/flow-create-pdf-from-docx-template.png
   :alt: Flow create PDF from DOCX template

Here is the step by step description for the flow.

**Flow trigger**

You can actually pick any trigger. For example, you can start Flow on file creation in a SharePoint document library. We use "Manually trigger a flow" trigger here to simplify the Flow.

**Get file content**

This action gets file content of the specified file from a SharePoint document library. You just specify SharePoint site URL and path to your file. We use this action to read .docx template.

You can use any other connector to get files from your system.

**Create document from DOCX template**

This is an action from Plumasail Documents connector, which is a part of `Plumsail Actions <https://plumsail.com/actions>`_.

There are two parameters:

1. DOCX document content
2. Template data

In the first parameter *'DOCX document content'* we specified file content of a template from the output of the previous action. Use `this link <../../../_static/files/flow/how-tos/Hiring%20Contract%20Template.docx>`_ to download it.

In the second parameter, we specified data to apply to the template in JSON format. This is information about a sample employee. You can actually request this information from an external system with the help of another Microsoft Flow action.

This is our sample data:

.. code:: JSON

    {
        "EmployerFullName": "David Navarro",
        "EmployeeFullName": "Anil Mittal",
        "CompanyName": "Contoso LLC",
        "Position": "Marketing manager",
        "SalaryAmount": "5000",
        "ListOfBenefits": "list of any benefits that come with employment, including healthcare, retirement, gym membership, etc",
        "BonusesPolicyDescription": "annual evaluation",
        "EffectiveDate": "10/27/2017",
        "TerminationDate": "10/27/2018",
        "State": "New York"
    }

You can find more information about this action `here <../../actions/document-processing.html#create-document-from-docx-template>`_.

**Convert DOCX to PDF**

This is also an action from Plumasail Documents connector.

Just put DOCX file content from the output of the previous action and receive PDF file content as an output of this action.

You can find more information about this action `here <../../actions/document-processing.html#convert-docx-document-to-pdf>`_.

**Create file**

Once the result document is generated, we need to store the Word file somewhere. In our example, we use "Create file" action from SharePoint connector to store the document in SharePoint document library.

.. image:: ../../../_static/img/flow/how-tos/generated-pdf-from-docx-template-sp-library.png
   :alt: Select fields

You can use any other connector to store the Word document into your system.

.. hint:: There is also `Convert HTML document to PDF <../../actions/document-processing.html#create-html-from-template>`_ action available. You can use it in conjunction with `Convert HTML to PDF <../../actions/document-processing.html#convert-html-to-pdf>`_ action to `create PDF documents from an HTML template <create-pdf-from-html-template.html>`_.