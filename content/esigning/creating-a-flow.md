+++
chapter = false
date = "2018-08-27T16:22:22.000+03:00"
menuTitle = "Creating a Flow"
title = "Creating a Flow"
weight = 3

+++
Here we will learn how to create an eSinging flow in Dialing. If you do not want to send documents in PDF form to your customers and just want simple singing pages, then skip the first step and continue to [Document Setup](https://docs.dialing.se/esigning/creating-a-flow/#document-setup).

To begin, on the eSigning Flows page, click on "Create a Flow".

![](/uploads/Screenshot 2018-08-28 20.32.14.png)

Then select "Dialing eSigning"

![](/uploads/Screenshot 2018-08-28 20.34.26.png)

### Template Setup

The first step in making an eSigning flow is to setup the document template. The template. If you do not want to send documents in PDF form to your customers and just want simple singing pages, then skip the first step and continue to [Document Setup](https://docs.dialing.se/esigning/creating-a-flow/#document-setup). Otherwise, click "Create New"

![](/uploads/Screenshot 2018-08-28 20.28.36.png)

Upload your desired PDF. This will form the basis of the document template. Once you have uploaded the PDF, it should look something like this:

![](/uploads/Screenshot 2018-08-28 20.38.30.png)

Now you can drag "Merge Fields" and "Signature Fields" onto your document. When you add a merge field, you can edit the following:

* The merge field: what data should be inserted into this field
* Font name
* Font size
* Text justification
* Color

![](/uploads/Screenshot 2018-08-28 20.48.51.png)

By default, Dialing allows inserting default lead date data such as Firstname, Lastname, Zip Code, etc. However, you can also create a custom field for custom data simply by selecting "Custom Field" for the merge type.

![](/uploads/Screenshot 2018-08-28 20.47.07.png)

When you are done inserting merge field, click "Next Step" or "Save".

### Senders

All documents are sent from reports@dialing.se with the from-name masked as the name of the sender you chose. The reply-to address is set as the sender you chose as well.

There are two types of senders; **static** and **dynamic**.

**Static Sender**: All documents will be sent from this sender. Either select a single user from the list, or select “Add Sender” to create a new one. 

**Dynamic Sender**: This setting will will allow for dynamic senders. All documents will will be sent from each respective agent in Dialing. Customers can reply directly to the agent via email. The user profiles should be updated with Firstname, Lastname and Title and Mobile (if required). Select “dynamic sender” when adding a sender. 

![](/uploads/Screenshot 2018-08-28 20.51.11.png)

When you are done with this step, click "Next".

### Document Setup

In this part, we have to map data from the Dialing system to the document template.

The page will initially look something like this:

![](/uploads/Screenshot 2018-08-28 20.59.49.png)

### Flow Settings

### SMS & Email Settings