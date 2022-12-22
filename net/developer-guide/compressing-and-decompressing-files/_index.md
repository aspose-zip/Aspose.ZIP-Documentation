---
title: Zip or UnZip Files in .NET
linktitle: ZIP/UnZIP Files
type: docs
weight: 20
url: /net/compressing-and-decompressing-files/
keywords: zip c# library, c# compress file, c# uncompress zip, unzip c#, c# decompress zip 
description: This article will teach you how to programmatically compress Zip files using a variety of methods utilising C# or the.NET API and sample code. You will learn how to zip or compress one or more files, as well as how to zip files simultaneously. You will also learn how to decompress or unzip files as well.
---

## Overview

This article will teach you how to programmatically compress Zip files using a variety of methods utilising C# or the.NET API and sample code. You will learn how to zip or compress one or more files, as well as how to zip files simultaneously. You will also learn how to decompress or unzip files as well.

## Zip or Compress files in C# and Decompress or Unzip files in C#

Aspose.ZIP API lets you compress and decompress files without worrying about the underlying file structure. This article shows working with single as well as multiple file compression.
## **Compressing Files**

### **Compressing Single File**

<a name="csharp-compressing-single-file" id="csharp-compressing-single-file"><strong><em>Steps:</em> Compressing Single File in C#</strong></a>

