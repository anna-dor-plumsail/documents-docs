Value formatters in DOCX templates
===================================

You can use formatters to add complex logic to values rendered in your templates. For example, you can change value format, hide content, join arrays, etc.

.. contents:: List of formatters
   :local:
   :depth: 1

format
------

This formatter formats value from tag. You can use it with or without parameters:

- :code:`format` - if encountered on date value it will forat it as short date string.
- :code:`format(val)` - formats current value using specified format. For example, you can use :code:`N2` for number with two decimals.

It uses standad format strings. You can find more information in Microsoft documentation:

- `Numberic format strings <https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-numeric-format-strings>`_
- `Date and time format strings <https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings>`_

Examples
~~~~~~~~

.. list-table::
    :header-rows: 1

    *   - Template
        - Data
        - Result
    *   - .. code-block:: json
    
            Date: {{date}:format(d MMM yyyy)}
            Date: {{date}:format(MM/dd)}
            Date: {{date}:format(U)}
            Number: {{num}:format(C)}
            Number: {{num}:format(P)}
            Number: {{num}:format(N2)}

        - .. code-block:: json

            {                     
                "date": "2012-04-21T18:25:43-05:00",
                "num": 8
            }        

        - .. code-block:: json
    
            Date: 22 Apr 2012
            Date: 04/22
            Saturday, April 21, 2012 11:25:43 PM
            Number: $8.00
            Number: 800.00%
            Number: 8.00
   
substring
---------

Returns substring. You can use it with one or two parameters:

- :code:`substring(index)` - returns substring of provided values after :code:`index` chars
- :code:`substring(index,length)` - returns substring of provided values after :code:`index` with :code:`length`.

Examples
~~~~~~~~

.. list-table::
    :header-rows: 1

    *   - Template
        - Data
        - Result
    *   - .. code-block:: json
    
            {{stringVal}:substring(6)}
            {{stringVal}:substring(0, 5)}     

        - .. code-block:: json

            {                     
                "stringVal" "Derek Clark"
            }        

        - .. code-block:: json
    
            Clark
            Derek        

join
----

:code:`join(separator)` - joins array values with an :code:`separator`.

Examples
~~~~~~~~

