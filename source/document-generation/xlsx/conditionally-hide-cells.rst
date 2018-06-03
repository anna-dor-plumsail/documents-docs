Conditionally hide cells in XLSX templates
===========================================

You can use `collapse formatter <../common-docx-xlsx/formatters.html#collapse>`_ to hide cells of an Excel document if some value or collection of values is null or empty.

The formatter checks if a value for current tag is empty, then finds clears content of cells.

There are two cases how you can use it:

.. contents:: Two cases when you can use it:
    :local:
    :depth: 1

Clear content of a single cell
------------------------------

Clear content of a named range
------------------------------

.. include:: named-ranges.rst

- Table row
- Bullet list item

First of all, review the `demo for this case <./demos.html#conditionally-hide-blocks>`_. 

Here we will learn how it works: