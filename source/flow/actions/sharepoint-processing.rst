SharePoint connector
==================================

This connector helps you to automatically generate and convert documents. Before starting, ensure that you `added Plumsail Documents connector to Microsoft Flow <../getting-started/use-from-flow.html>`_.

Change Permissions
----------------------------------

It is a complex action which include 12 actions for changing permissions for your SharePoint objects: sites, lists, and items.
On the first step of working with this action you need to specify two parameters:

* Actions type - The type of action on changing permissions: Grant, Remove, RemoveAll, RestoreInheritance
* Target - the target of action: Site, List, Item

.. image:: ../../_static/img/flow/sharepoint/ChangePermissionsExample.png
   :alt: Change Permissions Example

After that, others fields of the form will be generated automatically based on these parameters.

You may find the documentation of all actions which included in "Change Permissions" below:

- :ref:`grant-permissions-site`
- :ref:`remove-permissions-site`
- :ref:`remove-all-permissions-site`
- :ref:`restore-inheritance-permissions-site`
- :ref:`grant-permissions-list`
- :ref:`remove-permissions-list`
- :ref:`remove-all-permissions-list`
- :ref:`restore-inheritance-permissions-list`
- :ref:`grant-permissions-item`
- :ref:`remove-permissions-item`
- :ref:`remove-all-permissions-item`
- :ref:`restore-inheritance-permissions-item`


.. _grant-permissions-site:

Grant Permissions on Site
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Grant specific permissions to an user site

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  User or group
       -  Login, Email or Name of the User or Group. Also you can specify multiple items using semicolon ';' delimited
       -  :code:`user@contoso.com`
    *  -  Role Type
       -  permission levels:
                   * Full control
                   * Design
                   * Edit
                   * Contribute
                   * Read
                   * ViewOnly
                
       -  Read
    *  -  SharePoint Site Url
       -  The URL of the current SharePoint site. This property defines context of the workflow action. All actions performed by workflow action will be executed on specified SharePoint site. If this property is blank it will use current SharePoint site by default.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/GrantPermissionsOnSiteExample.png
   :alt: Grant Permissions on Site Example

.. _remove-permissions-site:

Remove Permissions from Site
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Delete specific permissions from Site for specified user or group

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  User or group
       -  Login, Email or Name of the User or Group. Also you can specify multiple items using semicolon ';' delimited
       -  :code:`user@contoso.com`
    *  -  Role Type
       -  permission levels:
                   * Full control
                   * Design
                   * Edit
                   * Contribute
                   * Read
                   * ViewOnly
                
       -  Read
    *  -  SharePoint Site Url
       -  The URL of the current SharePoint site. This property defines context of the workflow action. All actions performed by workflow action will be executed on specified SharePoint site. If this property is blank it will use current SharePoint site by default.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/RemovePermissionsOnSiteExample.png
   :alt: Remove Permissions from Site Example   

.. _remove-all-permissions-site:

Remove All Permissions from Site
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Removing all user permissions from a SharePoint Site

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  SharePoint Site Url
       -  The URL of the current SharePoint site. This property defines context of the workflow action. All actions performed by workflow action will be executed on specified SharePoint site. If this property is blank it will use current SharePoint site by default.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/RemoveAllPermissionsOnSiteExample.png
   :alt: Remove All Permissions from Site Example    

.. _restore-inheritance-permissions-site:

Restore Permissions Inheritance for Site
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Remove unique permissions and restore permission inheritance on current SharePoint Site

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  SharePoint Site Url
       -  The URL of the current SharePoint site. This property defines context of the workflow action. All actions performed by workflow action will be executed on specified SharePoint site. If this property is blank it will use current SharePoint site by default.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/RestorePermissionsOnSiteExample.png
   :alt: Restore Permissions Inheritance for Site Example  

.. _grant-permissions-list:

Grant Permissions on List
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Grant specific permissions to a user on a list

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  List name
       -  Title or Url of the list
       -  Sales
    *  -  User or group
       -  Login, Email or Name of the User or Group. Also you can specify multiple items using semicolon ';' delimited
       -  :code:`user@contoso.com`
    *  -  Role Type
       -  permission levels:
                   * Full control
                   * Design
                   * Edit
                   * Contribute
                   * Read
                   * ViewOnly
                
       -  Read
    *  -  SharePoint Site Url
       -  The URL of the current SharePoint site. This property defines context of the workflow action. All actions performed by workflow action will be executed on specified SharePoint site. If this property is blank it will use current SharePoint site by default.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/GrantPermissionsOnListExample.png
   :alt: Grant Permissions on List Example

