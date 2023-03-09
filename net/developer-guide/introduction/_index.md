---
title: Introduction
type: docs
weight: 10
url: /net/introduction/
---

Aspose.ZIP for .NET API lets work with creating and managing archives in your applications without the need of any other 3rd party applications. Its detailed implementation lets manage ZIP archives easily.

{{% alert color="primary" %}} This article descibes manipulation with _zip_ format only. Aspose.Zip support a lot of archive formats, they are listed [here](https://docs.aspose.com/zip/net/supported-file-formats/). {{% /alert %}}
## **Basic Concepts of the API**
Aspose.ZIP API conceptualizes the functionality of each item in an archive as [Entry](https://reference.aspose.com/zip/net/aspose.zip/archiveentry/). Entry(ies) can be added, updated as well as removed from an archive. The API makes it simplified to work with an archive and its entries. This section gives an idea about different classes and methods exposed by the API and their usage.
### **Working with Archives**
#### **Creating Archive**
An archive can be created using the [Archive](https://reference.aspose.com/zip/net/aspose.zip/archive/) class exposed by the API. A basic archive can be created using this class as shown in the following code sample.

{{< highlight java >}}
var archive = new Archive();
{{< /highlight >}}
Such archive is prepared for compression.

#### **Creating Archive with Custom Compression**
Archives can be created with additional settings specifying custom Compression techniques.

{{< highlight java >}}

 var archive = new Archive(new ArchiveEntrySettings(new CompressionSettings(CompressionMethod.Store), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256)));

{{< /highlight >}}
#### **Saving Archives**
Archives can be [saved](https://reference.aspose.com/zip/net/aspose.zip/archive/save/) to the file system on the disc as well as to streams.

{{< highlight java >}}

archive.Save(stream, ArchiveSaveOptions saveOptions = null)

archive.Save(filePath, ArchiveSaveOptions saveOptions = null)

{{< /highlight >}}
#### **Archive Extraction**
Archives can be extracted by passing the source stream or path to the Archive [extracting constructor](https://reference.aspose.com/zip/net/aspose.zip/archive/archive/#archive-constructor-2-of-3).

{{< highlight java >}}

FileStream zipFileStream = File.Open("myarchive.zip", FileMode.Open);
Archive archive = new Archive(zipFileStream);

or 

Archive archive = new Archive("myarchive.zip");

{{< /highlight >}}
#### **Extracting Encrypted Archives**
Password-protected archives can be extracted by specifying the [ArchiveLoadOptions](https://reference.aspose.com/zip/net/aspose.zip/archiveloadoptions/)

{{< highlight java >}}

 Archive archive = new Archive(sourceStream, new ArchiveLoadOptions() { DecryptiptionPassword = "p@s$" });

or

Archive archive = new Archive("myarchive.zip", new ArchiveLoadOptions() { DecryptiptionPassword = "p@s$" });

{{< /highlight >}}
### **Working with Archive Entries**
#### **Adding Entries to Archive**
Entries can be added to an archive using the [CreateEntry](https://reference.aspose.com/zip/net/aspose.zip/archive/createentry/) method of Archive. The overloads offered by this method allow you to create entries in an archive from file path or stream along with specification Archive Entry settings. Files from a directory can also be added to an archive specifying the recursive search through the directory.

{{< highlight java >}}

CreateEntry(string name, Stream source, ArchiveEntrySettings newEntriesSettings) - Creates single entry with given name, data source, optional compression and encryption settings for the entry.

CreateEntry(string name, string path, ArchiveEntrySettings newEntriesSettings) - Creates single entry with given name and file source, optional compression and encryption settings for the entry.

CreateEntry(string name, FileInfo fileInfo, ArchiveEntrySettings newEntriesSettings) - Creates single entry with given name, file source, optional compression and encryption settings for the entry. Keeps attributes of NTFS file.

CreateEntry(string name, Stream source, ArchiveEntrySettings newEntriesSettings, FileSystemInfo fileInfo) - Creates single entry with given name, data source, compression and encryption settings for the entry. Keeps attributes of NTFS file and respects optional parameters.

{{< /highlight >}}