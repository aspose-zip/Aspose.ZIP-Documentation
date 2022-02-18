---
title: How To
type: docs
weight: 20
url: /net/how-to/
---

This page shows how to perform standard archive operations in C# using [Aspose.ZIP for .NET](https://www.nuget.org/packages/Aspose.Zip/).
Aspose.ZIP package can be added to you .NET project using the following NuGet command:
```csharp
PM> Install-Package Aspose.Zip
```

It can also be added directly to .NET project as a assembly reference. Aspose.ZIP library can be downloaded from our home page: https://products.aspose.com/zip/net/.
Aspose.ZIP .NET library can be used on any OS that supports .NET Core (e.g. Windows, Linux or macOS).
## **How to ZIP files in C#**
```csharp
using (var archive = new Archive())
{
   archive.CreateEntry("entry_name1.dat", "input_file1.dat");
   archive.CreateEntry("entry_name2.dat", "input_file2.dat");
   archive.Save("result_archive.zip");
}
```
Archive class constructor creates a regular ZIP archive using [Deflate compression algorithm](https://en.wikipedia.org/wiki/Deflate) and no encryption.
## **How to UnZIP files in C#**
```csharp
using (var archive = new Archive("input_archive.zip"))
{
   archive.ExtractToDirectory("\\outputDirectory");
}
```
Archive class constructor can open any ZIP archive. ArchiveLoadOptions should be provided as a second parameter in case the input archive is password-protected (See example below).
## **How to 7z files in C#**
```csharp
using (var archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMACompressionSettings())))
{
	archive.CreateEntries(CommonConstants.TestFilesFolder + "ManyFilesToCompress");
	archive.Save(CommonConstants.TestOutFolder + "7Z_ManyFilesToCompress.7z");
}
```
SevenZipArchive class constructor should be used to create a new 7z archive. The above sample uses classic LZMA compression, but other compression as well as encryption options are also available.
## **How to extract 7z files in C#**
```csharp
using (var archive = new SevenZipArchive("input_archive.7z"))
{
	archive.ExtractToDirectory("\\outputDirectory");
}
```
In the above sample SevenZipArchive class constructor opens non-protected 7z archive.
## **How to extract RAR files in C#**
```csharp
using (var archive = new RarArchive("input_archive.rar"))
{
	archive.ExtractToDirectory("\\outputDirectory");
}
```
In the above sample RarArchive class constructor opens non-protected RAR archive.
## **How to ZIP files with password in C#**
```csharp
using (var archive = new Archive(new ArchiveEntrySettings(encryptionSettings: new TraditionalEncryptionSettings("pass"))))
{
   archive.CreateEntry("entry_name1.dat", "input_file1.dat");
   archive.CreateEntry("entry_name2.dat", "input_file2.dat");
   archive.Save("result_archive.zip");
}
```
The encryptionSettings parameter is used to create a password-protected ZIP archive.
## **How to UnZIP files with password in C#**
```csharp
using (var archive = new Archive("input_archive.zip", new ArchiveLoadOptions{DecryptionPassword = "pass"}))
{
   archive.ExtractToDirectory("\\outputDirectory");
}
```
The ArchiveLoadOptions with DecryptionPassword property value is used to open a password-protected ZIP archive.
