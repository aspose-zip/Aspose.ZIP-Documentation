---
title: Parallel bzip2 compression 
type: docs
weight: 72
url: /net/parallel-bzip2/
keywords: parallel bzip2, pbzip2
description: C# library allows you to compress to bzip2 in several threads.
---


## **Using several CPU cores**
Bzip2 divides data into blocks and compresses them independently. Aspose.ZIP API allows to do it in parallel.
The only thing you need to turn it on is set [CompressionThreads](https://reference.aspose.com/zip/net/aspose.zip.bzip2/bzip2saveoptions/compressionthreads/) to more then one.

In the sample all CPU cores are used.
{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "ParallelBzip2.cs" >}}

