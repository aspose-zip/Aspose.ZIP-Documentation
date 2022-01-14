---
title: Aspose.ZIP for .NET 22.1 Release Notes
type: docs
weight: 30
url: /net/aspose-zip-for-net-22-1-release-notes/
---

{{% alert color="primary" %}} 

This page contains release notes information for [Aspose.ZIP for .NET 22.1](https://downloads.aspose.com/zip/net/new-releases/aspose.zip-for-.net-22.1/).

{{% /alert %}} 


## **All Changes**

|**Key**|**Summary**|**Issue Type**|
| :- | :- | :- |
|ZIPNET-832|Extract Z archives.|Enhancement|
|ZIPNET-841|Bug on cpio extraction.|Bug|
|ZIPNET-840|Bug on tar extraction.|Bug|

## **Public API and Backwards Incompatible Changes**
|**The following public methods and properties were added:**|**Description**|
|Aspose.Zip.Z.ZArchive.Extract(Stream destination)|Extracts Z archive to the stream provided.|
|Aspose.Zip.Z.ZArchive.Extract(FileInfo fileInfo)|Extracts Z archive to a file.|
|Aspose.Zip.Z.ZArchive.Extract(string path)|Extracts Z archive to a file by path.|
|Aspose.Zip.Tar.TarArchive.FromZ(Stream source)|Extracts supplied Z format archive and composes TarArchive from extracted data.|
|Aspose.Zip.Tar.TarArchive.FromZ(string path)|Extracts supplied Z format archive and composes TarArchive from extracted data.|