Values formatters in DOCX templates
===================================

You can add formatters to add additional formatting to values rendered in your templates.

.. contents:: List of formatters
   :local:
   :depth: 1

format
------

format - if encountered on date value it will replace DateTime value with string value (short date string if time part is empty)

format(X) - replaces current value formatted by X argument (for example N2 for number with two decimals)

substring
---------

substring(n) - returns substring of provided values after n chars

substring(n,l) - returns substring of provided values after n chars with l length

join
----

join(X) - flattens array to create a string with X between (for example {1,2,3}.join(-) becomes 1-2-3)

hide
----

hide - replaces current value with empty string

bool
----

bool(yes,no) - boolean value will be converted to yes or no

bool(YES,NO,MAYBE) - boolean value will be converted to YES, NO or MAYBE

empty
-----

empty(X) - if value is null or empty (IEnumerable.length = 0) it will replace value with X


Not checked formatters
----------------------


clone - used for cloning entire document. Templater will append current document with current content.
fixed - used in resizeable objects (like table) when you don't want to resize that object. For example, you have table with fixed number of rows and want Templater to replace those IEnumerable values and replace all others with empty string
page - used for specifying resizing of the page range in docx. When tag is placed in table and you want to resize entire page, not number of rows in that table, use page to override default context resize
sheet - used for specifying resizing of the sheet in xlsx. If you want to resize sheet range you can place tag in header or use sheet metadata on tag which is used for resizing.
all - replaces all instances of selected tag with provided values. Useful when there is same tag on various places in document and Templater is unable to conclude that they should all be replaced with single value
header - for DataTable/ResultSet data types, include header during dynamic resize
horizontal-resize - in Excel resize context horizontally instead of vertically
whole-column - use whole column instead of minimum spanning range during horizontal resize
merge-nulls - special handling of null values in tables/cells. Cells will be horizontally merged if null value is detected
span-nulls - special handling of null values in Word tables. Cells will be vertically merged if null value is detected
remove-old-xml - when XElement/Element is provided, remove the XML tree where tag was detected. Useful for cleaning up whitespace garbage
replace-xml - when XElement/Element is provided, remove the children of matching XML tree and replace it with the provided XML. Useful for setting color in Word tables
merge-xml - when XElement/Element is provided, merge provided XML with the surounding XML of the detected tag. Useful for setting color without removing old XML
page-break - when doing resize include page break between elements (probably should not be used)
no-repeat - to invoke old behavior of processing only the first collection with matching tags (probably should not be used)


padLeft(n) - append space from left to create string of at least n length
padLeft(n,c) - append char c from left to create string of at least n length
padRight(n) - append space from right to create string of at least n length
padRight(n,c) - append char c from right to create string of at least n length


offset(D\:H:M) - DateTime value will be offsetted by parsed Timestamp (special sign : is escaped with \)
collapse - if value is null or empty (IEnumerable.length = 0) current context will be collapsed; tag will be removed - resize(tag, 0) will be invoked
collapse-nested - if value is null or empty (IEnumerable.length = 0) context matching all related tags will be collapsed; specified and all nested tags will be removed - resize(tags, 0) will be invoked
collapse-to(otherTag) - if value is null or empty (IEnumerable.length = 0) current context between original and otherTag will be collapsed; tags will be removed - resize(Array(tag, otherTag), 0) will be invoked. Other tag can have same value as original tag