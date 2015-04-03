---
title: OnClientRecurrenceActionDialogShowing
page_title: OnClientRecurrenceActionDialogShowing | UI for ASP.NET AJAX Documentation
description: OnClientRecurrenceActionDialogShowing
slug: scheduler/client-side-programming/events/onclientrecurrenceactiondialogshowing
tags: onclientrecurrenceactiondialogshowing
published: True
position: 15
---

# OnClientRecurrenceActionDialogShowing



The __OnClientRecurrenceActionDialogShowing__ client-side event is called just before the dialog appears to ask whether the change the user just started on a recurring appointment is to affect the appointment itself or the entire series.

Two parameters are passed to the event handler:

* __sender__ is the scheduler client object.

* __eventArgs__ has the following methods:

* __get_appointment()__ that returns the appointment instance.____

* __get_recurrenceAction()__returns __1__ for__edit__, __2__ for __delete__, __3__ for__resize__, and __4__ for __move__.

* __set_cancel()__ lets you permit or block the showing of the recurrence action dialog of the appointment. Calling __set_cancel(true)__ suppresses the showing of the dialog, while __set_cancel(false)__ allows the scheduler to proceed with showing the dialog.

* __set_editSeries()__- instructs the scheduler whether to edit the entire series or just the occurrence.

## Example

This example shows how to suppress the "Edit this occurrence" or "Edit Series" dialog and choose to either edit the entire series or just the occurrence:____

````ASPNET
	 
	 <script type="text/javascript">
	   function OnClientRecurrenceActionDialogShowing(sender, eventArgs)
	   {
	       eventArgs.set_cancel(true);   
	       //Edit this instance only:   
	       //eventArgs.set_editSeries(false);   
	              
	       //Edit the entire series:   
	       eventArgs.set_editSeries(true);
	   }        
	</script>
	<telerik:RadScheduler
	   ID="RadScheduler1"
	   runat="server"  
	   OnClientRecurrenceActionDialogShowing ="OnClientRecurrenceActionDialogShowing"
	   DataSourceID="AppointmentsDS" />
	
````



