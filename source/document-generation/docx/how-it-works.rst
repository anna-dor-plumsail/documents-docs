How Word DOCX templates work
=======================

Plumsail Word DOCX templates use different approach than most other templating solutions. It uses minimal amount of syntax to make your work done. Let us start from basics and move to more advanced scenarios.

Templating syntax described here can be used in `Create DOCX document from template <link here>`_ action for Microsoft Flow or in `REST API <../../getting-started/use-as-rest-api.html>`_.

Basic syntax
------------

Let us assume we have some simple data object that we want to apply to our template.

JSON representation of the object:

.. code:: json

    {
        name: "Mark Nigma"
    }

And we want to include name in the generated document. We need to surround property with braces. The template on the left side, the result is on the right side:

.. image:: ../../_static/img/document-generation/simple-document-template-result.png
   :alt: Simple document template

Simple bullet list and table
----------------------------

You don't need to declare any loops, the templating engine is smart enough to understand structure of source object applied to your document. Thus, if you reffer property of object inside collection, it understands that we need to iterate it.

Let us assume we have information about customer names. JSON representation of the object:

.. code:: json

    [
        {        
            "firstName": "Efren ",
            "lastName": "Gaskill"
        }, {        
            "firstName": "Sanly",
            "lastName": "Keyme"            
        }, {        
            "firstName": "Mark",
            "lastName": "Nigma"            
        }        
    ]

The template on the left site will result into the document on the left side:

.. image:: ../../_static/img/document-generation/simple-bullet-list-template-result.png
   :alt: Simple table template

Review `Lists <link>`_ for more complex scenarios.

The same approach works for tables:

.. image:: ../../_static/img/document-generation/simple-table-template-result.png
   :alt: Simple table template

Review `Tables <link>`_ for more complex scenarios.

Advanced scenarios
------------------

Now, when you now how to create basic templates, it is time to review more advanced scenarios:

.. toctree::      
    :name: toc-templating-syntax
    :maxdepth: 1
                              
    Lists <lists>
    Tables <tables>