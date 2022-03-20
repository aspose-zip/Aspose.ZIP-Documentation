---
title: Upload archive to ASP.NET web application
type: docs
weight: 47
url: /net/upload-archive-asp-net/
keywords: c# zip library, archive decompression
description: Provides example of how to use c# zip library for archive decompression and image processing for ASP.NET web application.
---

## **Scenario**
This article provides you with an example of how to use Aspose libraries for archive decompression and image processing for ASP.NET web application. The user case: site visitor uploads zip archive with images to web application to rotating them all by a specific angle.
Rotated images will be displayed on the same web page in response.

## **Prepare ASP.NET Web Application**
Using Visual Studio compose simple ASP.NET Core Web Application with Razor Pages. 
Using NuGet Package Manager refer two packages for your project: [Aspose.Zip](https://www.nuget.org/packages/Aspose.Zip/) for decompression and [Aspose.Imaging](https://www.nuget.org/packages/Aspose.Imaging/) for image processing.
<br/>
Find page `Index.cshtml` within your Solution Explorer. Now, add a form to that page with `enctype="multipart/form-data"` attribute within `<form>` tag. It needed to transfer file to web server. Then, add two input fields - one of type `file` for uploaded archive, another of type `number` to specify rotation angle.
Here is full HTML markup for the form:
```html
<form method="post" enctype="multipart/form-data">
    <span>Images archive: </span><input type="file" name="uploadedFile" required="required" />
    <br />
    <span>Rotation angle: </span><input type="number" value="30" min="0" max="360" name="rotateDegree" required="required" />
    <br />
    <input type="submit" value="Upload" />
</form>
```
Some validation attributes have been added as well. 

## **Handling user request** 
So, the user provides the zip archive with images and submits the form. How to handle his request on the server-side? Using ASP.NET approach we need to compose an appropriate `OnPost` method to `Index.cshtml.cs` source. Within this method we extract [zip archive](https://apireference.aspose.com/zip/net/aspose.zip/archive) using [the appropriate constructor](https://apireference.aspose.com/zip/net/aspose.zip/archive/constructors/1), then rotate each image. Here is the draft of the method:
```c#
public void OnPost(IFormFile uploadedFile, int rotateDegree) {
    using (Archive archive = new Archive(uploadedFile.OpenReadStream())) {
        foreach (ArchiveEntry entry in archive.Entries) {
		   // Extract image and rotate it.
		}
    }
}
```

## **Rotate images**
We use Aspose.Imaging library to rotate an image by particular angle on the fly angle following [this instruction](https://docs.aspose.com/imaging/net/crop-rotate-and-resize-images/#rotating-an-image-on-a-specific-angle).
The snippet of rotation code:
{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "RotateImageSnippet.cs" >}}

## **Page Model and Image Rendering**
We need to store bytes of proceeded pictures within the page model to render those pictures. Add property `public List<byte[]> ImageBytes { get; private set; }` to `IndexModel`. 
We fill this list with proceeded image bytes. To show them on the web page we use [data URI](https://en.wikipedia.org/wiki/Data_URI_scheme) We need to convert image bytes to base64 string.
Here is a rendering Razor code at `Index.cshtml`
```c#
@{
if (Model.ImageBytes != null && Model.ImageBytes.Count > 0) {
        <h4>Rotated images:</h4>
        foreach (byte[] image in Model.ImageBytes) {
            <img src="data:image;base64,@Convert.ToBase64String(image)" width="150"/>
        }
    }
}
```

## **Finishing response**
So, put it all together. Each entry of the archive has been decompressed, then an image composed from these bytes, and finally rotated. <br />We do not validate user file in this sample. In real-world applications, you should verify an uploaded archive and its content. <br />Below is the final `OnPost` method.
{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ExtractAndRotateImages.cs" >}}
