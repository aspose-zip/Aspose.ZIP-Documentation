---
title: Create self-extracting (SFX) archive
type: docs
weight: 67
url: /net/create-self-extracting-sfx-archive/
aliases: [/net/creating-sfx-archive/]
---

Aspose.ZIP allows creating a self-extracting (SFX) archive.  This is a special kind of zipped file, which has a filename extension of.exe. You can unzip a self-extracting file by double-clicking it.

## **Creation self-extracting archive**
To compose a self-extracting archive instantiate [SelfExtractorOptions](https://reference.aspose.com/zip/net/aspose.zip.saving/selfextractoroptions) and pass it to [ArchiveSaveOptions](https://reference.aspose.com/zip/net/aspose.zip.saving/archivesaveoptions) on saving.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ComposeSelfExtractingArchive.cs" >}}

## **Running self-extracting archive**
The archive you produce is executable and requires .NET Framework 2.0 or higher to run. Such frameworks are supplied with Windows Vista and above.
You can execute it as a regular program by double click, or run it via the command-line interface.
If you want to start extraction automatically specify `-autoExtract` command-line option. Sample:
```cmd
C:\>archive.exe -autoExtract -password:T0p$ecret
```
### **Command line options for self-extracting archive**
|**Option**|**Meaning**|**Sample**|
| :- | :- | :- |
|-autoExtract|<p>Primary option - without it decompression does not start.</p><p>Extraction starts automatically, other options apply.</p>|```sfx.exe -autoExtract```|
|-autoClose|Window closes when the extraction is complete. This option only makes sense if *-autoExtract* option is present.|```sfx.exe -autoExtract -autoClose```|
|-forceOverwrite|Overwrites all existing files without prompt if there are any. This option only makes sense if *-autoExtract* option present.|```sfx.exe -autoExtract -forceOverwrite```|
|-password:<password>|<p>Provides a password to encrypted entries. This option only makes sense if *-autoExtract* option is present.</p><p>If you have spaces within the password quote it.</p>|```sfx.exe -autoExtract -password:T0p$ecret```|
|-destination:<path to folder>|<p>Extracts files to the supplied directory. This option only makes sense if *-autoExtract* option is present.</p><p>If you have spaces within the path quote it.</p>|```sfx.exe -autoExtract -destination:"C:\My Documents"```|

You can use those options for composing Batch Script on Windows.