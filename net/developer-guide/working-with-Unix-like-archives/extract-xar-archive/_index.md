---
title: XAR extraction
type: docs
weight: 78
url: /net/xar-extraction/
keywords: xar extraction, xar archive library
description: C# library allows you to extract XAR archive.
---


## **Overview**
[Xar](https://docs.fileformat.com/compression/xar/) is popular Mac OS archiving format. You can extract such an archive with Aspose.Zip similarly as other archives. 

{{% alert color="primary" %}} 

Aspose.Zip can extract XAR entries compressed with gzip, bzip2, lzma.

{{% /alert %}} 

### **Extract an Entry**
Following sample extracts entries of the archive one by one.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ExtractXarFileEntries.cs" >}}

### **Extract Whole Arcive**
Following sample extracts all content to the directory.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ExtractXarToDirectory.cs" >}}