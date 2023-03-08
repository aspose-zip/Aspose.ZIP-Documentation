---
title: Converting ZIP to 7z
type: docs
weight: 66
url: /net/converting-from-zip-to-7z/
---

If you want to convert the ZIP archive to 7z read this article.

{{% alert color="primary" %}} 

Aspose.Zip now allows composing 7z archive with LZMA, LZMA2, PPMd and BZip2 compression algorithms.

{{% /alert %}} 

## **Convertation**
Aspose.ZIP API provides the [SevenZipArchive](https://reference.aspose.com/zip/net/aspose.zip.sevenzip/sevenziparchive) class to work with 7z archives.  We can extract an entry to memory without saving it into intermediate storage and pass it into the 7z archive right away.

{{% alert color="primary" %}} 

Make sure you have enough virtual memory to keep the content of all entries.

{{% /alert %}} 

### **Transfer an Entry**
The following code example demonstrates how to extract entries from the ZIP archive and immediately put them to the 7z archive. 7z entries will be compressed with [the LZMA2 method](https://reference.aspose.com/zip/net/aspose.zip.saving/sevenziplzma2compressionsettings) regardless of what algorithm they had in the source archive.
Entries that are directories are skipped, but their files are added respecting relative paths.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ConvertZipTo7z.cs" >}}