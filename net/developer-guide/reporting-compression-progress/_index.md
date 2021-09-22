---
title: Reporting progress of compression
type: docs
weight: 44
url: /net/reporting-compression-progress/
---

## **Progress Event Handler**
Compression process may take a long time especially if data size is huge. For zip archive there is a [CompressionProgressed event](https://apireference.aspose.com/zip/net/aspose.zip/archiveentry/events/compressionprogressed) to stay posted. This event relies on [ProgressEventArgs](https://apireference.aspose.com/zip/net/aspose.zip/progresseventargs) which contains the number of proceeded bytes so far.
This is how we can subscribe to this event using [lambda extression](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/lambda-expressions):
```c#
entry.CompressionProgressed += (s, e) => { 
   Console.WriteLine(string.Format("{0} bytes compressed", e.ProceededBytes); 
};
```
## **Reporting Progress Percentage**

Each time `CompressionProgressed` event raises we divide `ProceededBytes` number by the length of original file. Such we find the ratio of compressed bytes at the moment. Here is the full sample.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ReportZipCompressionProgress.cs" >}}