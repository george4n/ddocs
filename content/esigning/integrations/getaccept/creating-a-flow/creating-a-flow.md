+++
chapter = false
date = "2018-08-27T16:22:22.000+03:00"
draft = true
menuTitle = "- Creating a Flow"
title = "Creating a Flow"
weight = 3

+++
Here we will learn how to create an eSinging flow in GetAccept. To begin, on the eSigning Flows page, click on "Create a Flow".

![](/uploads/Screenshot 2018-08-28 20.32.14.png)

Then select "GetAccept"

![](/uploads/Screenshot 2018-08-28 20.34.26.png)

You will need to create an **authenticated entity** in GetAccept. Input your username and password, you will be prompted to select which entity to connect to. Then assign this authenticated entity to a customer and campaign in Dialing.

![](/uploads/Screenshot 2018-08-29 12.10.55.png)

### Template Setup

The first step in making an eSigning flow is to setup the document template. The specifics about creation of templates in GetAccept will not be covered in this documentation. All that you should be aware of is that when making fields in GetAccept, they must be set as **custom fields** in order to be read by Dialing.

![](/uploads/Screenshot 2018-08-29 12.26.09.png)

### Senders

All documents are sent from reply-to-sender@getaccept.com with the from-name masked as the name of the sender you chose. The reply-to address is set as the sender you chose as well.

There are two types of senders; **static** and **dynamic**.

**Static Sender**: All documents will be sent from this sender. Either select a single user from the list, or select “Add Sender” to create a new one.

**Dynamic Sender**: This setting will will allow for dynamic senders. All documents will will be sent from each respective agent in Dialing. Customers can reply directly to the agent via email. The user profiles should be updated with Firstname, Lastname and Title and Mobile (if required). Select “dynamic sender” when adding a sender. 

{{% notice note %}}

Please be aware that users should not be created in GetAccept, Dialing will create those users when required. 

{{% /notice %}}

![](/uploads/Screenshot 2018-08-28 20.51.11.png)

When you are done with this step, click "Next".

### Document Setup

### Flow Settings

### SMS & Email Settings