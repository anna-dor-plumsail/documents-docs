Demos for XLSX templates
========================

.. contents:: List of demos
   :local:
   :depth: 1


.. _tables:

Regular table
-------------

This demo shows how to create a table based on an array of objects. You can find the description of this case in the `tables <tables.html#table>`_ documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/table-template.xlsx>`_

          .. image:: ../../_static/img/document-generation/table-template-xlsx.png
                :alt: Table template
        - `Download result document <../../_static/files/document-generation/demos/table-result.xlsx>`_

          .. image:: ../../_static/img/document-generation/table-result-xlsx.png
                :alt: Table template result

.. rubric:: Template data

.. code:: json

    {
        "company": {
            "name": "Plumsail",
            "email": "contact@plumsail.com"
        },
        "employees": [
            {
                "name": "Derek Clark",
                "jobTitle": "Marketing director",
                "department": "Marketing Department",
                "office": "Room 18",
                "phone": "(206) 854-9798"
            },
            {
                "name": "Xue Li",
                "jobTitle": "Financial director",
                "department": "Financial Department",
                "office": "Room 19",
                "phone": "(206) 598-1259"
            },
            {
                "name": "Jessica Adams",
                "jobTitle": "Marketing manager",
                "department": "Marketing Department",
                "office": "Room 23",
                "phone": "(206) 789-1598"
            },
            {
                "name": "Katsuko Kawakami",
                "jobTitle": "Analyst",
                "department": "Financial Department",
                "office": "Room 26",
                "phone": "(206) 784-1258"
            }
        ]
    }

.. _dynamic-table:

Dynamic table
-------------

This demo shows how to create dynamic tables from arrays by just adding a single tag into the template document. You can find the description of this case in the `tables <tables.html#dynamic-table>`_ documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/table-from-array-template.xlsx>`_

          .. image:: ../../_static/img/document-generation/table-from-array-template-xlsx.png
                :alt: Table from array template
        - `Download result document <../../_static/files/document-generation/demos/table-from-array-result.xlsx>`_

          .. image:: ../../_static/img/document-generation/table-from-array-result-xlsx.png
                :alt: Table from array result

.. rubric:: Template data

.. code:: json

    {
        "myArray": [
            [
                "between",
                "inter-",
                "epi-"
            ],
            [
                "above, excess",
                "super-, ultra-",
                "hyper-"
            ],
            [
                "inside",
                "intra-",
                "endo-"
            ],
            [
                "outside",
                "extra-, extro-",
                "ecto-, exo-"
            ]
        ]
    }

.. _dynamic-table-columns:

Repeat multiple table rows
--------------------------

This demo shows how to occupy multiple table rows by properties of a single object from your source array. You can find the description of this case in the `tables <tables.html#repeat-multiple-table-rows>`_ documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/repeat-multiple-table-rows-result.xlsx>`_

          .. image:: ../../_static/img/document-generation/repeat-multiple-table-rows-template-xlsx.png
                :alt: Repeat multiple table rows template
        - `Download result document <../../_static/files/document-generation/demos/repeat-multiple-table-rows-template.xlsx>`_

          .. image:: ../../_static/img/document-generation/repeat-multiple-table-rows-result-xlsx.png
                :alt: Repeat multiple table rows result

.. rubric:: Template data

.. code:: json

    [
        {
            "name": "David Navarro",
            "phone": "(206) 854-9798",
            "title": "Head of Marketing"
        },
        {
            "name": "Jessica Adams",
            "phone": "(206) 789-1598",
            "title": "Financial director"
        },
        {
            "name": "Anil Mittal",
            "phone": "(206) 784-1258",
            "title": "Sales manager"
        }
    ]

.. _loops-and-nesting:

Loops and nesting
-----------------

This demo demonstrates how to create complex nested documents based on nested objects and collections. You can find the description of this case in the `loops and nesting <loops-and-nesting.html>`_ documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/loops-and-nesting-template.xlsx>`_

          .. image:: ../../_static/img/document-generation/xlsx-loops-and-nesting-template.png
                :alt: Loops and nesting template
        - `Download result document <../../_static/files/document-generation/demos/loops-and-nesting-result.xlsx>`_

          .. image:: ../../_static/img/document-generation/xlsx-loops-and-nesting-result.png
                :alt: Loops and nesting result

.. _loops-and-nesting-data:

.. rubric:: Template data

