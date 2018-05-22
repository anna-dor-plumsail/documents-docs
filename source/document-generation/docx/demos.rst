Demos
=====

.. contents:: List of demos
   :local:
   :depth: 1

.. _loops-and-nesting:

Loops and nesting
-----------------

This demo demonstrates how to create complex nested documents based on nested objects and collections. You can find descriptin of this case in the `loops and nesting <loops-and-nesting.html>`_ documentation.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/loops-nesting-template.docx>`_
         
          .. image:: ../../_static/img/document-generation/loops-nesting-template.png
                :alt: Loops and nesting template
        - `Download result document <../../_static/files/document-generation/demos/loops-nesting-result.docx>`_
         
          .. image:: ../../_static/img/document-generation/loops-nesting-result.png
                :alt: Loops and nesting template                    

.. rubric:: Template data

.. code:: json    

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