
# ScaleEffect.ByX Property (PowerPoint)

 **Last modified:** July 28, 2015

 **In this article**
 [Syntax](#sectionSection0)
 [Remarks](#sectionSection1)
 [Example](#sectionSection2)


Sets or returns a  **Single** that represents scaling or moving an object horizontally by a specified percentage of the screen width, depending on whether it used in conjunction with a ** [ScaleEffect](cb7c296e-a9ea-4ed6-87e0-a5d603da4f9f.md)**or  ** [MotionEffect](77a34f68-8806-22b8-149f-c28e0457e7e9.md)**object, respectively. For example, a value of 50 for a motion effect means to move the object half the screen width to the right. Read/write.


## Syntax
<a name="sectionSection0"> </a>

 _expression_. **ByX**

 _expression_A variable that represents a  **ScaleEffect** object.


### Return Value

Single


## Remarks
<a name="sectionSection1"> </a>

Negative numbers move the object horizontally to the left. Floating point numbers (for example, 55.5) are allowed.

To scale or move an object vertically, use the  **ByY**property.

If both the  **ByX** and **ByY** properties are set, then the object is scaled or moves both horizontally and vertically.

Do not confuse this property with the  **By**property of the  ** [ColorEffect](c21ca9cd-3aaa-35f7-3d0e-89ca155322f2.md)**,  ** [RotationEffect](d0fc5520-dbbd-a44a-b811-51fd299c4587.md)**, or  ** [PropertyEffect](8fa129ac-f222-a01c-4545-0097b1164aee.md)**objects, which is used to set colors, rotations, or other properties of an animation behavior, respectively.


## Example
<a name="sectionSection2"> </a>

The following example adds an animation path; then sets the horizontal and vertical movement of the shape.


```
Sub AddMotionPath()



    Dim effCustom As Effect

    Dim animBehavior As AnimationBehavior

    Dim shpRectangle As Shape



    'Adds rectangle and sets effect and animation

    Set shpRectangle = ActivePresentation.Slides(1).Shapes _

        .AddShape(Type:=msoShapeRectangle, Left:=300, _

        Top:=300, Width:=300, Height:=150)

    Set effCustom = ActivePresentation.Slides(1).TimeLine _

        .MainSequence.AddEffect(Shape:=shpRectangle, _

         effectId:=msoAnimEffectCustom)

    Set animBehavior = effCustom.Behaviors.Add(msoAnimTypeMotion)



    'Specifies animation motion

    With animBehavior.MotionEffect

        .ByX = 50

        .ByY = 50

    End With



End Sub
```


## See also
<a name="sectionSection2"> </a>


#### Concepts


 [ScaleEffect Object](cb7c296e-a9ea-4ed6-87e0-a5d603da4f9f.md)
#### Other resources


 [ScaleEffect Object Members](d8e13c36-490f-9402-cdf3-cb5ad344ff80.md)
