---
title: Compose Multi-volume Zip Archive
type: docs
weight: 10
url: /net/multi-volume-zip/
---


## **Overview**
Aspose.ZIP API lets you compose zip archive split into several files. Aspose.ZIP API provides [SaveSplit](https://reference.aspose.com/zip/net/aspose.zip/archive/savesplit/) methdod to compose such an archive. 


### **Options for split archive**

[SplitArchiveSaveOptions](https://reference.aspose.com/zip/net/aspose.zip.saving/splitarchivesaveoptions/splitarchivesaveoptions/) constructor require two parameter: file name for every piece and size of the volume. The last piece will get .zip extension, the others will have .z01, .z02, z03 ... extensions. The last volume is usually smaller then regular one.

### **Compose multi-volume archive**
The following code example demonstrates how to compose split zip archive with 65536 bytes each piece, maybe except for the last one.
File names would be part.z01, part.z02, part.z03, ..., part.zip.
{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ComposeMultiVolumeZip.cs" >}}

Multi-volume zip allows any encryption and compression method applied, same as regular zip.