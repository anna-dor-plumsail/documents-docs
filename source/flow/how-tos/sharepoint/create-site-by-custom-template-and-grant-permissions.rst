Create site by custom template and grant permissions
======================================================

This article will show how to use Microsoft Flow to create a new site by the custom template and then grant permissions to this site for specific SharePoint group. As an example I configured the flow for SharePoint list to automatically create new sites.

In this case, I'm using *‘Create Site from Template’* and *‘Change Permissions’* actions from Plumasail SP connector, which is a part of `Plumsail Actions <https://plumsail.com/actions>`_.

So, before starting, ensure that you `added Plumsail SP connector to Microsoft Flow <../../../getting-started/use-from-flow.html>`_.

This example will show a simple case of project management system when an administrator can create a new list item for a project in SharePoint list, specify project participants and URL for a new project workspace. Once it is done, the flow has to create the project workspace (SharePoint site). It will automatically break permissions inheritance for the new site and include the site to the top navigation. Then you can grant permissions to sensitive information in the project for any SharePoint group. To simplify this use case I have one Sharepoint group and contributors role only.

This article is divided to stages:

- :ref:`createSharePointList`
- :ref:`saveSiteAsTemplate`
- :ref:`configureMicrosoftFlow`

.. _createSharePointList:

Create SharePoint list
----------------------
At this stage it was created the new SharePoint list *‘Projects’*  with following structure:

* Title – Text field. The title of a project.
* Site partial URL – The text field. The partial URL for a new project site (for example, *‘project1′* can be used to create subsite with URL like this: :code:`http://yourdomain/projects/project1`)

This is how the new form looks like:
 
.. image:: ../../../_static/img/flow/how-tos/sharepoint/create-site-list-new-item.png
   :alt: Create site

As I mentioned above I simplified this example to keep it clear. You can add more fields to this list to work with your projects. For example, you can add field *‘Project Template’*  and use it for specifying the name of the template to create new SharePoint site.

.. _saveSiteAsTemplate:

Save site as template
---------------------
For demo purposes was customized SharePoint team site to use it as a project workspace. I added some web parts to the main page and changed style of the site. You can see my project site below:
 
.. image:: ../../../_static/img/flow/how-tos/sharepoint/create-site-template.png
   :alt: Site template   
 
Then it was saved as template. To save a site as template navigate to *‘Site Settings’* and click at *‘Save site as template’*. You can read official `Microsoft documentation <http://msdn.microsoft.com/en-us/library/office/jj938033%28v=office.15%29.aspx#bkmk_SaveTemplate>`_ for more information.

The template is called *‘ProjectSite’*. I will use this template in the flow, you will see it below in the description of the flow.

.. _configureMicrosoftFlow:

Configure Microsoft Flow
-----------------------------
At this stage was created a flow and configured it to start on list item creation for *‘Projects’* list. Thus, new SharePoint sites will be created automatically after creation of a list item.

You can find more information about specific parameters of the flow actions in `the documentation <https://plumsail.com/docs/actions/v1.x>`_ .

The complete flow is below:

.. image:: ../../../_static/img/flow/how-tos/sharepoint/create-site-from-template-flow.png
   :alt: Microsoft Flow

As you can see I used *‘When an item is created’* trigger from *‘SharePoint’* connector and two actions: *‘Create Site from Template’* and *‘Change Permissions’*

When an item is created
~~~~~~~~~~~~~~~~~~~~~~~~~~~

At this step I specify values for *‘Site Address’* and *‘List Name’* fields to bind the flow to the *‘Project‘* list.

Create Site from Template
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

In this flow action I used *‘Title’* field of current list item as the title for SharePoint site.

It was used *‘Site partial URL’* field of current list item as the partial URL for the new site (*‘Leaf URL’* field). As I mentioned in the beginning of this article *‘Site partial URL’*  field is the partial URL for the new site. For example, if current site has URL :code:`http://yourdomain/projects`  and you specified *‘Site partial URL’*  as *‘project1′* , then the new site will have such URL: code:`http://yourdomain/projects/project1`.

Specified the URL of the site as the value for *‘SharePoint Site URL‘* field.

I used the name of created earlier site template *‘ProjectSite’* as the site template name.

Additionally in the setting of the flow action was switched *‘Inherit Permissions’* property to *‘No’* . It means that a new site will not inherit permissions from a parent site.

Also, pay attention to the property *‘On top navigation‘*, it has *‘Yes’*  value by default. It allows to add new sites to the top navigation of the parent site automatically. Thus, you will be able to start working with project site without adding it to navigation manually.

Change Permissions
~~~~~~~~~~~~~~~~~~~~~~

In the *‘Change permissions’* action, I firstly choose *‘Grant’* value for *‘Action type’* field and *‘Site’* value for *‘Target’* field.

Then others fields of the form generated automatically based on my parameters.

And after that, I specified *‘Role type‘* field as *‘Contribute’* and the name of the existing Sharepoint group *‘Project Contributors’* as the value of *‘User or group’* field. Also, I specified the URL of the site as the value for *‘SharePoint Site URL‘* field.

That is all, the flow is configured.

.. hint:: You are may using actions for setting variables with your site URL and the name of the list and then use it in Plumsail Actions in *‘SharePoint Site URL‘* and *‘List Name‘* fields for more convenient using of actions.