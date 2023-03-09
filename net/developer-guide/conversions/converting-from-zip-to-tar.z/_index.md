---
title: Converting ZIP to tar.gz
type: docs
weight: 30
url: /net/converting-from-zip-to-tar.gz/
---

Tar.gz is by far the most widespread compressed archive format in the Linux world while ZIP is the most popular for Windows. If you want to convert a ZIP archive to tar.gz read this article.


## **Convertation**
Aspose.ZIP API provides the [SaveGzipped method](https://reference.aspose.com/zip/net/aspose.zip.tar.tararchive/savegzipped/methods/1) to compress a tar archive on the fly.  We can extract an entry from the ZIP archive to memory without saving it into intermediate storage and pass it into the tar archive right away.

{{% alert color="primary" %}} 
 
Make sure you have enough virtual memory to keep the content of all entries.

{{% /alert %}} 

### **Transfer an Entry**
The following code example demonstrates how to extract entries from the ZIP archive and immediately put them to the tar.gz archive. 
Entries that are directories are skipped, but their files are added respecting relative paths.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ConvertZipToTarGZ.cs" >}}