Conditionally hide cells in XLSX templates
===========================================

You can use `collapse formatter <formatters.html#collapse>`_ to hide cells of an Excel document if some value or collection of values is null or empty.

The formatter checks if a value for current tag is empty, then finds clears content of cells.

There are two cases how you can use it:

- Clear content of a single cells
- Clear content of a named range

.. include:: named-ranges.rst

- Table row
- Bullet list item

First of all, review the `demo for this case <./demos.html#conditionally-hide-blocks>`_. 

Here we will learn how it works:

.. contents::
    :local:
    :depth: 1    

.. _hide-table-rows:

Hide table rows
---------------

Let us assume we have a collection of employees. We want to render a table with information about them, but we want to hide employees without employment date (:code:`hideDate`).

This is JSON representation of employees data:

.. code:: json

    {           
        "employees": [
            {
                "name": "Derek Clark",
                "hireDate": "2012-04-21T18:25:43-05:00"
            },
            {
                "name": "Jessica Adams",
                "hireDate": null
            },
            {
                "name": "Anil Mittal",
                "hireDate": "2016-04-11T14:22:13-02:00"         
            }
        ]
    }

We will use the template like this:

.. image:: ../../_static/img/document-generation/hide-table-row-template.png
    :alt: hide table row template

As you can see, we added this string to the template row: :code:`{{employees.hireDate}:collapse:hide}`. The :code:`collapse` formatter checks if hire date is empty and hides table row that contains this tag. The :code:`hide` formatter hides the value of the tag if it is not empty.

The result table will look like this:

.. image:: ../../_static/img/document-generation/hide-table-row-result.png
    :alt: hide table row result

The employee with the name "Jessica Adams" was hidden because of empty hire date.


Hide bullet list items
----------------------

We will use the same JSON data as in the example for table rows above.

Our template will look like this:

.. image:: ../../_static/img/document-generation/hide-bullet-list-item-template.png
    :alt: hide bullet list template

As you can see, we added this string to the bullet list item template: :code:`{{employees.hireDate}:collapse:hide}`. The :code:`collapse` formatter works the same way as in `the example for table rows <#hide-table-rows>`_ above.

The result table will look like this:

.. image:: ../../_static/img/document-generation/hide-bullet-list-item-result.png
    :alt: hide bullet list result

Hide arbitrary block
--------------------

If you want to hide arbitrary section that is not a table row or a bullet list item, we recommend you to wrap it into a table cell with invisible borders.

In this example, we will use information about a company as a source data for the template.

This is JSON representation of company data:

.. code:: json

    {       
        "companyName": "Plumsail",    
        "site": "http://plumsail.com",
        "contacts": null    
    }

We want to display company name, site and contacts and hide contacts if they are empty. We will just wrap all text related to contacts into a table cell with transparent borders:

.. image:: ../../_static/img/document-generation/hide-arbitrary-block-template.png
    :alt: hide arbitrary block template

As you can see, we added this string to the template for contact information: :code:`{{contacts}:collapse:hide}`. The :code:`collapse` formatter works the same way as in `the example for table rows <#hide-table-rows>`_ above.

The result will look like this:

.. image:: ../../_static/img/document-generation/hide-arbitrary-block-result.png
    :alt: hide arbitrary block result