---
title: Reporting progress of compression
type: docs
weight: 44
url: /net/reporting-compression-progress/
keywords: C# zip library, compression progress, archive events
description: The compression process may take a long time. C# zip library provides events to report the progress of compression and progress percentage.
---

## **Progress Event Handler**
The compression process may take a long time especially if the data size is huge. For zip archive, there is a [CompressionProgressed event](https://reference.aspose.com/zip/net/aspose.zip/archiveentry/compressionprogressed/) to stay posted. This event relies on [ProgressEventArgs](https://reference.aspose.com/zip/net/aspose.zip/progresseventargs) which contains the number of proceeded bytes so far.
This is how we can subscribe to this event using [lambda extression](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/lambda-expressions):
```c#
entry.CompressionProgressed += (s, e) => { 
   Console.WriteLine(string.Format("{0} bytes compressed", e.ProceededBytes); 
};
```
## **Reporting Zip Progress Percentage**

Each time the `CompressionProgressed` event raises we divide the `ProceededBytes` number by the length of the original file. Such we find the ratio of compressed bytes at the moment. Here is the full sample.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ReportZipCompressionProgress.cs" >}}

## **Reporting 7z Progress Percentage** 

Similar approach is for 7z archive. Its entry has own [CompressionProgressed event](https://reference.aspose.com/zip/net/aspose.zip.sevenzip/sevenziparchiveentry/compressionprogressed/)

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "Report7ZCompressionProgress.cs" >}}