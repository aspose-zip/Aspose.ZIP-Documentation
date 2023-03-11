---
title: How to Compress or Extract Archives using C#
linktitle: How To
type: docs
weight: 20
url: /net/how-to/
description: Learn how to compress or extract archives using C#. These archives could be Zip, 7z, Rar and other such formats.
---

## Overview

This article explains how to compress or extract archives. These archives could be Zip, 7z, Rar and other such formats. It covers the following topics.

_Format_: **ZIP**
- [C# Create Zip File](#csharp-create-zip-file)
- [C# Unzip File to Folder](#csharp-unzip-file-to-folder)

_Format_: **ZIP - Password**
- [C# Create Zip file with Password](#csharp-create-zip-file-with-password)
- [C# Unzip Password Protected Zip file](#csharp-unzip-password-protected-zip-file)

_Format_: **7z**
- [C# Create 7z archives](#csharp-7z-archives)
- [C# Extract 7z file](#csharp-extract-7z-file) 

_Format_: **RAR**
- [C# Extract RAR file](#csharp-extract-rar-file)

Other topics covered by this article.
- [See Also](#see-also)

## C# Compress or Extract Archives

This page shows how to perform standard archive operations in C# using [Aspose.ZIP for .NET](https://www.nuget.org/packages/Aspose.Zip/).
Aspose.ZIP package can be added to you .NET project using the following NuGet command:
```csharp
PM> Install-Package Aspose.Zip
```

It can also be added directly to .NET project as a assembly reference. Aspose.ZIP library can be downloaded from our home page: https://products.aspose.com/zip/net/.

Aspose.ZIP .NET library can be used on any OS that supports .NET Core (e.g. Windows, Linux or macOS).

## How to ZIP files in C#

<a name="csharp-create-zip-file" id="csharp-create-zip-file"><strong>Steps: Create Zip file in C#</strong></a>

1. Create an instance of [Archive](https://reference.aspose.com/zip/net/aspose.zip/archive/) class.
2. Add files using [Archive.CreateEntry](https://reference.aspose.com/zip/net/aspose.zip/archive/createentry/) method.
3. Zip the files using [Archive.Save](https://reference.aspose.com/zip/net/aspose.zip/archive/save/) method.

```csharp
using (var archive = new Archive())
{
   archive.CreateEntry("entry_name1.dat", "input_file1.dat");
   archive.CreateEntry("entry_name2.dat", "input_file2.dat");
   archive.Save("result_archive.zip");
}
```
Archive class constructor creates a regular ZIP archive using [Deflate compression algorithm](https://en.wikipedia.org/wiki/Deflate) and no encryption.

## How to UnZIP files in C#

<a name="csharp-unzip-file-to-folder" id="csharp-unzip-file-to-folder"><strong>Steps: Unzip File to Folder in C#</strong></a>

1. Create an instance of [Archive](https://reference.aspose.com/zip/net/aspose.zip/archive/) class with your _zip file_.
2. UnZip the _zip file_ using [Archive.ExtractToDirectory](https://reference.aspose.com/zip/net/aspose.zip/archive/extracttodirectory/) method to your folder.

```csharp
using (var archive = new Archive("input_archive.zip"))
{
   archive.ExtractToDirectory("\\outputDirectory");
}
```
Archive class constructor can open any ZIP archive. ArchiveLoadOptions should be provided as a second parameter in case the input archive is password-protected (See example below).

## How to 7z files in C#

<a name="csharp-7z-archives" id="csharp-7z-archives"><strong>Steps: Create 7z archives in C#</strong></a>

1. Create an instance of [SevenZipArchive](https://reference.aspose.com/zip/net/aspose.zip.sevenzip/sevenziparchive/) class with [SevenZipLZMACompressionSettings](https://reference.aspose.com/zip/net/aspose.zip.saving/sevenziplzmacompressionsettings/).
2. Add your files by calling [SevenZipArchive.CreateEntries](https://reference.aspose.com/zip/net/aspose.zip.sevenzip/sevenziparchive/createentries/) method.
3. Save it to **7z format** by calling [SevenZipArchive.Save](https://reference.aspose.com/zip/net/aspose.zip.sevenzip/sevenziparchive/save/) method.

```csharp
using (var archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMACompressionSettings())))
{
	archive.CreateEntries(CommonConstants.TestFilesFolder + "ManyFilesToCompress");
	archive.Save(CommonConstants.TestOutFolder + "7Z_ManyFilesToCompress.7z");
}
```
SevenZipArchive class constructor should be used to create a new 7z archive. The above sample uses classic LZMA compression, but other compression as well as encryption options are also available.

## How to extract 7z files in C#

<a name="csharp-extract-7z-file" id="csharp-extract-7z-file"><strong>Steps: Extract 7z file in C#</strong></a>

1. Create an instance of [SevenZipArchive](https://reference.aspose.com/zip/net/aspose.zip.sevenzip/sevenziparchive/) class with your _7z file_.
2. Extract the contents of **7z file** by calling [SevenZipArchive.ExtractToDirectory](https://reference.aspose.com/zip/net/aspose.zip.sevenzip/sevenziparchive/extracttodirectory/) method.

```csharp
using (var archive = new SevenZipArchive("input_archive.7z"))
{
	archive.ExtractToDirectory("\\outputDirectory");
}
```
In the above sample SevenZipArchive class constructor opens non-protected 7z archive.

## How to extract RAR files in C#

<a name="csharp-extract-rar-file" id="csharp-extract-rar-file"><strong>Steps: Extract RAR file in C#</strong></a>

1. Create an instance of [RarArchive](https://reference.aspose.com/zip/net/aspose.zip.rar/rararchive/) class with your _RAR file_.
2. Extract the contents of **RAR file** by calling [RarArchive.ExtractToDirectory](https://reference.aspose.com/zip/net/aspose.zip.rar/rararchive/extracttodirectory/) method.

```csharp
using (var archive = new RarArchive("input_archive.rar"))
{
	archive.ExtractToDirectory("\\outputDirectory");
}
```
In the above sample RarArchive class constructor opens non-protected RAR archive.

## How to ZIP files with password in C#

<a name="csharp-create-zip-file-with-password" id="csharp-create-zip-file-with-password"><strong>Steps: Create Zip file with Password in C#</strong></a>

1. Create an instance of [Archive](https://reference.aspose.com/zip/net/aspose.zip/archive/) class.
2. Pass it [ArchiveEntrySettings](https://reference.aspose.com/zip/net/aspose.zip.saving/archiveentrysettings/) and set [encryptionSettings](https://reference.aspose.com/zip/net/aspose.zip.saving/archiveentrysettings/encryptionsettings/) property with the object of [TraditionalEncryptionSettings](https://reference.aspose.com/zip/net/aspose.zip.saving/traditionalencryptionsettings/) having your _password_.
3. Add as many files by calling [Archive.CreateEntry](https://reference.aspose.com/zip/net/aspose.zip/archive/createentry/) method multiple times.
4. Save it as _Zip file_ using [Archive.Save](https://reference.aspose.com/zip/net/aspose.zip/archive/save/) method.

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

<a name="csharp-unzip-password-protected-zip-file" id="csharp-unzip-password-protected-zip-file"><strong>Steps: Unzip Password Protected Zip file using C#</strong></a>

1. Create an instance of [Archive](https://reference.aspose.com/zip/net/aspose.zip/archive/) class.
2. Pass it [ArchiveLoadOptions](https://reference.aspose.com/zip/net/aspose.zip/archiveloadoptions/) object and set [DecryptionPassword](https://reference.aspose.com/zip/net/aspose.zip/archiveloadoptions/decryptionpassword/) property with your zip file _password_.
3. UnZip the _zip file_ using [Archive.ExtractToDirectory](https://reference.aspose.com/zip/net/aspose.zip/archive/extracttodirectory/) method to your folder.

```csharp
using (var archive = new Archive("input_archive.zip", new ArchiveLoadOptions{DecryptionPassword = "pass"}))
{
   archive.ExtractToDirectory("\\outputDirectory");
}
```
The ArchiveLoadOptions with DecryptionPassword property value is used to open a password-protected ZIP archive.

## See Also
This article also covers these topics. The codes are same as above.

_Format_: **ZIP**
- _Compression_
- [C# Zip File](#csharp-create-zip-file)
- [C# Zip Files](#csharp-create-zip-file)
- [C# Create Zip Archive](#csharp-create-zip-file)
- [C# Zip Multiple Files](#csharp-create-zip-file)
- [C# Add File to Zip](#csharp-create-zip-file)
- [C# Compress files to Zip](#csharp-create-zip-file)
- [C# Archives files to Zip](#csharp-create-zip-file)
- [C# How to Zip a File](#csharp-create-zip-file)
- _Extraction_
- [C# UnZip File](#csharp-unzip-file-to-folder)
- [C# UnZip Files](#csharp-unzip-file-to-folder)
- [C# Extract Zip Archive](#csharp-unzip-file-to-folder)
- [C# How to UnZip a File](#csharp-unzip-file-to-folder)
- _Compression Password Protected_
- [C# Zip File with Password](#csharp-create-zip-file-with-password)
- [C# Zip Files with Password](#csharp-create-zip-file-with-password)
- [C# Compress files to Password Protected Zip](#csharp-create-zip-file-with-password)
- [C# Archives files to Zip with Password Protection](#csharp-create-zip-file-with-password)
- _Extraction Password Protected_
- [C# UnZip Password Protected File](#csharp-unzip-password-protected-zip-file)
- [C# UnZip Password Protected Files](#csharp-unzip-password-protected-zip-file)
- [C# Extract Password Protected Zip Archive](#csharp-unzip-password-protected-zip-file)
- [C# How to UnZip a File with Password Protection](#csharp-unzip-password-protected-zip-file)

_Format_: **7z**
- _Compression_
- [C# 7z File](#csharp-7z-archives)
- [C# 7z Files](#csharp-7z-archives)
- [C# Create 7z Archive](#csharp-7z-archives)
- [C# 7z Multiple Files](#csharp-7z-archives)
- [C# Add File to 7z](#csharp-7z-archives)
- [C# Compress files to 7z](#csharp-7z-archives)
- [C# Archives files to 7z](#csharp-7z-archives)
- [C# How to 7z a File](#csharp-7z-archives)
- _Extraction_
- [C# Decompress 7z File](#csharp-extract-7z-file)
- [C# Decompress 7z Files](#csharp-extract-7z-file)
- [C# Extract 7z File](#csharp-extract-7z-file)
- [C# Extract 7z Files](#csharp-extract-7z-file)
- [C# Extract 7z Archive](#csharp-extract-7z-file)
- [C# How to Extract 7z File](#csharp-extract-7z-file)

_Format_: **RAR**
- _Extraction_
- [C# Decompress RAR File](#csharp-extract-7z-file)
- [C# Decompress RAR Files](#csharp-extract-7z-file)
- [C# Extract RAR File](#csharp-extract-7z-file)
- [C# Extract RAR Files](#csharp-extract-7z-file)
- [C# Extract RAR Archive](#csharp-extract-7z-file)
- [C# How to Extract RAR File](#csharp-extract-7z-file)
