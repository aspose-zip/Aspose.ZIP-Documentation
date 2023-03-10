---
title: WIM extraction
type: docs
weight: 79
url: /net/wim-extraction/
keywords: wim C# extraction, wim archive library
description: C# library allows you to extract Wim archive.
---


## **Overview**
Wim is Microsoft Windows image format. You can extract such an archive with Aspose.Zip similarly as other archives. It can contain several images, each of them is represented by [WimImage](https://reference.aspose.com/zip/net/aspose.zip.wim/wimimage/) class. We can to extract content of the images constituting the archive.


### **Extract Image**

This sample extracts two images of an archive, each to own directory.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ExtractWIMImage.cs" >}}

### **Extract Files**

This sample extracts each file entry of the first image to the directory.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ExtractWIMEntries.cs" >}}


