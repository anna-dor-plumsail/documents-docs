External Links
==============

.. _external-links:

*Create DOCX from template* actions allows you to add a dynamic hyperlink to a location on the web  or to a new email message.

Let us assume we have a list of online learning resources. JSON representation of the object:

.. code:: json

    [
        {
            "name": "The Open University",
            "description": "Distance and online courses. Qualifications range from certificates, diplomas and short courses to undergraduate and postgraduate degrees.",
            "link_name": "Go to the site",
            "link_url": "http://www.openuniversity.edu/courses"
        },
        {
            "name": "Coursera",
            "description": "Online courses from top universities like Yale, Michigan, Stanford, and leading companies like Google and IBM.",
            "link_name": "Go to the site",
            "link_url": "https://plato.stanford.edu/"
        },
        {
            "name": "edX",
            "description": "Flexible learning on your schedule. Access more than 1900 online courses from 100+ leading institutions including Harvard, MIT, Microsoft, and more.",
            "link_name": "Go to the site",
            "link_url": "https://www.edx.org/"
        }
    ]


Now, let us take a look at the source template for this structure:

.. image:: ../../_static/img/document-generation/external-links-template.png
    :alt: External links template

We designed a table with a header and just one row that contains our tags. The templating engine is smart enough to understand what content needs to be duplicated.

To refer properties of the objects we just used the names of the properties:

:code:`{{name}}`, :code:`{{description}}`, :code:`{{link_name}}`, :code:`{{link_url}}`.

To create a hyperlink to a location on the web we select the text that we want to display as a hyperlink, on the **Insert** tab in MS Word, click **Link**, navigate to the **Existing File or Web Page** tab and add a tag into the **Address** field:

.. image:: ../../_static/img/document-generation/insert-hyperlink-url.png
    :alt: Insert hyperlink: URL

We have also added endnotes to our template. To do that please click where you want to add an endnote, click **References** in the top ribbon and **Insert Endnote**.

.. image:: ../../_static/img/document-generation/insert-endnote.png
    :alt: Insert endnote

Endnotes and footnotes maintain the context of their definition. This allows the template engine to replace multiple tags which belong to the same context.

You can see the result of rendering below. The templating engine created web hyperlinks in the document:

.. image:: ../../_static/img/document-generation/external-links-result.png
    :alt: External links result

You can download the source document and the result document for this example in `external links demo <./demos.html#external-links>`_.