---
title: Working with Z Archives in C#
linktitle: Working with Z Archives
type: docs
weight: 76
url: /net/working-with-unix-z-archives/
keywords: z c# api, c# z/compress library
description: C# z API lets you work with creating and managing unix Z archives in your applications without the need of any other 3rd party applications and provides various methods to perform operations on archives.
---


## **Overview**
[Compress](https://en.wikipedia.org/wiki/Compress) is a Unix shell utility producing an archive with .Z extension. Aspose.ZIP for .NET API lets work with creating and managing Z archives in your applications without the need of any other 3rd party applications. Aspose.ZIP API provides [ZArchive](https://reference.aspose.com/zip/net/aspose.zip.z/zarchive/) class to work with such archives. This class provides basic methods to perform operations on archives.

{{% alert color="primary" %}} 

This utility iplements LZC algorithm which is modification of LZW algorithm.
{{% /alert %}} 


## **Compress A File**
The following code example shows how to compress a file using ZArchive instance.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ComposeZCompress.cs" >}}


## **Open Z Archive**
The following code example shows how to open a Z archive.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ExtractZCompress.cs" >}}
## **Save to Stream**
The following code example shows how to save to stream.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ComposeZCompressToStream.cs" >}}