.. _remove-permissions-list:

Remove Permissions from List
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Delete specific permissions from a user on a list

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  List name
       -  Title or Url of the list
       -  Sales
    *  -  User or group
       -  Login, Email or Name of the User or Group. Also you can specify multiple items using semicolon ';' delimited
       -  :code:`user@contoso.com`
    *  -  Role Type
       -  permission levels:
                   * Full control
                   * Design
                   * Edit
                   * Contribute
                   * Read
                   * ViewOnly
                
       -  Read
    *  -  SharePoint Site Url
       -  The URL of the current SharePoint site. This property defines context of the workflow action. All actions performed by workflow action will be executed on specified SharePoint site. If this property is blank it will use current SharePoint site by default.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/RemovePermissionsOnListExample.png
   :alt: Remove Permissions from List Example   

.. _remove-all-permissions-list:

Remove All Permissions from List
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Removing all user permissions from a SharePoint List

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  List name
       -  Title or Url of the list
       -  Sales
    *  -  SharePoint Site Url
       -  The URL of the current SharePoint site. This property defines context of the workflow action. All actions performed by workflow action will be executed on specified SharePoint site. If this property is blank it will use current SharePoint site by default.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/RemoveAllPermissionsOnListExample.png
   :alt: Remove All Permissions from List Example    

.. _restore-inheritance-permissions-list:

Restore Permissions Inheritance for List
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Remove unique permissions and restore permission inheritance on a SharePoint list

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  List name
       -  Title or Url of the list
       -  Sales
    *  -  SharePoint Site Url
       -  The URL of the current SharePoint site. This property defines context of the workflow action. All actions performed by workflow action will be executed on specified SharePoint site. If this property is blank it will use current SharePoint site by default.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/RestorePermissionsOnListExample.png
   :alt: Restore Permissions Inheritance for List Example  

.. _grant-permissions-item:

Grant Permissions on Item
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Grant specific permissions to a user on an item

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Item ID
       -  ID of the item
       -  7
    *  -  List name
       -  Title or Url of the list
       -  Sales
    *  -  User or group
       -  Login, Email or Name of the User or Group. Also you can specify multiple items using semicolon ';' delimited
       -  :code:`user@contoso.com`
    *  -  Role Type
       -  permission levels:
                   * Full control
                   * Design
                   * Edit
                   * Contribute
                   * Read
                   * ViewOnly
                
       -  Read
    *  -  SharePoint Site Url
       -  The URL of the current SharePoint site. This property defines context of the workflow action. All actions performed by workflow action will be executed on specified SharePoint site. If this property is blank it will use current SharePoint site by default.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/GrantPermissionsOnItemExample.png
   :alt: Grant Permissions on Item Example

.. _remove-permissions-item:

Remove Permissions from Item
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Delete specific permissions from a user on an item

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Item ID
       -  ID of the item
       -  7
    *  -  List name
       -  Title or Url of the list
       -  Sales
    *  -  User or group
       -  Login, Email or Name of the User or Group. Also you can specify multiple items using semicolon ';' delimited
       -  :code:`user@contoso.com`
    *  -  Role Type
       -  permission levels:
                   * Full control
                   * Design
                   * Edit
                   * Contribute
                   * Read
                   * ViewOnly
                
       -  Read
    *  -  SharePoint Site Url
       -  The URL of the current SharePoint site. This property defines context of the workflow action. All actions performed by workflow action will be executed on specified SharePoint site. If this property is blank it will use current SharePoint site by default.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/RemovePermissionsOnItemExample.png
   :alt: Remove Permissions from Item Example   

.. _remove-all-permissions-item:

Remove All Permissions from Item
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Removing all user permissions from a SharePoint Item

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Item ID
       -  ID of the item
       -  7
    *  -  List name
       -  Title or Url of the list
       -  Sales
    *  -  SharePoint Site Url
       -  The URL of the current SharePoint site. This property defines context of the workflow action. All actions performed by workflow action will be executed on specified SharePoint site. If this property is blank it will use current SharePoint site by default.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/RemoveAllPermissionsOnItemExample.png
   :alt: Remove All Permissions from Item Example    

