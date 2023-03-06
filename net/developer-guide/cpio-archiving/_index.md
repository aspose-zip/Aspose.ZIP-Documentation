---
title: Collect files to cpio and compress
type: docs
weight: 75
url: /net/cpio-archiving/
keywords: cpio compression, create cpio
description: .NET library allows you to compose and compress cpio
---

### **Cpio purpose**
Cpio format is similar to [tar](https://docs.fileformat.com/compression/tar/). 
[Cpio archive](https://reference.aspose.com/zip/net/aspose.zip.cpio/cpioarchive/) allows you to combine several files into a single file. You may compress the joint file, too.

### **Collecting without compression**

There is a sample of collecting two files into a cpio archive.
{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "CpioArchiving.cs" >}}

### **Compressing cpio archive**

In Unix-like operating systems `cpio` utility allows compressing cpio archive to gzip on creation. Aspose.Zip provides similar functionality with the [SaveGzipped](https://reference.aspose.com/zip/net/aspose.zip.cpio/cpioarchive/savegzipped/) method.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "CpioArchiveingAndCompressing.cs" >}}

Nowadays [xz utility](https://en.wikipedia.org/wiki/XZ_Utils) has become popular in Linux and Unix. Its compression of cpio is seamlessly integrated into Aspose.Zip. Use the [SaveXzCompressed](https://reference.aspose.com/zip/net/aspose.zip.cpio/cpioarchive/savexzcompressed/) method of a cpio archive.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "CpioArchiveAndXZCompress.cs" >}}