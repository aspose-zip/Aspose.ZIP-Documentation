---
title: Introduction
type: docs
weight: 10
url: /net/introduction/
---

Aspose.ZIP for .NET API lets work with creating and managing archives in your applications without the need of any other 3rd party applications. Its detailed implementation lets manage ZIP archives easily.
## **Basic Concepts of the API**
Aspose.ZIP API conceptualizes the functionality of each item in an archive as Entry. Entry(ies) can be added, updated as well as removed from an archive. The API makes it simplified to work with an archive and its entries. This section gives an idea about different classes and methods exposed by the API and their usage.
### **Working with Archives**
#### **Creating Archive**
An archive can be created using the Archive class exposed by the API. A basic archive can be created using this class as shown in the following code sample.

{{< highlight java >}}

 var archive = new Archive();

{{< /highlight >}}
#### **Creating Archive with Custom Compression**
Archives can be created with additional settings specifying custom Compression techniques.

{{< highlight java >}}

 var archive = new Archive(new ArchiveEntrySettings(new CompressionSettings(CompressionMethod.Store), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256)));

{{< /highlight >}}
#### **Saving Archives**
Archives can be saved to the file system on the disc as well as to streams.

{{< highlight java >}}

 archive.Save(stream, ArchiveSaveOptions saveOptions= null)



archive.Save(filePath, ArchiveSaveOptions saveOptions = null)

{{< /highlight >}}
#### **Archive Extraction**
Archives can be extracted by passing the source stream or path to the ZIP file.

{{< highlight java >}}

 FileStream zipFileStream = File.Open("myarchive.zip", FileMode.Open);

Archive archive = new Archive(zipFileStream);



or 



Archive archive = new Archive("myarchive.zip");

{{< /highlight >}}
#### **Extracting Encrypted Archives**
Password-protected archives can be extracted by specifying the ArchiveLoadOptions

{{< highlight java >}}

 Archive archive = new Archive(sourceStream, new ArchiveLoadOptions() { DecryptiptionPassword = "p@s$" });

or

Archive archive = new Archive("myarchive.zip", new ArchiveLoadOptions() { DecryptiptionPassword = "p@s$" });

{{< /highlight >}}
### **Working with Archive Entries**
#### **Adding Entries to Archive**
Entries can be added to an archive using the CreateEntry method of Archive. The overloads offered by this method allow you to create entries in an archive from file path or stream along with specification Archive Entry settings. Files from a directory can also be added to an archive specifying the recursive search through the directory.

{{< highlight java >}}

 CreateEntry(string name, Stream source, ArchiveEntrySettings newEntriesSettings) - Creates single entry with given name, data source, optional compression and encryption settings for the entry.

CreateEntry(string name, string path, ArchiveEntrySettings newEntriesSettings) - Creates single entry with given name and file source, optional compression and encryption settings for the entry.

CreateEntry(string name, FileInfo fileInfo, ArchiveEntrySettings newEntriesSettings) - Creates single entry with given name, file source, optional compression and encryption settings for the entry. Keeps attributes of NTFS file.

CreateEntry(string name, Stream source, ArchiveEntrySettings newEntriesSettings, FileSystemInfo fileInfo) - Creates single entry with given name, data source, compression and encryption settings for the entry. Keeps attributes of NTFS file and respects optional parameters.

{{< /highlight >}}
## **Modifying ZIP File**
In order to edit the zip file on the fly without extracting it on the disk, it can easily be done using extracting inner archives into memory and then remove them later. The content of the inner entries can be kept within memory streams so memory consumption may be higher. It is also possible to save the archive to the physical directory path. The following code example demonstrates the functionality.

{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-ModifyingZipFile-ModifyingZipFile.cs" >}}

