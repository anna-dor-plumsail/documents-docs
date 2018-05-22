Loops and nesting in DOCX templates
===================================

.. contents::
   :local:
   :depth: 1

Overview
--------

You can learn how to create simple `bullet lists <./lists.html>`_ and `tables <./tables.html>`_ in other sections of this documentation. Here we will learn how to implement more complex scenarios with nesting. 

The templating engine allows you to create following repeating objects:

- Tables
- Bullet lists
- Chapters

You can create nested constructions by putting one repeating object inside another. Review the `loops and nesting demo <./demos.html#loops-and-nesting>`_. 

A template like this:

.. image:: ../../_static/img/document-generation/loops-nesting-template.png
   :alt: Loops and nesting template

Can produce result like below. You can see all possible types of repeating objects nested one inside another:

.. image:: ../../_static/img/document-generation/loops-nesting-result.png
   :alt: Loops and nesting result

The result is built based on complex nested object with nested collection. JSON representation of the object:

.. code:: json
    :class: pl-fixed-code-block

    [
        {
            "name": "David Navarro",
            "companies": [
                {
                    "name": "Plumsail",
                    "projects": [
                        {
                            "name": "Plumsail Actions",
                            "achievement": [
                                {
                                    "description": "Design the hardware"
                                },
                                {
                                    "description": "Design the software"
                                },
                                {
                                    "description": "Implement the software"
                                }
                            ]
                        },
                        {
                            "name": "Plumsail Forms",
                            "achievement": [
                                {
                                    "description": "Design everything"
                                },
                                {
                                    "description": "Implement everything"
                                }
                            ]
                        }
                    ],
                    "managers": [
                        {
                            "name": "Derek clark",
                            "title": "Head of Development",
                            "reference": "he likes programming \nand good coffee"
                        },
                        {
                            "name": "Jessica Adams",
                            "title": "CEO",
                            "reference": "I don't know this guy"
                        }
                    ]
                },
                {
                    "name": "Contoso",
                    "projects": [
                        {
                            "name": "Who knows what it was",
                            "achievement": [
                                {
                                    "description": "R&D"
                                },
                                {
                                    "description": "Bureaucracy"
                                }
                            ]
                        }
                    ],
                    "managers": [
                        {
                            "name": "Lots of people",
                            "title": "Managers",
                            "reference": "I saw this guy once in the cafeteria"
                        }
                    ]
                }
            ]
        },
        {
            "name": "Martin Harris",
            "companies": [
                {
                    "name": "Plumsail",
                    "projects": [
                        {
                            "name": "Plumsail Org Chart",
                            "achievement": [
                                {
                                    "description": "Mentor"
                                },
                                {
                                    "description": "Teach"
                                }
                            ]
                        }
                    ],
                    "managers": [
                        {
                            "name": "Anil Mittal",
                            "title": "Founder",
                            "reference": "I like the way he laughs"
                        }
                    ]
                },
                {
                    "name": "Contoso",
                    "projects": [
                        {
                            "name": "Whatever it was",
                            "achievement": [
                                {
                                    "description": "R&D"
                                },
                                {
                                    "description": "Documentation"
                                }
                            ]
                        },
                        {
                            "name": "Another old project",
                            "achievement": [
                                {
                                    "description": "Research"
                                },
                                {
                                    "description": "Development"
                                }
                            ]
                        }
                    ],
                    "managers": [
                        {
                            "name": "Brenda Coel",
                            "title": "Head of Heads",
                            "reference": "he knows the stuff"
                        },
                        {
                            "name": "Xue Li",
                            "title": "CEO",
                            "reference": "Brenda said he knows the stuff"
                        }
                    ]
                }
            ]
        }
    ]

How it works
------------

The templating engine allows you to create following repeating objects:

- Tables
- Bullet lists
- Chapters

Let us take a look at the source template one more time:

.. image:: ../../_static/img/document-generation/loops-nesting-template.png
   :alt: Loops and nesting template

You can refer to a property inside collection like this:

.. code::

    {{jobs.companyName}}

The :code:`companyName` is a property inside :code:`jobs` collection.

Actually all tags in the template above refer to properties inside collecitons. The templating engine understands it and iterates through all objects in those collecitons to render them. It is smart enought to understand what content needs to be duplicated.

When the engine finds a tag that refers to collection, it tries to find nearest object that can be duplicated. For example:

- Table cell
- Bullet list item
- Chapter

If nothing found, it thinks that whole document needs to bee duplicated.

.. note:: If you need to repeat some content that is not table, bullet list or chapter, just create a single table cell and put contant that you want to repeat inside. This approach is demonstrated above to to repeat :code:`{{jobs.companyName}}`.

Advanced scenarios
~~~~~~~~~~~~~~~~~~

The templating engine can duplicate not only single table rows and single 

You may notice that in the tempate above we duplicated two table lines


The templating engine understands that you want to iterate through this colleciton and display this property for each element of your collection. It tries to find closest repeating objects like bullet list items, table rows, chapter that contains all tags for from single item in colleciton that you want to render. The the engine uses this 
