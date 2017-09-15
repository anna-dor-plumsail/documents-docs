Create text document from template
==================================

This article demonstrates how to generate text document from template with the help of `Microsoft Flow <https://flow.microsoft.com>`_.

Before starting, ensure that you `added Plumsail Documents connector to Microsoft Flow <../getting-started/use-from-flow.html>`_.

We will generate simple text file with the list based on some data. This is how our final file looks:

.. image:: ../../_static/img/flow/how-tos/result-text-file.png
   :alt: Result text file

Our resulting document has to be stored somewhere. Microsoft Flow has a lot of connectors for different systems. Here are just a few of them:

- SharePoint
- Salesforce
- Box
- OneDrive
- Google Drive
- Dropbox
- SFTP
- File System

You can store your file anywhere. In this example, we will store our document in SharePoint. Our flow will use JSON object as a source data for the template, but you can get data from other sources, for example query list items from SharePoint or from Salesforce.


This is how our flow looks: 

.. image:: ../../_static/img/flow/how-tos/flow-text-file-from-template.png
   :alt: Result text file
