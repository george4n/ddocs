+++
chapter = false
date = "2018-08-27T16:22:22.000+03:00"
menuTitle = "- Creating a Flow"
title = "Creating a Flow"
weight = 3

+++
Here we will learn how to create an eSinging flow in GetAccept. To begin, on the eSigning Flows page, click on "Create a Flow".

![](/uploads/Screenshot 2018-08-29 15.03.22.png)

Then select "GetAccept"

![](/uploads/Screenshot 2018-08-28 20.34.26.png)

You will need to create an **authenticated entity** in GetAccept. Input your username and password, you will be prompted to select which entity to connect to. Then assign this authenticated entity to a customer and campaign in Dialing. When you are done, press "Continue" on the entity you created.

![](/uploads/Screenshot 2018-08-29 14.39.02.png)

### Template Setup

The first step in making an eSigning flow is to setup the document template. The specifics about creation of templates in GetAccept will not be covered in this documentation. All that you should be aware of is that when making fields in GetAccept, they must be set as **custom fields** in order to be read by Dialing.

![](/uploads/Screenshot 2018-08-29 12.26.09.png)

### Senders

All documents are sent from reply-to-sender@getaccept.com with the from-name masked as the name of the sender you chose. The reply-to address is set as the sender you chose as well.

There are two types of senders; **static** and **dynamic**.

**Static Sender**: All documents will be sent from this sender. Either select a single user from the list, or select “Add Sender” to create a new one.

**Dynamic Sender**: This setting will will allow for dynamic senders. All documents will will be sent from each respective agent in Dialing. Customers can reply directly to the agent via email. The user profiles should be updated with Firstname, Lastname and Title and Mobile (if required). Select “dynamic sender” when adding a sender.

{{% notice warning %}}

Please be aware that users should not be created in GetAccept, Dialing will create those users when required.

{{% /notice %}}

![](/uploads/Screenshot 2018-08-29 14.40.32.png)

When you are done with this step, click "Next".

### Document Setup

In this part, we have to map data from the Dialing system to the document template in GetAccept.

The page will initially look something like this:

![](/uploads/Screenshot 2018-08-29 14.54.43.png)

Select which template to load.

The first field "Document Name" is a standard field, and will be present in all flows. We can also see a field for "Firstname", "Lastname" and "our-custom-field" in the example above.

For each field, we can select a Data Type and Data Value to insert into the field. They will be inserted as a **shortcode**. You can use shortcodes to construct numbers and strings. You can also apply functions to these shortcodes. It sounds complicating, but really, its not :)

You can insert system variables into your fields:

Ringcard Fields, begin with "rc"

    {{rc.firstname}}

Order Form Fields, begin with "of"

    {{of.product}}

These variables must always be enclosed inside double curly braces like so:

    {{xx.variableName}}

Functions - There are a number of functions you can execute against variables. Functions are always wrapped in double brackets like so:

    [[ 1 + 2 ]]

These shortcodes can be made up of the following:

    {{rc.Personnummer/Organisationsnummer}}-[YYYY-MM-DD]-Document

Note how we did a custom calculation for "our-custom-field"

    [[{{of.test }}*1.20]]

For the document name, we also inserted today's date:

    {{rc.Personal no}} - [YYYY-MM-DD] - Agreement

When you are done with this step, click "Next".

### Flow Settings

In this part, you need to give the flow a name, set the expire time and reminder time. You also have to select your delivery method.

![](/uploads/Screenshot 2018-08-29 14.59.16.png)

For expire time, you can set it as amount of days or the day of the week, ie, all documents should expire on a Sunday OR documents should expire after 7 days.

For delivery methods, you can select:

* Email only
* Both SMS & Email

### Triggers

A trigger defines when a document should be sent, and what outcome should change when the customer interacts with the document.

![](/uploads/Screenshot 2018-08-29 15.00.38.png)

##### eSigning Triggers

Many call centers may use different suboutcomes for orders pending approval, and orders approved. For the sending trigger, you can set it send if the outcome is **"Yes" - "Pending Approval"**. When the document gets signed, the outcome will change to **"Yes" - "Order Approved"**.

In the example, we will send a document when the outcome is **"Yes thank you" - "Yes 1"**. When the document gets signed, we will change the outcome to **"Yes thank you" - "Yes 2".**

If a document gets rejected or expires, you can set it to **"Failure"** or even a **"Personal Callback"**.

When you are done, press "Finish".

If you go back to the eSigning Flow page, you should see your flow at the top of the list. It is active by default.