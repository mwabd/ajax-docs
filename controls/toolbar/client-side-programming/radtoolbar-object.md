---
title: RadToolBar Object
page_title: RadToolBar Object | UI for ASP.NET AJAX Documentation
description: RadToolBar Object
slug: toolbar/client-side-programming/radtoolbar-object
tags: radtoolbar,object
published: True
position: 1
---

# RadToolBar Object



## 

The following table lists the most important methods of the __RadToolBar__ client-side object:


>caption  

| Name | Parameters | Return Type | Description |
| ------ | ------ | ------ | ------ |
| __trackChanges__ |none|none|Begins tracking changes to the toolbar items. Only changes to the items that occur between a call to __trackChanges__ and __commitChanges__ persist after a postback.|
| __commitChanges__ |none|none|Ends tracking changes to the toolbar items. Only changes to the items that occur between a call to __trackChanges__ and __commitChanges__ persist after a postback.|

>caution Client side changes are available on the server side after postback. You can use the[ClientChanges]({%slug toolbar/client-side-programming/accessing-client-changes-at-the-server%})property to access them.
>


````JavaScript
	
	        var toolBar = $find("<%=RadToolBar1.ClientID %>");
	        var dropDownButton = toolBar.get_items().getItem(0);
	        toolBar.trackChanges();
	        var dropDownChildButton = new Telerik.Web.UI.RadToolBarButton();
	        dropDownChildButton.set_text("Added on the client-side button");
	        dropDownButton.get_buttons().add(dropDownChildButton);
	        toolBar.commitChanges();
				
````




>caption  

|  __findItemByText__  | string | [RadToolBarItem]({%slug toolbar/client-side-programming/radtoolbaritem-object%}) | Returns the first item in the toolbar with the specified text. |
| ------ | ------ | ------ | ------ |
| __findItemByAttribute__ |string, string|[RadToolBarItem]({%slug toolbar/client-side-programming/radtoolbaritem-object%})|Returns the first item in the toolbar with the custom attribute specified by the first parameter set to the value specified by the second parameter.|
| __findItemByValue__ |string|[RadToolBarItem]({%slug toolbar/client-side-programming/radtoolbaritem-object%})|Returns the first item in the toolbar with the specified value.|
| __get_attributes__ |none|[Attributes]({%slug toolbar/client-side-programming/attributes-object%})|Returns the collection of custom attributes defined for the toolbar.|
| __get_items__ |none|[RadToolBarItemCollection]({%slug toolbar/client-side-programming/radtoolbaritemcollection-object%})|Returns the collection of items in the toolbar (not including items in drop-down lists).|
| __get_allItems__ |none|Array of[RadToolBarItem]({%slug toolbar/client-side-programming/radtoolbaritem-object%})|Returns an array containing all the items in the toolbar, including the items in drop-down lists. Items in drop-down lists appear immediately following their parent items.|
| __get_orientation__ |none|integer|Returns 0 if the toolbar is horizontal, 1 if it is vertical.|
| __set_orientation__ |integer|none|Sets the orientation of the toolbar.|
| __get_expandAnimation__ |none|[Animation]({%slug toolbar/client-side-programming/animation-object%})|Returns the expand animation object.|
| __get_collapseAnimation__ |none|[Animation]({%slug toolbar/client-side-programming/animation-object%})|Returns the collapse animation object.|
| __get_element__ |none|HTML element|Gets the DOM element for the toolbar.|
| __get_childListElement__ |none|HTML element|Gets the DOM element for the UL element that lists the toolbar buttons.|
| __add_<EventName>__ |eventHandler|none|Attaches an eventHandler to the event with the name <EventName>. Note that client-side event names differ from their server-side counterparts. For more information, see[Client-Side Events]({%slug toolbar/client-side-programming/events%}).|
| __remove_<EventName>__ |eventHandler|Boolean|Detaches an eventHandler from the event with the name <EventName>.Returns "True" if the eventHandler is found and detached, false otherwise.Note that client-side event names differ from their server-side counterparts. For more information, see[Client-Side Events]({%slug toolbar/client-side-programming/events%}).|