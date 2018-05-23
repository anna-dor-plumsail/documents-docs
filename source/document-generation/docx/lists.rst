Lists in DOCX templates
=======================

Bullet lists
------------

You don't need to declare any loops, the templating engine is smart enough to understand structure of source object applied to your document. Thus, if you reffer property of object inside collection, it understands that we need to iterate it.

Let us assume we have information about customer names. JSON representation of the object:

.. code:: json

    [
        {
            "firstName": "Efren",
            "lastName": "Gaskill"
        }, {
            "firstName": "Sanly",
            "lastName": "Keyme"
        }, {
            "firstName": "Mark",
            "lastName": "Nigma"
        }
    ]


Tags in the template will look like this:

:code:`{{firstName}} {{lastName}}`

Just select the sting and change it into a bullet list by clicking the **Bullets** button:

.. image:: ../../_static/img/document-generation/bullets-button.png
    :alt: Bullets button

The template on the left site will result into the document on the left side:

.. image:: ../../_static/img/document-generation/simple-bullet-list-template-result.png
    :alt: Bullet list template


Numbered lists
--------------

As with the bullet lists, you don't need to declare any loops, the templating engine will understand structure of source object applied to your document. Thus, if you reffer property of object inside collection, it understands that we need to iterate it.

We take the same information about customer names. Here is JSON representation of the object:

.. code:: json

    [
        {
            "firstName": "Efren",
            "lastName": "Gaskill"
        }, {
            "firstName": "Sanly",
            "lastName": "Keyme"
        }, {
            "firstName": "Mark",
            "lastName": "Nigma"
        }
    ]


Tags in the template will look like this:

:code:`{{firstName}} {{lastName}}`

Select the sting and change it into a numbered list by clicking the **Numbering** button:

.. image:: ../../_static/img/document-generation/numbering-button.png
    :alt: Numbering button

The template on the left site will result into the document on the left side:

.. image:: ../../_static/img/document-generation/simple-numbering-list-template-result.png
    :alt: Numbered list template