.. _restore-inheritance-permissions-item:

Restore Permissions Inheritance for Item
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Remove unique permissions and restore permission inheritance on a SharePoint Item

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Item ID
       -  ID of the item
       -  7
    *  -  List name
       -  Title or Url of the list
       -  Sales
    *  -  SharePoint Site Url
       -  The URL of the current SharePoint site. This property defines context of the workflow action. All actions performed by workflow action will be executed on specified SharePoint site. If this property is blank it will use current SharePoint site by default.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/RestorePermissionsOnItemExample.png
   :alt: Restore Permissions Inheritance for Item Example

Activate Feature
----------------------------------

Activate a feature with specific ID

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Feature ID
       -  Unique ID of the feature to activate
       -  {D7891031-E7F5-4734-8077-9189DD35551C}

    *  -  Force
       -  Yes to force activation of the Feature even if there are errors; otherwise, false.
       -  Yes 

    *  -  Is Web Feature
       -  Yes if it is web feature otherwise, false.
       -  Yes

    *  -  SharePoint Site Url
       -  The URL of the current SharePoint site. This property defines the context of the workflow action. All actions performed by workflow action will be executed on specified SharePoint site.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/ActivateFeatureExample.png
   :alt: Activate Feature Example

Create List or Library
----------------------------------

Create list by template.

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Title
       -  Title of the list.
       -  Sales reports

    *  -  Template
       -  Title of the template that will be used for this list.
       -  Custom List

    *  -  Partial Url
       -  Usually, when you create a list you can't control which URL it will get. For example, if you create a document library with the name "Some document lib" it will get the following URL: Some%20doc%20lib. But in some cases more useful to choose other URL, using this field, you can specify the required value. This is an optional field you can leave it blank. By default, URL will be automatically generated.
       -  Sales_Department

    *  -  Description
       -  Description of the list.
       -  Library contains sales reports

    *  -  On Quick Nav
       -  Display this list on the Quick Launch.
       -  Yes

    *  -  SharePoint Site Url
       -  The URL of the current SharePoint site. This property defines the context of the workflow action. All actions performed by workflow action will be executed on specified SharePoint site.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/CreateListOrLibraryExample.png
   :alt: Create List or Library Example

Create Site from Template
----------------------------

Create a new SharePoint site based on specific template.

.. rubric:: Output Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Web URL
       -  URL of the created SharePoint site.
       -  :code:`https://contoso/sites/newSubSite`

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Title
       -  Title of new site.
       -  Sales department
       
    *  -  Description
       -  Description of the web.
       -  Sales department's site
       
    *  -  Template
       -  Title of the site template that will be used for the new site.
       -  Team Site

    *  -  Leaf URL
       -  A string that represents the URL leaf name
       -  Sales_Department

    *  -  Lcid
       -  LCID of the new web.
       -  1033

    *  -  Inherit Permissions
       -  Specifies whether the new site will inherit permissions from its parent site.
       -  Yes

    *  -  Inherit navigation
       -  Specifies whether the site inherits navigation.
       -  No

    *  -  On top navigation
       -  Display this site on the top link bar of the parent site. The default value is Yes.
       -  Yes

    *  -  On quick launch
       -  Display this site on the Quick Launch of the parent site. The default value is No.
       -  No

    *  -  SharePoint Site Url
       -  The URL of the current SharePoint site. This property defines the context of the workflow action. All actions performed by workflow action will be executed on specified SharePoint site.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/CreateSiteFromTemplateExample.png
   :alt: Create Site from Template Example

Set Default Site Group
----------------------------

Configure default groups for the site it is analog of the permsetup.aspx page.

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Group Type
       -  Type of the group: owners, members or visitors     
       -  Owners

    *  -  Group Name
       -  Name or ID of the group
       -  Sales owners

    *  -  SharePoint Site Url
       -  The URL of the current SharePoint site. This property defines the context of the workflow action. All actions performed by workflow action will be executed on specified SharePoint site.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`         

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/SetDefaultSiteGroupExample.png
   :alt: Set Default Site Group Example