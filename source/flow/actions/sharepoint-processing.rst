SharePoint connector
==================================

Provides advanced set of Microsoft Flow actions for SharePoint. It allows you to change permissions on sites, lists, list items. You can create sites from templates and many more. 

Before starting, ensure that you `added Plumsail connector to Microsoft Flow <../../getting-started/use-from-flow.html>`_.

Change Permissions on site, list or list item
---------------------------------------------

"Change Permissions" is a complex action that includes 12 different operations for granting, removing or restoring permissions on sites, lists, and list items.

Once you added this action to your Flow, you need to specify two initial parameters:

* Action type - type of action for changing permissions: Grant, Remove, RemoveAll, RestoreInheritance
* Target - target of action: Site, List, Item

.. image:: ../../_static/img/flow/sharepoint/ChangePermissionsExample.png
   :alt: Change Permissions Example

Once you did this, you will see the rest of parameters for this particular operation.

You can find the documentation for all operations included in "Change Permissions" action below:

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

Grant specific permissions on site to a SharePoint user or Group

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Action type
       -  The type of action for changing permissions. You should pick 'Grant' for this case.
       -  Grant
    *  -  Target
       -  The target of action: Site, List, Item. You should pick 'Site' for this case.
       -  Site
    *  -  User or group
       -  Login, Email or Name of a User or Group. Also you can specify multiple items using semicolon ';' delimited
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
       -  This property defines the context of the action. The action will be executed on specified SharePoint site.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/GrantPermissionsOnSiteExample.png
   :alt: Grant Permissions on Site Example

.. _remove-permissions-site:

Remove Permissions from Site
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Delete specific permissions from site for specified SharePoint user or group

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Action type
       -  The type of action for changing permissions. You should pick 'Remove' for this case.
       -  Remove
    *  -  Target
       -  The target of action: Site, List, Item. You should pick 'Site' for this case.
       -  Site
    *  -  User or group
       -  Login, Email or Name of a User or Group. Also you can specify multiple items using semicolon ';' delimited
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
       -  This property defines the context of the action. The action will be executed on specified SharePoint site.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/RemovePermissionsOnSiteExample.png
   :alt: Remove Permissions from Site Example   

.. _remove-all-permissions-site:

Remove All Permissions from Site
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Removing all user permissions from a SharePoint site

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Action type
       -  The type of action for changing permissions. You should pick 'RemoveAll' for this case.
       -  RemoveAll
    *  -  Target
       -  The target of action: Site, List, Item. You should pick 'Site' for this case.
       -  Site
    *  -  SharePoint Site Url
       -  This property defines the context of the action. The action will be executed on specified SharePoint site.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/RemoveAllPermissionsOnSiteExample.png
   :alt: Remove All Permissions from Site Example    

.. _restore-inheritance-permissions-site:

Restore Permissions Inheritance for Site
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Remove unique permissions and restore permission inheritance on current SharePoint site

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Action type
       -  The type of action for changing permissions. You should pick 'RestoreInheritance' for this case.
       -  RestoreInheritance
    *  -  Target
       -  The target of action: Site, List, Item. You should pick 'Site' for this case.
       -  Site
    *  -  SharePoint Site Url
       -  This property defines the context of the action. The action will be executed on specified SharePoint site.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/RestorePermissionsOnSiteExample.png
   :alt: Restore Permissions Inheritance for Site Example  

.. _grant-permissions-list:

Grant Permissions on List
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Grant specific permissions to a user on a SharePoint list

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Action type
       -  The type of action for changing permissions. You should pick 'Grant' for this case.
       -  Grant
    *  -  Target
       -  The target of action: Site, List, Item. You should pick 'List' for this case.
       -  List
    *  -  List name
       -  Title or Url of a list
       -  Sales
    *  -  User or group
       -  Login, Email or Name of a User or Group. Also you can specify multiple items using semicolon ';' delimited
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
       -  This property defines the context of the action. The action will be executed on specified SharePoint site.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/GrantPermissionsOnListExample.png
   :alt: Grant Permissions on List Example

.. _remove-permissions-list:

Remove Permissions from List
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Delete specific permissions from a user on a SharePoint list

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Action type
       -  The type of action for changing permissions. You should pick 'Remove' for this case.
       -  Remove
    *  -  Target
       -  The target of action: Site, List, Item. You should pick 'List' for this case.
       -  List
    *  -  List name
       -  Title or Url of a list
       -  Sales
    *  -  User or group
       -  Login, Email or Name of a User or Group. Also you can specify multiple items using semicolon ';' delimited
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
       -  This property defines the context of the action. The action will be executed on specified SharePoint site.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/RemovePermissionsOnListExample.png
   :alt: Remove Permissions from List Example   

.. _remove-all-permissions-list:

