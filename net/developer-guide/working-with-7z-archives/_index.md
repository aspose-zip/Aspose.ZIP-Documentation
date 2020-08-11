---
title: Working with 7z Archives
type: docs
weight: 60
url: /net/working-with-7z-archives/
---


## **Overview**
7-Zip is a file archiver with a high compression ratio. Aspose.ZIP API lets work with creating and managing 7-Zip archives in your applications without the need of any other 3rd party applications. Aspose.ZIP API provides [SevenZipArchive](https://apireference.aspose.com/net/zip/aspose.zip.sevenzip/sevenziparchive) class to work with 7-Zip archives. This class provides various methods to perform operations on archives. API provides the [SevenZipArchiveEntry ](https://apireference.aspose.com/net/zip/aspose.zip.sevenzip/sevenziparchiveentry)class to represents a single file within the 7z archive.
### **Create a 7-Zip Single Entry**
The following code example demonstrates how to create a 7-Zip entry using SevenZipArchive instance.

{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-WorkingWithSevenZip-CreateSevenZipEntry-CreateSevenZipEntry.cs" >}}
### **Create 7-Zip Archive Entries**
The SevenZipArchive class provides CreateEntries methods to add files and directories recursively in the given directory given. The following code example demonstrates how to create 7-Zip archive entries.

{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-WorkingWithSevenZip-CreateSevenZipEntries-CreateSevenZipEntries.cs" >}}
### **7-Zip Encryption Settings**
Aspose.ZIP API provides [SevenZipAESEncryptionSettings](https://apireference.aspose.com/net/zip/aspose.zip.saving/sevenzipaesencryptionsettings) class which provides Settings for AES encryption or decryption for 7z archives. The following code example demonstrates how to provide AES Encryption Settings.

{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-WorkingWithSevenZip-AESEncryptionSettings-AESEncryptionSettings.cs" >}}

{{% alert color="primary" %}} 

The AES-256 is the only possible encryption method for the 7z archive.

{{% /alert %}} 


### **7-Zip Archive with LZMA Compression**
The following code example demonstrates how to create a 7z archive with LZMA compression.

{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-WorkingWithSevenZip-ArchiveWithEncryptedEntry-ArchiveWithEncryptedEntry.cs" >}}


### **Setting Different Password for Entries**
The following code example demonstrates how to create an archive with entries encrypted with different passwords for each entry.

{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-WorkingWithSevenZip-EntriesWithDifferentPasswords-EntriesWithDifferentPasswords.cs" >}}
