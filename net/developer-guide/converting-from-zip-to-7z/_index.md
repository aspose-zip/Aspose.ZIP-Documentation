---
title: Converting ZIP to 7z
type: docs
weight: 66
url: /net/converting-from-zip-to-7z/
---

If you want to convert ZIP archive to 7z read this article.

{{% alert color="primary" %}} 

Aspose.Zip now allows to compose 7z archive with LZMA, LZMA2 and BZip2 compression algorithms.

{{% /alert %}} 

## **Convertation**
Aspose.ZIP API provides [SevenZipArchive](https://apireference.aspose.com/zip/net/aspose.zip.sevenzip/sevenziparchive) class to work with 7z archives.  We can extract an entry to memory without saving it into intermediate storage and pass into 7z archive right away.

{{% alert color="primary" %}} 

Make sure you have enough virtual memory to keep content of all entries.

{{% /alert %}} 

### **Transfer an Entry**
The following code example demonstrates how to extract entries from ZIP archive and immediately put it to 7z archive. 7z entreis will be compressed with [LZMA2 method](https://apireference.aspose.com/zip/net/aspose.zip.saving/sevenziplzma2compressionsettings) regardless of what algorithm them had in the source archive.
Entries that are directories are skipped, but their files are added respecting relative paths.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ConvertZipTo7z.cs" >}}