Remove All Permissions from List
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Remove all user permissions from a SharePoint list

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Action type
       -  The type of action for changing permissions. You should pick 'RemoveAll' for this case.
       -  RemoveAll
    *  -  Target
       -  The target of action: Site, List, Item. You should pick 'List' for this case.
       -  List
    *  -  List name
       -  Title or Url of a list
       -  Sales
    *  -  SharePoint Site Url
       -  This property defines the context of the action. The action will be executed on specified SharePoint site.
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
    *  -  Action type
       -  The type of action for changing permissions. You should pick 'RestoreInheritance' for this case.
       -  RestoreInheritance
    *  -  Target
       -  The target of action: Site, List, Item. You should pick 'List' for this case.
       -  List
    *  -  List name
       -  Title or Url of a list
       -  Sales
    *  -  SharePoint Site Url
       -  This property defines the context of the action. The action will be executed on specified SharePoint site.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/RestorePermissionsOnListExample.png
   :alt: Restore Permissions Inheritance for List Example  

.. _grant-permissions-item:

Grant Permissions on Item
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Grant specific permissions to a user on a SharePoint list item

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Action type
       -  The type of action for changing permissions. You should pick 'Grant' for this case.
       -  Grant
    *  -  Target
       -  The target of action: Site, List, Item. You should pick 'Item' for this case.
       -  Item
    *  -  Item ID
       -  ID of the item
       -  7
    *  -  List name
       -  Title or Url of a list
       -  Sales
    *  -  User or group
       -  Login, Email or Name of a User or Group. Also you can specify multiple items using semicolon ';' delimited
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
       -  This property defines the context of the action. The action will be executed on specified SharePoint site.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/GrantPermissionsOnItemExample.png
   :alt: Grant Permissions on Item Example

.. _remove-permissions-item:

Remove Permissions from Item
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Delete specific permissions from a user on a SharePoint list item

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Action type
       -  The type of action for changing permissions. You should pick 'Remove' for this case.
       -  Remove
    *  -  Target
       -  The target of action: Site, List, Item. You should pick 'Item' for this case.
       -  Item
    *  -  Item ID
       -  ID of the item
       -  7
    *  -  List name
       -  Title or Url of a list
       -  Sales
    *  -  User or group
       -  Login, Email or Name of a User or Group. Also you can specify multiple items using semicolon ';' delimited
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
       -  This property defines the context of the action. The action will be executed on specified SharePoint site.
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
    *  -  Action type
       -  The type of action for changing permissions. You should pick 'RemoveAll' for this case.
       -  RemoveAll
    *  -  Target
       -  The target of action: Site, List, Item. You should pick 'Item' for this case.
       -  Item
    *  -  Item ID
       -  ID of the item
       -  7
    *  -  List name
       -  Title or Url of a list
       -  Sales
    *  -  SharePoint Site Url
       -  This property defines the context of the action. The action will be executed on specified SharePoint site.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/RemoveAllPermissionsOnItemExample.png
   :alt: Remove All Permissions from Item Example    

.. _restore-inheritance-permissions-item:

Restore Permissions Inheritance for Item
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Remove unique permissions and restore permission inheritance on a SharePoint list item

.. rubric:: Input Parameters

.. list-table::
    :header-rows: 1
    :widths: 10 30 20

    *  -  Parameter
       -  Description
       -  Example
    *  -  Action type
       -  The type of action for changing permissions. You should pick 'RestoreInheritance' for this case.
       -  RestoreInheritance
    *  -  Target
       -  The target of action: Site, List, Item. You should pick 'Item' for this case.
       -  Item
    *  -  Item ID
       -  ID of the item
       -  7
    *  -  List name
       -  Title or Url of a list
       -  Sales
    *  -  SharePoint Site Url
       -  This property defines the context of the action. The action will be executed on specified SharePoint site.
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
       -  This property defines the context of the action. The action will be executed on specified SharePoint site.
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
       -  Title of a list.
       -  Sales reports

    *  -  Template
       -  Title of the template that will be used for this list.
       -  Custom List

    *  -  Partial Url
       -  Usually, when you create a list you can't control which URL it will get. For example, if you create a document library with the name "Some document lib" it will get the following URL: Some%20doc%20lib. But in some cases more useful to choose other URL, using this field, you can specify the required value. This is an optional field you can leave it blank. By default, URL will be automatically generated.
       -  Sales_Department

    *  -  Description
       -  Description of a list.
       -  Library contains sales reports

    *  -  On Quick Nav
       -  Display this list on the Quick Launch.
       -  Yes

    *  -  SharePoint Site Url
       -  This property defines the context of the action. The action will be executed on specified SharePoint site.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/CreateListOrLibraryExample.png
   :alt: Create List or Library Example

Create Site from Template
-------------------------

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
       -  :code:`https://contoso/sites/subSite/Sales_Department`

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
       -  This property defines the context of the action. The action will be executed on specified SharePoint site.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/CreateSiteFromTemplateExample.png
   :alt: Create Site from Template Example

Set Default Site Group
----------------------------

Configure default groups for a site. It is alternative of the permsetup.aspx page in SharePoint UI.

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
       -  This property defines the context of the action. The action will be executed on specified SharePoint site.
       -  :code:`https://contoso.sharepoint.com/sites/subSite`         

.. rubric:: Example

.. image:: ../../_static/img/flow/sharepoint/SetDefaultSiteGroupExample.png
   :alt: Set Default Site Group Example