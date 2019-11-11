How to insert images into DOCX document
##################################################################


In this article I'm going to show how to insert images into DOCX document.

`Create DOCX from template connector`_  supports `Picture formatter`_: it resolves URL or base64 string and converts it to an image.
If you need to resize the picture you can specify the size

{{value}:picture(100,100)}

Let's check out a couple of examples.

Picture formatter and base64 string
##################################################################
As it's said you can insert the image using base64 string.

- .. code-block:: json

            {                     
                "value": "iVBORw0KGgoAAAANSUhEUgAAAIAAAAA9CAYAAABlamFgAA"
            }  

A common situation is getting photos from the camera in PowerApps or pen input for signatures, converting it to base64 and then inserting into a docx template.
In general, you can insert any image if you can get its base64 code in Micrisoft Flow or even using some third-party services.


Picture formatter and URL
##################################################################

The formatter also accepts URLs, Plumsail Documents support anonymous authentication only. 
To use a link to a picture stored in SharePoint, please, 
create a guest link and replace guestacces.aspx string with download.aspx one. 
Your link should look something like this: https://yourDomain.sharepoint.com/_layouts/15/download.aspx?docid=DocID&authkey=AuthKey

- .. code-block:: json

            {                     
                "value": "https://picturesite.com/pics/picture.png"
            }  

|signed_contract|

Now you have an idea how to automate your workflow with the help of Plumsail Documents connector for Microsoft Flow. Find more simple solutions on creating Flows for your operational processes amoung our `Flow examples`_. If you are new to Plumsail Documents, feel free to `sign up for an account`_ and get a 30-Day free trial. It’s easy `to get started`_. 




.. |sign_now_flow| image:: /_static/img/flow/how-tos/sign_now_flow.png
.. |get_content| image:: /_static/img/flow/how-tos/get_content_signnow.png
.. |docx_from_template| image:: /_static/img/flow/how-tos/docx_from_template_sn.png
.. |create_file| image:: /_static/img/flow/how-tos/create_file_sn.png
.. |upload_document| image:: /_static/img/flow/how-tos/upload_doc_sn.png
.. |invite_to_sign| image:: /_static/img/flow/how-tos/invite_to_sign.png
.. |signed_contract| image:: /_static/img/flow/how-tos/notification_sn.png





.. _Create DOCX from template connector: https://plumsail.com/docs/documents/v1.x/flow/actions/document-processing.html#create-docx-document-from-template
.. _Picture formatter: https://docs.microsoft.com/en-us/connectors/signnow/
