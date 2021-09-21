---
title: Downloading archive in choosen format
type: docs
weight: 43
url: /net/send-in-choosen-format/
---

### **Download archive from server**
It is common feature for web applications to download a file from your web server. To reduce data size transferred over wire you may want to compress the file. It is convinient for user to choose format of the archive to download.
This sample give you some insights how to manage it.

### **Prepare Web Application**
Using Visual Studio compose ASP.NET Core Web Application. Let it be simple Web Application with Razor Pages. 
Using NuGet Package Managet include two packages for your project: [Aspose.Zip](https://www.nuget.org/packages/Aspose.Zip/) for compression and [Aspose.BarCode](https://www.nuget.org/packages/Aspose.BarCode/) for generation sample data.
<br/>
Find page `Index.cshtml` within your Solution Explorer. Now, add a form to that page with a submit button within it. It needed to initiate download request by user.
Add to that page following HTML markup:
```html
<form method="post">    
    <input type="submit" value="Download" />
</form>
```

### **List archive formats**
For this sample we choosen three of [archive formats](https://docs.aspose.com/zip/net/supported-file-formats/) Aspose.ZIP supports: ZIP, Bzip2, 7z.
Compose enumeration for those formats marking its members with [DisplayAttribute](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute)
<br/>The enumeration code will be:
```c#
public enum ArchiveFormat
{
    [Display(Name = "ZIP")]
    Zip,

    [Display(Name = "Bzip2")]
    Bz2,

    [Display(Name = "7z")]
    SevenZip
}
```
Next, you need to create a dropdown list within web form. It is pretty simple with [GetEnumSelectList](https://docs.microsoft.com/en-us/dotnet/api/microsoft.aspnetcore.mvc.viewfeatures.htmlhelper.getenumselectlist) html helper - no need to generate items with a loop. 
Just put inside your form on `Index.cshtml` following snippet:
```html
<select name="archiveFormat" asp-items="Html.GetEnumSelectList<ArchiveFormat>()"></select>
```
Run the application and look to the index page. You'll see something like that:

<select name="archiveFormat">
<option value="0">ZIP</option>
<option value="1">Bz2</option>
<option value="2">7z</option>
</select>
<input type="button" value="Download">

### **Handling user request** 
So, user specify desired archive format and hits "Download". How to handle his request on the server side? We need to compose appropriate `OnPost` method to `Index.cshtml.cs` source. Here is the draft of the method:
```c#
public FileStreamResult OnPost([FromForm] ArchiveFormat archiveFormat)
{
  switch (archiveFormat)
  {
     case ArchiveFormat.Zip:
       ...
       return new FileStreamResult(result, "application/zip") {FileDownloadName = "barcode.zip"};
     case ArchiveFormat.Bzip2:
       ...
       return new FileStreamResult(result, "application/x-bzip2") {FileDownloadName = "barcode.bmp.bz2"};
     case ArchiveFormat.SevenZip:
       ...
       return new FileStreamResult(result, "application/x-7z-compressed") {FileDownloadName = "barcode.7z"};                           
  }
}
```
So for requested archive type we must prepare corresponding archive from sample data (`result` variable) and respond with proper MIME type.

### **Generating sample data**

We use Aspose.BarCode library to generate BMP image of barcode using [this instruction](https://docs.aspose.com/barcode/net/two-dimensional-2d-barcodes/).
The snippet of data stream generation:
{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "GenerateBarcodeToCompress.cs" >}}

### **Finishing response**

Now we have a raw data stream from `GenerateBarcode` method. Compress it appropriately in every case. Below is the final `OnPost` method.
{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "HttpResponseWithChoosenArchiveKind.cs" >}}