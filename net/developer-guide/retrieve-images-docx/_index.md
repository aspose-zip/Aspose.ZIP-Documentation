---
title: Retrieve images from *.docx Word document
type: docs
weight: 90
url: /net/retrieve-images-from-docx/
---

### **Scenario**
This article teaches you how to compose an ASP.NET web application for fetching all the images from Microsoft Docx format document.

### **Prepare ASP.NET Web Application**
Using Visual Studio compose simple ASP.NET Core Web Application with Razor Pages. 
Using NuGet Package Manager refer two packages for your project: [Aspose.Zip](https://www.nuget.org/packages/Aspose.Zip/) for decompression and [Aspose.Imaging](https://www.nuget.org/packages/Aspose.Imaging/) for image verification.
<br/>
Find page `Index.cshtml` within your Solution Explorer. Now, add a form to that page with `enctype="multipart/form-data"` attribute within `<form>` tag. It needed to transfer Word document to web server. Then, add a input field of type `file` for uploaded docx file.
Here is full HTML markup for the form:
```html
<form method="post" enctype="multipart/form-data">
    <<span>Microsoft *.docx document: </span><input type="file" name="uploadedFile" required="required" accept=".docx" />   
    <br />
    <input type="submit" value="Upload" />
</form>
```
`Accept` attributes have been added for user convenience. 

### **Docx Structure** 
[Docx documet](https://docs.fileformat.com/word-processing/docx/) is a zip archive itself. If it has any embedded images they are located within 'word/media' folder after extraction. So, the user provides the docx file and submits the form. On the server side we need to compose an appropriate `OnPost` method to `Index.cshtml.cs` source. Within this method we extract [zip archive](https://reference.aspose.com/zip/net/aspose.zip/archive) using [the appropriate constructor](https://reference.aspose.com/zip/net/aspose.zip/archive/constructors/1).  Here is the draft of the method:
```c#
public void OnPost(IFormFile uploadedFile) {
    using (Archive archive = new Archive(uploadedFile.OpenReadStream())) {
        using (Archive archive = new Archive(uploadedFile.OpenReadStream()))
        {
            foreach (var entry in archive.Entries.Where(e => e.Name.StartsWith(@"word/media", StringComparison.InvariantCultureIgnoreCase)))
			{
			 ...
			}
		}	
    }
}
```

### **Page Model and Image Rendering**
After extraction we need to verify that extracted entry is actually an image. For this purpose we can use [Image.CanLoad](https://reference.aspose.com/imaging/net/aspose.imaging/image/methods/canload) method. If it approves the valid image, we need to store bytes of it within the page model to render that picture. Add property `public List<byte[]> ImageBytes { get; private set; }` to `IndexModel`. 
We fill this list with extracted image bytes. To show them on the web page we use [data URI](https://en.wikipedia.org/wiki/Data_URI_scheme) with convertion image bytes to base64 string.
Here is a rendering Razor code at `Index.cshtml`
```c#
@{
if (Model.ImageBytes != null && Model.ImageBytes.Count > 0) {
        <h4>Images within document:</h4>
        foreach (byte[] image in Model.ImageBytes) {
            <img src="data:image;base64,@Convert.ToBase64String(image)"/>
        }
    }
}
```

### **Finishing response**
So, put it all together. Each entry of the archive has been decompressed, then an image composed from these bytes. <br />We do not validate user file in this sample. In real-world applications, you should verify an uploaded archive and its content. <br />Below is the final `OnPost` method.
{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ExtractImagesFromDocx.cs" >}}