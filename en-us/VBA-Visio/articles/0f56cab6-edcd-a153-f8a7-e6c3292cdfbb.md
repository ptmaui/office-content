
# Toolbars.Item Property (Visio)

 **Last modified:** July 28, 2015

 _**Applies to:** Visio 2013 Preview_

Returns an object from a collection. The  **Item** property is the default property for all collections. Read-only.


## Syntax

 _expression_. **Item**( **_lIndex_**)

 _expression_A variable that represents a  **Toolbars** collection.


### Parameters



|**Name**|**Required/Optional**|**Data Type**|**Description**|
|:-----|:-----|:-----|:-----|
|lIndex|Required| **Long**|Contains the index of the object to retrieve.|

### Return Value

Toolbar


## Remarks


 **Note**  Starting with Visio, the Microsoft Office Fluent user interface (UI) replaces the previous system of layered menus, toolbars, and task panes. VBA objects and members that you used to customize the user interface in previous versions of Visio are still available in Visio, but they function differently.

When retrieving objects from a collection, you can omit  **Item** from the expression because it is the default property for all collections. The following statement is equivalent to the syntax example given above:


```
objRet = object(index)
```

