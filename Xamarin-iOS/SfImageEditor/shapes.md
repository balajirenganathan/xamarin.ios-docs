---
layout : post
title : Text in Syncfusion SfImageEditor control in Xamarin.iOS
description : Learn how to add shapes, text and draw over an Image in ImageEditor for Xamarin.iOS
platform : xamarin-iOS.ios
control : ImageEditoriOSentation : ug
---

## Shapes

You can annotate any shapes over an image using the `AddShape` method. The following shapes are available in image editor:

* Circle
* Rectangle
* Arrow
* Path

### Selecting a shape type

The `ShapeType` is an enum property with values `Rectangle`, `Circle`, `Arrow`, and `Path`. You can give the desired shape type as an argument to the `AddShape` method.

{% highlight C# %}

      editor.AddShape(ShapeType.Circle);

{% endhighlight %}

## Customizing a shape with pen settings

You can customize the appearance of each shape using the `PenSettings` property:

## PenSettings

The `PenSettings` property consists of the following properties:

* [`Color`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfImageEditor.iOS.PenSettings.html#Syncfusion_SfImageEditor_iOS_PenSettings_Color): Specifies the desired stroke color to a shape.
* `FillColor`: Specifies the desired fill color to a shape.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfImageEditor.iOS.PenSettings.html#Syncfusion_SfImageEditor_iOS_PenSettings_StrokeWidth): Allows to denote the stroke width for the desired shape.
* [`Mode`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfImageEditor.iOS.PenSettings.html#Syncfusion_SfImageEditor_iOS_PenSettings_Mode): Determines whether the shape color mode is `Fill` or `Stroke`. It is an enum value.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfImageEditor.iOS.PenSettings.html#Syncfusion_SfImageEditor_iOS_PenSettings_Opacity): Denotes opacity for the desired shapes.
* [`Bounds`](https://help.syncfusion.com/cr/xamarin-ios/Syncfusion.SfImageEditor.iOS.PenSettings.html#Syncfusion_SfImageEditor_iOS_PenSettings_Bounds): Allows to set frame for the newly added shapes (rectangle and circle). You can position the shapes wherever you want on the image.In percentage, the value of the shape frame should fall between 0 and 100.

N> The `FillColor` property is applicable only if the ShapeType is `Rectangle` or `Circle`.

* To add a rectangle, circle, or arrow over an image, specify the `ShapeType` and the desired `PenSettings` as shown in the following code snippet.

{% tabs %}

{% highlight C# %}

            editor.AddShape(ShapeType.Circle, new PenSettings() { Color = UIColor.Red, Mode = Mode.Stroke, Opacity = 1f, Bounds = new Rectangle(20, 20, 35, 35) });

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/shapes.gif)

 * You can annotate any path on an image by using free hand drawing as shown in the below code,

{% tabs %}

{% highlight C# %}

      editor.AddShape(ShapeType.Path, new PenSettings() { StrokeWidth = 10 });

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/path.gif)

## Deleting a shape or text from view

You can delete the selected shape by using the `Delete` method as shown in the following code snippet.

{% tabs %}

{% highlight C# %}

    editor.Delete();

{% endhighlight %}

{% endtabs %}

N> You cannot delete the path.
