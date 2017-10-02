DOCX template creation
======================

This article demonstrates how to create .docx Word template. This template can be used document generation actions. For example, in the `Create document from DOCX template <../actions/document-processing.html#convert-html-document-to-pdf>`_ action.

In this example we will prepare a template for hiring contract. We need to insert special placeholders into our word document. They will be replaced by text in the future. To do this, open Microsoft Word, click in the text where you want to add placeholder, navigate to *'Insert'* tab and select *'Quick Parts'*. Then select *'Field'*.

.. image:: ../../_static/img/flow/how-tos/Create-document-from-docx-template-sample-quick-parts.png
   :alt: Select fields

Select *'MergeField'* from the list of categories and fill in *'Field name'*:

.. image:: ../../_static/img/flow/how-tos/Create-document-from-docx-template-sample-merge-field.png
   :alt: Pick merge field

.. note:: *'Field Name'* has to correspond to a name of a property in the data object, that you want to apply to this template. For example, you may have an object with property *'EmployerFullName'*. Use the same name for merge field.

After adding all required placeholders, the document should look like this:

.. image:: ../../_static/img/flow/how-tos/hiring-contract-docx-template.png
   :alt: Sample document

Use `this link <../../_static/files/flow/how-tos/Hiring%20Contract%20Template.docx>`_ to download it.