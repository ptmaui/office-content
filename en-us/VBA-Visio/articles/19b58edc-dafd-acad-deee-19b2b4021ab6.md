
# Application.QueryCancelQuit Event (Visio)

 **Last modified:** July 28, 2015

 _**Applies to:** Visio 2013 Preview_

Occurs before the application terminates in response to a user action in the interface. If any event handler returns  **True**, the operation is canceled.


## Syntax

Private Sub  _expression__**QueryCancelQuit**( **_ByVal app As [IVAPPLICATION]_**)

 _expression_A variable that represents an  **Application** object.


### Parameters



|**Name**|**Required/Optional**|**Data Type**|**Description**|
|:-----|:-----|:-----|:-----|
|app|Required| **[IVAPPLICATION]**|The instance of Microsoft Visio that is going to terminate.|

## Remarks

A Visio instance fires  **QueryCancelQuit** after the user has directed the instance to terminate.




- If any event handler returns  **True** (cancel), the instance fires **QuitCanceled** and does not terminate.
    
- If all handlers return  **False** (don't cancel), the instance fires **BeforeQuit** and then terminates.
    


While a Visio instance is firing a query or cancel event, it responds to inquiries from client code but refuses to perform operations. Client code can show forms or message boxes while responding to a query or cancel event.

If you're using Microsoft Visual Basic or Visual Basic for Applications (VBA), the syntax in this topic describes a common, efficient way to handle events.

If you want to create your own  **Event** objects, use the **Add** or **AddAdvise** method. To create an **Event** object that runs an add-on, use the **Add** method as it applies to the **EventList** collection. To create an **Event** object that receives notification, use the **AddAdvise** method. To find an event code for the event you want to create, see [Event codes](de8f5c7a-421d-ebcf-22b6-4310a202ef64.md).

