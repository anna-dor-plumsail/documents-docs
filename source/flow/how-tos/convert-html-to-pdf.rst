Convert HTML to PDF
==================================

This article demonstrates how to convert DOCX Word document to PDF with the help of `Microsoft Flow <https://flow.microsoft.com>`_. 

Before starting, ensure that you `added Plumsail Documents connector to Microsoft Flow <../getting-started/use-from-flow.html>`_.

We will take a hiring contract as a sample Word document:

.. code-block:: html
   
  <table id="invoice-amount">
    <thead>
      <tr id="header_row">
        <th class="index_th">#</th>
        <th class="left details_th">Title</th>
        <th class="quantity_th">Quantity</th>
        <th class="unitprice_th">Unit Price ($)</th>
        <th class="subtotal_th">Subtotal ($)</th>
      </tr>
    </thead>
    <tfoot>
    <tr id="total_tr">
      <td colspan="2">&amp;nbsp;</td>
      <td colspan="2" class="total" id="total_currency"><span class="currency">$ </span> Total</td>
      <td class="total">${{Total}}</td>
    </tr>
    </tfoot>
    <tbody>
      {{#each Items}}
      {{#with FieldValues}}
      <tr class="item">
        <td class="item_l">{{#index}}</td>
        <td class="item_l">{{Title}} </td>
        <td class="item_r">{{Quantity}}</td>
        <td class="item_r">{{UnitPrice}}</td>
        <td class="item_r">{{SubTotal}}</td>
      </tr>
      {{/with}}
      {{/each}}
    </tbody>
  </table>

Our document has to be stored somewhere. Microsoft Flow has a lot of connectors for different systems. Here are just a few of them:

- SharePoint
- Salesforce
- Box
- OneDrive
- Google Drive
- Dropbox
- SFTP
- File System

You can store your source file anywhere. In this example, we will store our document in SharePoint. Our Flow will get a file from a SharePoint document library, convert it to PDF and store generated file back to SharePoint document library. 

This is how complete flow looks:

.. image:: ../../_static/img/flow/how-tos/convert-docx-to-pdf-flow.png
   :alt: Select fields

Here is step by step description for the flow.

**Flow trigger**

You can actually pick any trigger. For example, you can start conversion of file creation in a SharePoint document library. We use "Manually trigger a flow" trigger here to simplify the Flow.

**Get file content**

This action gets file content of specified file from a SharePoint document library. You just specify SharePoint site URL and path to your file.

You can use any other connector to get files from your system.

**Convert DOCX to PDF**

This is an action from Plumasail Documents connector, which is a part of `Plumsail Actions <https://plumsail.com/actions>`_.

Just put DOCX file content from the output of the previous action and receive PDF file content as an output of this action.

You can find more information about this action `here <../actions/document-processing.html#convert-docx-to-pdf>`_.

**Create PDF file**

Now you need to store PDF file somewhere. In our example, we use "Create file" action from SharePoint connector to store the PDF document into SharePoint document library.

.. image:: ../../_static/img/flow/how-tos/generated-pdf-sp-library.png
   :alt: Select fields

You can use any other connector to store PDF document into your system.

.. hint:: There is also `Create document from DOCX template <../actions/document-processing.html#create-document-from-docx-template>`_ action available. You can use it in conjunction with `Convert DOCX to PDF <../actions/document-processing.html#convert-docx-document-to-pdf>`_ action to `create PDF documents from a template <create-pdf-from-docx-template.html>`_.