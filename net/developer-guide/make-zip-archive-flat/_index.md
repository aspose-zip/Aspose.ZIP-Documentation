---
title: Make a ZIP archive flat
type: docs
weight: 42
url: /net/flatten-nested-zip/
---

It may happen that your zip archive has other zip archives inside it. One may want to extract the nested zip archive’s contents into the parent archive to get flat structure.

<h5> Current archive structure </h5>
<pre>
<u>outer.zip</u>
 ├first.txt
 ├<u>inner.zip</u>
 │ ├game.exe
 │ └subitem.bin
 └picture.gif
</pre>
<h5> Desired archive structure </h5>
<pre>
<u>flatten.zip</u>
 ├first.txt
 ├picture.gif
 ├game.exe
 └subitem.bin
</pre>


If you are not familiar with Aspose.Zip read how to [extract zip archive](https://docs.aspose.com/zip/net/compressing-and-decompressing-files/#decompressing-archives) first.

### **Overal explanation**

First, we need to list all the entries of the archive. Regular entries should be kept as they are, we should not even decompress them. Entries that are archives themselves need to be extracted to memory and removed from outer archive. Their content need to included to the main archive. 

### **Detecting entries that are archives**
Lets decide which entries are archives itself. We can figure this out by extension of entry name.
Later we will remove those entries from main archive, so keep such entries in a list.
```c#
if (entry.Name.EndsWith(".zip", StringComparison.InvariantCultureIgnoreCase)) {
    entriesToDelete.Add(entry);
    ...
}
```

### **Extracting entry's content to memory**

Aspose.Zip allows to extract the content of zip entry into any writable stream, not only to a file. So, we can extract a nested archive to a memory stream.

{{% alert color="primary" %}} 

Please note: the virtual memory must be big enough to keep all extracted content.

{{% /alert %}} 

```c#
MemoryStream innerCompressed = new MemoryStream();
entry.Open().CopyTo(innerCompressed); 
```

After that innerCompressed stream contains inner archive itself. The [Archive constructor](https://apireference.aspose.com/zip/net/aspose.zip/archive/constructors/1) allows to decompress the stream provided.
So, we can extract it as well:
```c#
Archive inner = new Archive(innerCompressed);
```


### **Excluding entries** 

We can remove an entry from zip archive with [particular method](https://apireference.aspose.com/zip/net/aspose.zip/archive/methods/deleteentry).

```c#
foreach (ArchiveEntry e in entriesToDelete) { outer.DeleteEntry(e); }
```

### **Put it all together**

Here is the complete algorithm.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "FlattenZip.cs" >}}