1. Create a [file stream](https://learn.microsoft.com/en-us/dotnet/api/system.io.filestream?view=net-7.0) with the desired name of your output zip file.
2. Create file stream of the data file to be compressed.
3. Create an instance of [Archive](https://reference.aspose.com/zip/net/aspose.zip/archive/) class and pass it instance of [ArchiveEntrySettings](https://reference.aspose.com/zip/net/aspose.zip.saving/archiveentrysettings/) class.
4. Add data file created in step 2 using [Archive.CreateEntry](https://reference.aspose.com/zip/net/aspose.zip/archive/createentry/) method.
5. Zip the data file using [Archive.Save](https://reference.aspose.com/zip/net/aspose.zip/archive/save/) method and pass it the file stream created in step 1.

{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-CompressSingleFile-CompressSingleFile.cs" >}}

### **Compressing Multiple Files**

<a name="csharp-compressing-multiple-files" id="csharp-compressing-multiple-files"><strong><em>Steps:</em> Compressing Multiple Files in C#</strong></a>

1. Create a file stream with the desired name of your output zip file.
2. Create file stream of the first data file to be compressed.
3. Create file stream of the second data file to be compressed.
4. Create an instance of [Archive](https://reference.aspose.com/zip/net/aspose.zip/archive/) class.
5. Add data files created in step 2 and step 3 using [Archive.CreateEntry](https://reference.aspose.com/zip/net/aspose.zip/archive/createentry/) method.
6. Create an instance of [ArchiveSaveOptions](https://reference.aspose.com/zip/net/aspose.zip.saving/archivesaveoptions/) class.
7. Zip the data files using [Archive.Save](https://reference.aspose.com/zip/net/aspose.zip/archive/save/) method and pass it the file stream created in step 1 and instance of **ArchiveSaveOptions** created in above step.

{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-CompressMultipleFiles-CompressMultipleFiles.cs" >}}

### **Compress Files by File Info**

<a name="csharp-compress-files-by-file-info" id="csharp-compress-files-by-file-info"><strong><em>Steps:</em> Compress Files by File Info in C#</strong></a>

1. Open a file stream with **FileMode.Create** with the desired name of your output zip file.
2. Create [FileInfo](https://learn.microsoft.com/en-us/dotnet/api/system.io.fileinfo?view=net-7.0) object of your first data file to be compressed.
3. Create **FileInfo** object of your second data file to be compressed.
4. Create an instance of [Archive](https://reference.aspose.com/zip/net/aspose.zip/archive/) class.
5. Add data files created in step 2 and step 3 using [Archive.CreateEntry](https://reference.aspose.com/zip/net/aspose.zip/archive/createentry/) method.
6. Create an instance of [ArchiveSaveOptions](https://reference.aspose.com/zip/net/aspose.zip.saving/archivesaveoptions/) class.
7. Zip the data files using [Archive.Save](https://reference.aspose.com/zip/net/aspose.zip/archive/save/) method and pass it the file stream created in step 1 and instance of **ArchiveSaveOptions** created in above step.

{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-CompressFilesByFileInfo-CompressFilesByFileInfo.cs" >}}

### **Storing Files to Archives without Compression**

<a name="csharp-storing-files-to-archives-without-compression" id="csharp-storing-files-to-archives-without-compression"><strong><em>Steps:</em> Storing Files to Archives without Compression using C#</strong></a>

1. Open a file stream with **FileMode.Create** with the desired name of your output zip file.
2. Create [FileInfo](https://learn.microsoft.com/en-us/dotnet/api/system.io.fileinfo?view=net-7.0) objects for your data files to be stored in archive.
3. Create an instance of [ArchiveEntrySettings](https://reference.aspose.com/zip/net/aspose.zip.saving/archiveentrysettings/) class and pass it instance of [StoreCompressionSettings](https://reference.aspose.com/zip/net/aspose.zip.saving/storecompressionsettings/) class.
4. Create an instance of [Archive](https://reference.aspose.com/zip/net/aspose.zip/archive/) class and pass it instance of **ArchiveEntrySettings** class created in above step.
5. Add **FileInfo** objects created in step 2 using [Archive.CreateEntry](https://reference.aspose.com/zip/net/aspose.zip/archive/createentry/) method.
6. Create instance of [ArchiveSaveOptions](https://reference.aspose.com/zip/net/aspose.zip.saving/archivesaveoptions/) and set **Encoding = Encoding.ASCII**.
7. Zip the data files using [Archive.Save](https://reference.aspose.com/zip/net/aspose.zip/archive/save/) method and pass it the file stream created in step 1 and instance of **ArchiveSaveOptions** created in above step.

{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-StoreMultipleFilesWithoutCompression-StoreMultipleFilesWithoutCompression.cs" >}}

### **Using Parallelism to Compress Files**

<a name="csharp-using-parallelism-to-compress-files" id="csharp-using-parallelism-to-compress-files"><strong><em>Steps:</em> Using Parallelism to Compress Files using C#</strong></a>

1. Open a file stream with **FileMode.Create** with the desired name of your output zip file.
2. Open file streams with **FileMode.Open** and **FileAccess.Read** for your first and second data files to be compressed.
3. Create an instance of [Archive](https://reference.aspose.com/zip/net/aspose.zip/archive/) class.
4. Add data files created in step 2 using [Archive.CreateEntry](https://reference.aspose.com/zip/net/aspose.zip/archive/createentry/) method.
5. Create an instance of [ParallelOptions](https://reference.aspose.com/zip/net/aspose.zip.saving/paralleloptions/) and set **ParallelCompressInMemory = ParallelCompressionMode.Always**.
6. Create an instance of [ArchiveSaveOptions](https://reference.aspose.com/zip/net/aspose.zip.saving/archivesaveoptions/) and set its property **ParallelOptions** with the above instance.
7. Zip the data files using [Archive.Save](https://reference.aspose.com/zip/net/aspose.zip/archive/save/) method and pass it the file stream created in step 1 and instance of **ArchiveSaveOptions** created in above step.

{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-UsingParallelismToCompressFiles-UsingParallelismToCompressFiles.cs" >}}


### **LZMA Compression within ZIP Archive**

The **Lempel–Ziv–Markov chain algorithm** (**LZMA**) is an algorithm used to perform lossless data compression. LZMA uses a dictionary compression algorithm, the compressed stream is a stream of bits. LZMA compression within the ZIP archive allows ZIP containers to contain LZMA compressed entries. The following code example shows the implementation of LZMA compression using Aspose.ZIP API.

<a name="csharp-lzma-compression-within-zip-archive" id="csharp-lzma-compression-within-zip-archive"><strong><em>Steps:</em> LZMA Compression within ZIP Archive using C#</strong></a>

1. Open a file stream with **FileMode.Create** with the desired name of your output zip file.
2. Create an instance of [ArchiveEntrySettings](https://reference.aspose.com/zip/net/aspose.zip.saving/archiveentrysettings/) and pass it the instance of [LzmaCompressionSettings](https://reference.aspose.com/zip/net/aspose.zip.saving/lzmacompressionsettings/) class.
3. Create an instance of [Archive](https://reference.aspose.com/zip/net/aspose.zip/archive/) class and pass it the instance of **ArchiveEntrySettings** created above.
4. Add data files to be compressed via file paths using [Archive.CreateEntry](https://reference.aspose.com/zip/net/aspose.zip/archive/createentry/) method.
5. Zip the data files using [Archive.Save](https://reference.aspose.com/zip/net/aspose.zip/archive/save/) method.

{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-CompressionSettings-UsingLZMACompressionSettings.cs" >}}

### **BZip2 Compression within ZIP Archive**
BZip2 compression settings allow ZIP container to contain BZip2 compressed entries. The following code example shows the implementation of BZip2 compression using Aspose.ZIP API.

<a name="csharp-bzip2-compression-within-zip-archive" id="csharp-bzip2-compression-within-zip-archive"><strong><em>Steps:</em> BZip2 Compression within ZIP Archive using C#</strong></a>

1. Open a file stream with **FileMode.Create** with the desired name of your output zip file.
2. Create an instance of [ArchiveEntrySettings](https://reference.aspose.com/zip/net/aspose.zip.saving/archiveentrysettings/) and pass it the instance of [Bzip2CompressionSettings](https://reference.aspose.com/zip/net/aspose.zip.saving/bzip2compressionsettings/) class.
3. Create an instance of [Archive](https://reference.aspose.com/zip/net/aspose.zip/archive/) class and pass it the instance of **ArchiveEntrySettings** created above.
4. Add data files to be compressed via file paths using [Archive.CreateEntry](https://reference.aspose.com/zip/net/aspose.zip/archive/createentry/) method.
5. Zip the data files using [Archive.Save](https://reference.aspose.com/zip/net/aspose.zip/archive/save/) method.

{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-CompressionSettings-UsingBzip2CompressionSettings.cs" >}}

### **PPMd Compression within ZIP Archive**
PPMd compression settings allow ZIP container to contain PPMd compressed entries. The following code example demonstrated the implementation of PPMd compression using Aspose.ZIP API.

<a name="csharp-ppmd-compression-within-zip-archive" id="csharp-ppmd-compression-within-zip-archive"><strong><em>Steps:</em> PPMd Compression within ZIP Archive using C#</strong></a>

1. Open a file stream with **FileMode.Create** with the desired name of your output zip file.
2. Create an instance of [ArchiveEntrySettings](https://reference.aspose.com/zip/net/aspose.zip.saving/archiveentrysettings/) and pass it the instance of [PPMdCompressionSettings](https://reference.aspose.com/zip/net/aspose.zip.saving/ppmdcompressionsettings/) class.
3. Create an instance of [Archive](https://reference.aspose.com/zip/net/aspose.zip/archive/) class and pass it the instance of **ArchiveEntrySettings** created above.
4. Add data files to be compressed via file paths using [Archive.CreateEntry](https://reference.aspose.com/zip/net/aspose.zip/archive/createentry/) method.
5. Zip the data files using [Archive.Save](https://reference.aspose.com/zip/net/aspose.zip/archive/save/) method.

{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-CompressionSettings-UsingPPMdCompressionSettings.cs" >}}


## **Decompressing Archives**
### **Decompress Archive having Single File**
{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-DecompressSingleFile-DecompressSingleFile.cs" >}}
### **Decompress Archive having Multiple Files**
{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-DecompressMultipleFiles-DecompressMultipleFiles.cs" >}}
### **Extract Stored Archive without Compression**
{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-DecompressStoredFile-DecompressStoredFile.cs" >}}

