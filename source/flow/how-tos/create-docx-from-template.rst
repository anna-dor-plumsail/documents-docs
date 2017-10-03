Create DOCX from template
==================================

This article demonstrates how to generate DOCX Word document from a DOCX template with the help of `Microsoft Flow <https://flow.microsoft.com>`_. 

Before starting, ensure that you `added Plumsail Documents connector to Microsoft Flow <../getting-started/use-from-flow.html>`_.

We will generate a hiring contract from a template. Our template and result document has to be stored somewhere. Microsoft Flow has a lot of connectors for different systems. Here are just a few of them:

- SharePoint
- Salesforce
- Box
- OneDrive
- Google Drive
- Dropbox
- SFTP
- File System

You can store your source file anywhere. In this example, we will store our documents in SharePoint. Our Flow will get a template from a SharePoint document library, generate a new document based on this template and on some data. The result document will be stored back to SharePoint document library.

Firstly, we have to prepare the template file. Pleas follow `this instruction to prepare your template <../../advanced/create-docx-template.html>`_.

Now we need to create a Microsoft Flow that will get the template from the SharePoint document library, apply data to this template and save result document back to the document library. This is how complete flow looks:

.. image:: ../../_static/img/flow/how-tos/flow-create-docx-from-template.png
   :alt: Select fields

Here is the step by step description for the flow.

**Flow trigger**

You can actually pick any trigger. For example, you can start Flow on file creation in a SharePoint document library. We use "Manually trigger a flow" trigger here to simplify the Flow.

**Get file content**

This action gets file content of specified file from a SharePoint document library. You just specify SharePoint site URL and path to your file. We use this action to read .docx template.

You can use any other connector to get files from your system.

**Create document from DOCX template**

This is an action from Plumasail Documents connector, which is a part of `Plumsail Actions <https://plumsail.com/actions>`_.

There are two parameters. In the first parameter *'DOCX document content'* we specified file content of a template from the output of the previous action. In the second parameter we specified data to apply to the template in JSON format. This is information about a sample employee. You can actually request this information from external system with the help of another Microsoft Flow action.

You can find more information about this action `here <../actions/document-processing.html#create-document-from-docx-template>`_.

**Create file**

Once the result document is generated, we need to store the Word file somewhere. In our example, we use "Create file" action from SharePoint connector to store the document into SharePoint document library.

.. image:: ../../_static/img/flow/how-tos/generated-docx-from-template-sp-library.png
   :alt: Select fields

You can use any other connector to store the Word document into your system.

.. hint:: There is also `Convert DOCX document to PDF <../actions/document-processing.html#convert-docx-document-to-pdf>`_ action available. You can use it in conjunction with `Create document from DOCX template <../actions/document-processing.html#create-document-from-docx-template>`_ action to `create PDF documents from a template <create-pdf-from-docx-template.html>`_.