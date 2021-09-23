---
title: Collect files to tar and compress
type: docs
weight: 64
url: /net/tar-archiving/
---

### **Tar purpose**
[Tar archive](https://apireference.aspose.com/zip/net/aspose.zip.tar/tararchive) allows you combine several files to single file. You may compress joint file, too.

### **Collecting without compression**

There is a sample of collecting two files into tar archive.
{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "TarArchiving.cs" >}}

### **Compressing tar archive**

In Unix-like operating systems `tar` utility allows to compress tar archive to gzip on creation. Aspose.Zip provides similar functionality with [SaveGzipped](https://apireference.aspose.com/zip/net/aspose.zip.tar.tararchive/savegzipped/methods/1) method.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "TarArchiveingAndCompressing.cs" >}}

Nowdays [xz utility](https://en.wikipedia.org/wiki/XZ_Utils) become popular in Linux and Unix. Its compression of tar is seamlessly integrated into Aspose.Zip. Use [SaveXzCompressed](https://apireference.aspose.com/zip/net/aspose.zip.tar/tararchive/methods/savexzcompressed) method of tar archive.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "TarArchiveAndXZCompress.cs" >}}