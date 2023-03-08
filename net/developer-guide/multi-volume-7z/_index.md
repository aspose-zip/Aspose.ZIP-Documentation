---
title: Compose Multi-volume 7z Archive
type: docs
weight: 79
url: /net/multi-volume-7z/
keywords: multi volume 7z c#, split 7z c#
description: Compose multi-volume 7z archive with .net library
---


## **Overview**
Aspose.ZIP API lets you compose 7z archive split into several files (volumes). Aspose.ZIP API provides [SaveSplit](https://reference.aspose.com/zip/net/aspose.zip.sevenzip/sevenziparchive/savesplit/) methdod to compose such an archive. 


### **Options for split archive**

[SplitSevenZipArchiveSaveOptions](https://reference.aspose.com/zip/net/aspose.zip.saving/splitsevenziparchivesaveoptions/) constructor require two parameter: file name for every piece and size of the volume. Pieces will have .7z.001, .7z.002, .7z.003 ... extensions. The last volume is usually smaller then regular one.

### **Compose multi-volue archive**
The following code example demonstrates how to compose split 7z archive with 65536 bytes each piece, maybe except for the last one.
File names would be part.7z.001, part.7z.002, part.7z.003, ...

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ComposeMultiVolume7Z.cs" >}}

Multi-volume 7z allows encryption and any compression method applied, same as regular 7z archive.