.. list-table::
    :header-rows: 1

    *   - Template
        - Data
        - Result
    *   - .. code-block:: json
    
            {{arr}:join(, )}
            {{arr}:join(; )
            {{arr}:join(-)}

        - .. code-block:: json

            {                     
                "stringVal" "Derek Clark"
            }        

        - .. code-block:: json
    
            1, 2, 3
            1; 2; 3
            1-2-3      

offset
------

:code:`offset(d)` - date and time value will be offsetted by :code:`d` days. 

:code:`offset(d.hh\:mm\:ss)` - advanced approach for offsetting :code:`d` days, :code:`hh` hours, :code:`mm` minutes, :code:`ss` seconds. 

Just replace :code:`d`, :code:`hh`, :code:`mm` and :code:`ss` by required number of days, hours, minutes and seconds in this string pattern :code:`d.hh\:mm\:ss`.

Examples
~~~~~~~~

.. list-table::
    :header-rows: 1

    *   - Template
        - Data
        - Result
    *   - .. code-block:: json
    
            Without offset:
            {{date}}
            
            Plus 10 days
            {{date}:offset(10)}
            
            Minus 10 days:
            {{date}:offset(-10)}
            
            Plus 10 days, 1 hour, 
            5 minutes, 10 seconds:
            {{date}:offset(10.1\:5\:10)}
            
            Minus 10 days, 1 hour, 
            5 minutes, 10 seconds:
            {{date}:offset(-10.1\:5\:10)}

        - .. code-block:: json

            {                     
                "date" "2012-04-21T18:25:43-05:00"
            }        

        - .. code-block:: json
    
            Without offset:
            4/22/2012 3:25:43 AM
            
            Plus 10 days
            5/2/2012 3:25:43 AM
            
            Minus 10 days:
            4/12/2012 3:25:43 AM
            
            Plus 10 days, 1 hour, 
            5 minutes, 10 seconds:
            5/2/2012 4:30:53 AM

            Minus 10 days, 1 hour, 
            5 minutes, 10 seconds:
            4/12/2012 2:20:33 AM                                        

hide
----

:code:`hide` - replaces current value with empty string.

Examples
~~~~~~~~

.. list-table::
    :header-rows: 1

    *   - Template
        - Data
        - Result
    *   - .. code-block:: json
    
            {{val1}}
            {{val2}:hide}

        - .. code-block:: json

            {                     
                "val1" "Derek Clark",
                "val2" "Jessica Adams"
            }         

        - .. code-block:: json
    
            Derek Clark

bool
----

:code:`bool(yes,no,maybe)` - boolean value will be converted to :code:`yes`, :code:`no` or :code:`maybe`. You can specify your own value for each state. The last parameter is optional.

Examples
~~~~~~~~

.. list-table::
    :header-rows: 1

    *   - Template
        - Data
        - Result
    *   - .. code-block:: json
    
            {{boolVal1}:bool(yes,no,maybe)}
            {{boolVal2}:bool(yes,no,maybe)}
            {{boolVal3}:bool(yes,no,maybe)}

        - .. code-block:: json

            {                     
                "boolVal1": true,
                "boolVal2": false,
                "boolVal3": null,
            }         

        - .. code-block:: json
    
            yes
            no
            maybe

empty
-----

:code:`empty(val)` - if value in tag is null, empty or empty array it will replace value with :code:`val`. You can use this formatter to display default value. For example, "N/A".

Examples
~~~~~~~~

.. list-table::
    :header-rows: 1

    *   - Template
        - Data
        - Result
    *   - .. code-block:: json
    
            {{val1}:empty(N/A)}
            {{val2}:empty(N/A)}
            {{val3}:empty(N/A)}


        - .. code-block:: json

            {                     
                "val1": "Jessica Adams",
                "val2": "",
                "val3": [],
            }         

        - .. code-block:: json
    
            Jessica Adams
            N/A
            N/A

collapse
--------

collapse - if value is null or empty (IEnumerable.length = 0) current context will be collapsed; tag will be removed - resize(tag, 0) will be invoked

page
----

:code:`page` - it can be used for changing logic of repeating collections. When tag is placed in table and you want to repeat entire page instead of a table cell, use page to override default repeating logic.

.. list-table::
    :header-rows: 1

    *   - Template
        - Data
        - Result
    *   - .. image:: ../../_static/img/document-generation/page-formatter-template.png
            :alt: page formatter template

        - .. code-block:: json

            {                     
                "collection": [
                    {
                        "name": "Derek Clark",
                        "sold": 10000
                    },
                    {
                        "name": "Jessica Adams",
                        "sold": 14000
                    },
                    {
                        "name": "Xue Li",
                        "sold": 9400
                    }
                ]
            }         

        - 
        
            New pages are added instead of new table rows:
        
            .. image:: ../../_static/img/document-generation/page-formatter-result.png
                :alt: page formatter result


Not checked formatters
----------------------

clone - used for cloning entire document. Templater will append current document with current content.
fixed - used in resizeable objects (like table) when you don't want to resize that object. For example, you have table with fixed number of rows and want Templater to replace those IEnumerable values and replace all others with empty string
whole-column - use whole column instead of minimum spanning range during horizontal resize
merge-nulls - special handling of null values in tables/cells. Cells will be horizontally merged if null value is detected
span-nulls - special handling of null values in Word tables. Cells will be vertically merged if null value is detected

page-break - when doing resize include page break between elements (probably should not be used)
no-repeat - to invoke old behavior of processing only the first collection with matching tags (probably should not be used)


padLeft(n) - append space from left to create string of at least n length
padLeft(n,c) - append char c from left to create string of at least n length
padRight(n) - append space from right to create string of at least n length
padRight(n,c) - append char c from right to create string of at least n length