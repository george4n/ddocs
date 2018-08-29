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

Select which template to load, if you have already done this in the first step, then move onto selecting which campaign this flow will apply to.

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

When you are done filling in the fields, it should look something like this:

![](/uploads/Screenshot 2018-08-29 10.21.27.png)

Not how we did a custom calculation for "our-custom-field"

    [[{{of.test }}*1.20]]

For the document name, we also inserted today's date:

    {{rc.Personal no}} - [YYYY-MM-DD] - Agreement

When you are done with this step, click "Next".

### Flow Settings

In this part, you need to give the flow a name, set the expire time and reminder time. You also have to select your delivery method.

![](/uploads/Screenshot 2018-08-29 10.23.25.png)

For expire time, you can set it as amount of days or the day of the week, ie, all documents should expire on a Sunday.

For delivery methods, you can select:

* SMS only
* Email only
* Both SMS & Email
* Prefer SMS - If no mobile number is found, an email will be sent
* Prefer Email - If no email is found, an SMS will be sent

### Triggers

A trigger defines when a document should be sent, and what outcome should change when the customer interacts with the document.

![](/uploads/Screenshot 2018-08-29 10.27.29.png)

##### eSigning Triggers

Many call centers may use different suboutcomes for orders pending approval, and orders approved. For the sending trigger, you can set it send if the outcome is **"Yes" - "Pending Approval"**. When the document gets signed, the outcome will change to **"Yes" - "Order Approved"**.

In the example, we will send a document when the outcome is **"Yes thank you" - "Ja 1"**. When the document gets signed, we will change the outcome to **"Yes thank you" - "Ja 2".**

If a document gets rejected or expires, you can set it to **"Failure"** or even a **"Personal Callback"**.

### SMS & Email Settings

This is the final step in creating a flow.