.. code:: json

    {
        "reports":[
            {
                "quarter": "Q1",
                "sales": [
                    {
                        "month": "Jan",
                        "products": [
                            {
                                "name": "Television set", 
                                "total": 63225.81
                            },
                            {
                                "name": "Fridge",                            
                                "total": 15500
                            },
                            {
                                "name": "Microwave",                            
                                "total": 29032.26
                            }
                        ]
                    },
                    {
                        "month": "Feb",
                        "products": [
                            {
                                "name": "Television set", 
                                "total": 47419.35
                            },
                            {
                                "name": "Fridge",                            
                                "total": 20500
                            },
                            {
                                "name": "Microwave",                            
                                "total": 23467.74
                            }
                        ]
                    },
                    {
                        "month": "Mar",
                        "products": [
                            {
                                "name": "Television set", 
                                "total": 48548.39
                            },
                            {
                                "name": "Fridge",                            
                                "total": 12500
                            },
                            {
                                "name": "Microwave",                            
                                "total": 19354.83
                            }
                        ]
                    }
                ]
            },
            {
                "quarter": "Q2",
                "sales": [
                    {
                        "month": "Apr",
                        "products": [
                            {
                                "name": "Television set", 
                                "total": 54193.55
                            },
                            {
                                "name": "Fridge",                            
                                "total": 14500
                            },
                            {
                                "name": "Microwave",                          
                                "total": 35080.65
                            }
                        ]
                    },
                    {
                        "month": "May",
                        "products": [
                            {
                                "name": "Television set", 
                                "total": 44032.25
                            },
                            {
                                "name": "Fridge",                            
                                "total": 17500
                            },
                            {
                                "name": "Microwave",                            
                                "total": 24435.48
                            }
                        ]
                    },
                    {
                        "month": "Jun",
                        "products": [
                            {
                                "name": "Television set", 
                                "total": 42903.23
                            },
                            {
                                "name": "Fridge",                            
                                "total": 11500
                            },
                            {
                                "name": "Microwave",                            
                                "total": 36290.32
                            }
                        ]
                    }
                ]
            }
        ]
    }

 .. _multiple-worksheets:

Multiple worksheets
--------------------------

This demo shows how to create multiple worksheets in one file. You can find the description of this case in the `multiple worksheets <multiple-worksheets.html>`_ section of the documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/multiple-worksheets-template.xlsx>`_

          .. image:: ../../_static/img/document-generation/multiple-worksheets-template.png
                :alt: Multiple worksheets template
        - `Download result document <../../_static/files/document-generation/demos/multiple-worksheets-result.xlsx>`_

          .. image:: ../../_static/img/document-generation/multiple-worksheets-result.png
                :alt: Multiple worksheets result

.. rubric:: Template data

.. code:: json

    [
        {
            "name": "Jessica Adams",
            "jobInfo": {
                "title": "Marketing manager",
                "department": "Marketing Department",
                "manager": "Derek Clark",
                "telephone": "(206) 789-1598",
                "dateOfHire": "2012-04-21T00:00:00"
            },
            "personalInfo": {
                "address": "132, My Street, Kingston, New York 12401",
                "cell": "(123) 555-5551",
                "dateOfBirth": "1983-08-22",
                "SIN": "046 454 286"
            },
            "inCaseOfEmergency": {
                "name": "Sarah Adams",
                "relationship": "Mom",
                "telephone": "(123) 987-6541",
                "cell": "(123) 444-4441"
            }
        },
        {
            "name": "Katsuko Kawakami",
            "jobInfo": {
                "title": "Analyst",
                "department": "Financial Department",
                "manager": "Xue Li",
                "telephone": "(206) 784-1258",
                "dateOfHire": "2016-03-06T00:00:00"
            },
            "personalInfo": {
                "address": "257, My Street, East Village, New York 12401",
                "cell": "(123) 555-5552",
                "dateOfBirth": "1979-09-19",
                "SIN": "073 454 287"
            },
            "inCaseOfEmergency": {
                "name": "Jane Smith",
                "relationship": "Friend",
                "telephone": "(123) 987-6542",
                "cell": "(123) 333-3332"
            }
        },
        {
            "name": "Brenda Coel",
            "jobInfo": {
                "title": "Marketing director",
                "department": "Marketing Department",
                "manager": "Derek Clark",
                "telephone": "(206) 854-9798",
                "dateOfHire": "2011-11-05T00:00:00"
            },
            "personalInfo": {
                "address": "87, My Street, Lower East Side, New York 12401",
                "cell": "(123) 555-5553",
                "dateOfBirth": "1975-12-01",
                "SIN": "051 454 288"
            },
            "inCaseOfEmergency": {
                "name": "John Smith",
                "relationship": "Husband",
                "telephone": "(123) 987-6543",
                "cell": "(123) 222-2223"
            }
        }
    ]


.. _links:

Links
-----

This demo shows how to add external links to your document. You can find the description of this case in the `links <external-links.html>`_ section of the documentation.

Scroll down to see source data for the template in JSON format.

.. list-table::
    :header-rows: 1

    *   - Template
        - Result
    *   - `Download template document <../../_static/files/document-generation/demos/external-links-template.xlsx>`_

          .. image:: ../../_static/img/document-generation/external-links-template-xlsx.png
                :alt: Links template
        - `Download result document <../../_static/files/document-generation/demos/external-links-result.xlsx>`_

          .. image:: ../../_static/img/document-generation/external-links-result-xlsx.png
                :alt: Links result

.. rubric:: Template data

.. code:: json

    [
        {
            "name": "Coursera",
            "type": "Commercial",
            "headquarters": "USA",
            "linkName": "Go to the site",
            "linkURL": "https://plato.stanford.edu/"
        },
        {
            "name": "edX",
            "type": "Non-profit",
            "headquarters": "USA",
            "linkName": "Go to the site",
            "linkURL": "https://www.edx.org/"
        },
        {
            "name": "FutureLearn",
            "type": "Commercial",
            "headquarters": "UK",
            "linkName": "Go to the site",
            "linkURL": "https://www.futurelearn.com/"
        }
    ]