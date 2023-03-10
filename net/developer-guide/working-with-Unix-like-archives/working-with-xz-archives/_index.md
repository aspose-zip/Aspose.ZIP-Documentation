---
title: Working with XZ Archives in C#
linktitle: Working with XZ Archives
type: docs
weight: 77
url: /net/working-with-xz-archives/
keywords: xz c# api, c# xz library
description: C# xz API lets you work with creating and managing xz archives in your applications without the need of any other 3rd party applications and provides various methods to perform operations on archives.
---


## **Overview**
[XZ archive](https://tukaani.org/xz/format.html) is common in Linux. It uses LZMA2 algorithm. Aspose.ZIP for .NET API lets work with creating and managing XZ archives in your applications without the need of any other 3rd party applications. Aspose.ZIP API provides [XzArchive](https://reference.aspose.com/zip/net/aspose.zip.xz/xzarchive/) class to work with such archives. This class provides basic methods to perform operations on archives.


## **Compress A File**
The following code example shows how to compress a file using XzArchive instance.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ComposeXzArchive.cs" >}}


## **Open XZ Archive**
The following simple code example shows how to open a XZ archive.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ExtractXzArchive.cs" >}}

## **Choosing Checksum Calculation Method**
XZ archive allows to choose data integrity calculation from CRC32, CRC64, SHA-256 or omit it.
Aspose.Zip implements 3 of such methods: `XzCheckType.None`, `XzCheckType.Crc32`, `XzCheckType.Crc64`. Default is CRC32.