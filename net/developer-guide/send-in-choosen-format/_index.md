---
title: Download archive from ASP.NET web application
type: docs
weight: 43
url: /net/download-archive-from-asp.net-web-app/
aliases: [/net/send-in-choosen-format/]
keywords: download zip file c# asp.net, zip c# library
description: C# Zip library lets you to reduce or compress data size which is helpful for your ASP.NET or .NET web application to transfer the files on the internet quickly.
---

## **Download archive from the server**
It is a common feature for web applications to download a file from your web server. To reduce data size transferred over wire you may want to compress the file. It is convenient for a user to choose the format of the archive to download.
This sample gives you some insights on how to manage it.

## **Prepare ASP.NET Web Application**
Using Visual Studio compose ASP.NET Core Web Application. Let it be a simple Web Application with Razor Pages. 
Using NuGet Package Manager you include two packages for your project: [Aspose.Zip](https://www.nuget.org/packages/Aspose.Zip/) for compression and [Aspose.BarCode](https://www.nuget.org/packages/Aspose.BarCode/) for generation sample data.
<br/>
Find page `Index.cshtml` within your Solution Explorer. Now, add a form to that page with a submit button within it. It needed to initiate download request by user.
Add to that page following HTML markup:
```html
<form method="post">    
    <input type="submit" value="Download" />
</form>
```

## **List archive formats**
For this sample, we chosen three of [archive formats](https://docs.aspose.com/zip/net/supported-file-formats/) Aspose.ZIP supports: ZIP, Bzip2, 7z.
Compose enumeration for those formats marking its members with [DisplayAttribute](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute?view=net-5.0)
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
Next, you need to create a dropdown list within the web form. It is pretty simple with [GetEnumSelectList](https://docs.microsoft.com/en-us/dotnet/api/microsoft.aspnetcore.mvc.viewfeatures.htmlhelper.getenumselectlist?view=aspnetcore-5.0) Html helper - no need to generate items with a loop. 
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

## **Handling user request** 
So,the user specify desired archive format and hits "Download". How to handle his request on the server-side? Using ASP.NET approach we need to compose an appropriate `OnPost` method to `Index.cshtml.cs` source. Here is the draft of the method:
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
So for the requested archive type we must prepare the corresponding archive from sample data (`result` variable) and respond with `Microsoft.AspNetCore.Mvc.FileStreamResult` having the proper MIME type.

## **Generating sample data**

We use Aspose.BarCode library to generate BMP image of barcode using [this instruction](https://docs.aspose.com/barcode/net/two-dimensional-2d-barcodes/).
The snippet of data stream generation:
{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "GenerateBarcodeToCompress.cs" >}}

## **Finishing response**

Now we have a raw data stream from the `GenerateBarcode` method. Compress it appropriately in every case. Below is the final `OnPost` method.
{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "HttpResponseWithChoosenArchiveKind.cs" >}}
