---
title: How To
type: docs
weight: 20
url: /net/how-to/
---

This page shows how to perform standard archive operations in C# using [Aspose.ZIP for .NET](https://www.nuget.org/packages/Aspose.Zip/).
### **How to ZIP files in C#**
```csharp
using (var archive = new Archive())
{
   archive.CreateEntry("entry_name1.dat", "input_file1.dat");
   archive.CreateEntry("entry_name2.dat", "input_file2.dat");
   archive.Save("result_archive.zip");
}
```
### **How to UnZIP files in C#**
```csharp
using (var archive = new Archive("input_archive.zip"))
{
   archive.ExtractToDirectory("\\outputDirectory");
}
```
### **How to 7z files in C#**
```csharp
using (var archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMACompressionSettings())))
{
	archive.CreateEntries(CommonConstants.TestFilesFolder + "ManyFilesToCompress");
	archive.Save(CommonConstants.TestOutFolder + "7Z_ManyFilesToCompress.7z");
}
```
### **How to extract 7z files in C#**
```csharp
using (var archive = new SevenZipArchive("input_archive.7z"))
{
	archive.ExtractToDirectory("\\outputDirectory");
}
```
### **How to extract RAR files in C#**
```csharp
using (var archive = new RarArchive("input_archive.rar"))
{
	archive.ExtractToDirectory("\\outputDirectory");
}
```
### **How to ZIP files with password in C#**
```csharp
using (var archive = new Archive(new ArchiveEntrySettings(encryptionSettings: new TraditionalEncryptionSettings("pass"))))
{
   archive.CreateEntry("entry_name1.dat", "input_file1.dat");
   archive.CreateEntry("entry_name2.dat", "input_file2.dat");
   archive.Save("result_archive.zip");
}
```
### **How to UnZIP files with password in C#**
```csharp
using (var archive = new Archive("input_archive.zip", new ArchiveLoadOptions{DecryptionPassword = "pass"}))
{
   archive.ExtractToDirectory("\\outputDirectory");
}
```