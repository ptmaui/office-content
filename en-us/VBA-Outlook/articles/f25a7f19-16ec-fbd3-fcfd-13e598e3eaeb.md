
# TaskRequestAcceptItem.AfterWrite Event (Outlook)

 **Last modified:** July 28, 2015

Occurs after Microsoft Outlook has saved the item.

## Syntax

 _expression_. **AfterWrite**

 _expression_A variable that represents a  **TaskRequestAcceptItem** object.


## Remarks

The  **AfterWrite** event occurs after the ** [Write](005b0f33-1848-101b-2119-cb15eb51f411.md)** event. This event is not cancelable. To determine when the item is unloaded from memory, use the ** [Unload](19e89fda-1887-ad50-5db3-a1bb2ad77261.md)** event.

The  **AfterWrite** event corresponds to the Exchange Client Extensions (ECE) event **IExchExtMessageEvents::OnWriteComplete**.

Only the following members of the item object can be accessed in the  **AfterWrite** event:


-  ** [Class](d829ebf5-ec8a-7c4f-89c2-49c194339672.md)**
    
-  ** [MessageClass](817ffe01-109d-5121-96c9-d4738b1dfd91.md)**
    
-  **MAPIOBJECT**
    
The  **MAPIOBJECT** property is a hidden property in the Outlook object model. This property provides access to the underlying MAPI ** [IMessage](http://msdn.microsoft.com/en-us/library/cc842097%28office.14%29.aspx)** object, and can be invoked only via the ** [IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28VS.85%29.aspx)** interface. The property is accessible to programs written in languages such as C or C++ that support **IUnknown**.  **MAPIOBJECT** is not available through the ** [IDispatch](http://msdn.microsoft.com/en-us/library/ms221608.aspx)** interface. Development languages such as Visual Basic for Applications (VBA), Visual C#, and Visual Basic support the **IDispatch** interface and not **IUnknown**, and therefore, they cannot access  **MAPIOBJECT**. If other properties or methods of the parent item are accessed in this event, Outlook raises an error.

The object obtained from the  **MAPIOBJECT** property in this event must contain all the changes persisted by Outlook. The implementer can call the ** [SaveChanges](http://msdn.microsoft.com/en-us/library/cc842181%28office.14%29.aspx)** method on the **IMessage** object to persist changes to the underlying **IMessage** object represented by **MAPIOBJECT**, and Outlook will not revert those changes.

Implementers must release the object obtained from the  **MAPIOBJECT** property in the event before the event completes. Attempting to use that object outside the context of the event is unsupported and will lead to unpredictable behavior.


## See also


#### Concepts


 [TaskRequestAcceptItem Object](a2905f72-0a67-b07d-7f85-84fe4de17c25.md)
#### Other resources


 [TaskRequestAcceptItem Object Members](fe91c4cc-f505-11d8-0d0a-84fc4d355651.md)
