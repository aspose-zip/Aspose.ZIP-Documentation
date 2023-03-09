---
title: Converting RAR to ZIP
type: docs
weight: 10
url: /net/converting-from-rar-to-zip/
---

If you want to convert RAR archive to ZIP read this article.

## **Convertation**
Aspose.ZIP API provides [RarArchive](https://reference.aspose.com/zip/net/aspose.zip.rar/rararchive) class to extract RAR archives. We can extract an entry to memory without saving it into intermediate storage and pass into ZIP archive right away.

{{% alert color="primary" %}} 

Make sure you have enough virtual memory to keep content of all entries.

{{% /alert %}} 

### **Transfer an Entry**
The following code example demonstrates how to extract entries from RAR archive and immediately put it to ZIP archive.
Entries that are directories added with appended slash to specify their kind.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ConvertRarToZip.cs" >}}