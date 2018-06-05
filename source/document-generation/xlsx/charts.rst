Charts in XLSX templates
========================

With help of **Create XLSX document from template** action, you can create different type of charts based on differently structured data. Let us check a few examples.

.. contents:: Content
    :local:
    :depth: 1

.. _pie-charts:

Pie charts
----------

In this section, we will see how to render an array of objects into a table and build a chart based on this table.

Let us take an object containing a list of coffee production countries and annual production of each country. We want to display a simple table with countries coffee production in 2017 and build a pie chart with  percentage value for each country.

This is how our result document will look like:

.. image:: ../../_static/img/document-generation/pie-chart-result-small.png
    :alt: Pie chart result

You can download the source document and the result document for this example in `pie and clustered columns charts demo <./demos.html#tables>`_. Description of the example is below.

JSON representation of the object:

.. code:: json

    [
        {
            "title": "Countries by coffee production",
            "description": "Production in thousand kilogram bags",
            "prod": [
                {
                    "country": "Brazil",
                    "value2015": 37600,
                    "value2016": 43200,
                    "value2017": 51500
                },
                {
                    "country": "Vietnam",
                    "value2015": 22000,
                    "value2016": 27500,
                    "value2017": 28500
                },
                {
                    "country": "Colombia",
                    "value2015": 11300,
                    "value2016": 13500,
                    "value2017": 14000
                },
                {
                    "country": "Indonesia",
                    "value2015": 14000,
                    "value2016": 11000,
                    "value2017": 10800
                },
                {
                    "country": "Honduras",
                    "value2015": 7500,
                    "value2016": 5800,
                    "value2017": 8349
                },
                {
                    "country": "Other countries",
                    "value2015": 37358
                    "value2016": 44229,
                    "value2017": 51000,
                }
            ]
        }
    ]

Now, let us take a look at the source template:

.. image:: ../../_static/img/document-generation/pie-chart-template.png
    :alt: Pie chart template

As we want to display production from 2017 only, we create a simple table and use :code:`{{prod.country}}` and :code:`{{prod.value2017}}` tags to refer needed properties inside our objects. To learn how to build a chart based on multiple columns of data please review the next `clustered columns <./charts.html#clustered-columns-charts>`_ section.

We also add :code:`{{title}}` and :code:`{{description}}` tags to the top of the page to let the engine know that we want to render corresponding properties.

To crate a chart we select our table, navigate to the **Insert** tab in the top ribbon and choose a 3-D pie chart:

.. image:: ../../_static/img/document-generation/3-D-pie-chart.png
    :alt: Adding 3-D pie chart template

Basically, the template is ready. We just want to change the design a bit and add percentage values to the data labels. We apply one of the default styles:

.. image:: ../../_static/img/document-generation/chart-style.png
    :alt: Apply one of the default styles

Then, we open **Data Label** settings, check the *Percentage* checkbox and uncheck the *Value* one:

.. image:: ../../_static/img/document-generation/pie-chart-data-label-settings.png
    :alt: Data Label settings

Let us have a look the result of rendering another time. The templating engine automatically created rows with production data and built a chart based on it:

.. image:: ../../_static/img/document-generation/pie-chart-result.png
    :alt: Pie chart result

.. _clustered-columns-charts:

Clustered columns charts
------------------------

In this section, using the data from the same JSON object as we used in the previous `pie chart example <./charts.html#pie-charts>`_ we will create a table with countries coffee production by years and build a clustered columns chart.

This is how our result document will look like:

.. image:: ../../_static/img/document-generation/clustered-columns-chart-result-small.png
    :alt: Clustered columns result

You can download the source document and the result document for this example in `pie and clustered columns charts demo <./demos.html#tables>`_. Description of the example is below.

JSON representation of the object:

.. code:: json

    [
        {
            "title": "Countries by coffee production",
            "description": "Production in thousand kilogram bags",
            "prod": [
                {
                    "country": "Brazil",
                    "value2015": 37600,
                    "value2016": 43200,
                    "value2017": 51500
                },
                {
                    "country": "Vietnam",
                    "value2015": 22000,
                    "value2016": 27500,
                    "value2017": 28500
                },
                {
                    "country": "Colombia",
                    "value2015": 11300,
                    "value2016": 13500,
                    "value2017": 14000
                },
                {
                    "country": "Indonesia",
                    "value2015": 14000,
                    "value2016": 11000,
                    "value2017": 10800
                },
                {
                    "country": "Honduras",
                    "value2015": 7500,
                    "value2016": 5800,
                    "value2017": 8349
                },
                {
                    "country": "Other countries",
                    "value2015": 37358
                    "value2016": 44229,
                    "value2017": 51000,
                }
            ]
        }
    ]

Now, let us take a look at the source template:

.. image:: ../../_static/img/document-generation/clustered-columns-chart-template.png
    :alt: Clustered columns chart template

To display production by years, we create a table and add :code:`{{prod.country}}` and :code:`{{prod.value2015}}`, :code:`{{prod.value2016}}`, :code:`{{prod.value2017}}` tags to refer the properties inside our objects.

We also add :code:`{{title}}` and :code:`{{description}}` tags to the top of the page to let the engine know that we want to render corresponding properties.

To crate a chart we select our table, navigate to the **Insert** tab in the top ribbon and choose a clustered columns chart:

.. image:: ../../_static/img/document-generation/clustered-columns-chart.png
    :alt: Adding clustered columns chart template

Now, we need to edit the data that will be visible in our chart. We select the chart, click the *Filer* icon and click *Select data* link. Here we need to add entries for production in 2015 and 2016. We may use *Production in 2017* entry as a reference:

.. image:: ../../_static/img/document-generation/clustered-columns-series.png
    :alt: Adding clustered columns series

Then, we edit the horizontal axis labels to display there the text from the first column only:

.. image:: ../../_static/img/document-generation/clustered-columns-label.png
    :alt: Adding clustered columns labels


In general, the template is ready. We just want to change the colors and add a legend under the chart:

.. image:: ../../_static/img/document-generation/clustered-columns-legend.png
    :alt: Adding clustered columns legend

Let us have a look the result of rendering another time. The templating engine automatically created rows with production data and built a chart based on it:

.. image:: ../../_static/img/document-generation/clustered-columns-chart-result.png
    :alt: Clustered columns result

.. _charts-on-multiple-worksheets:

Charts on multiple worksheets
-----------------------------

You already learned how to create different kinds of tables. In the examples above we always repeated a single table row for a single object from a source object. But you can actually occupy multiple table rows by a single object and repeat those rows for each object of your source array.

Download the source document and the result document for this example in `the repeat multiple table rows demo <./demos.html#repeat-multiple-table-rows>`_. Description of the example is below.

Let us assume we have a list of employees:

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

We want to put a name and a phone in the first table row and a job title in the second row. Then we want to repeat both lines for each employee.

This is how our source template will look in this case:

.. image:: ../../_static/img/document-generation/repeat-multiple-table-rows-template-xlsx.png
    :alt: Repeat multiple table rows template

And this is the result document:

.. image:: ../../_static/img/document-generation/repeat-multiple-table-rows-result-xlsx.png
    :alt: Repeat multiple table rows result

The templating engine understands that we used tags for properties of the same object in both table rows. Thus, it knows that it needs to repeat both rows.
