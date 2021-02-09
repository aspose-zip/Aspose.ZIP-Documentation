---
title: ZIP/UnZIP Files
type: docs
weight: 20
url: /net/compressing-and-decompressing-files/
---

Aspose.ZIP API lets you compress and decompress files without worrying about the underlying file structure. This article shows working with single as well as multiple file compression.
## **Compressing Files**
### **Compressing Single File**
{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-CompressSingleFile-CompressSingleFile.cs" >}}
### **Compressing Multiple Files**
{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-CompressMultipleFiles-CompressMultipleFiles.cs" >}}
### **Compress Files by File Info**
{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-CompressFilesByFileInfo-CompressFilesByFileInfo.cs" >}}
### **Storing Files to Archives without Compression**
{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-StoreMultipleFilesWithoutCompression-StoreMultipleFilesWithoutCompression.cs" >}}
### **Using Parallelism to Compress Files**
{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-UsingParallelismToCompressFiles-UsingParallelismToCompressFiles.cs" >}}


### **LZMA Compression within ZIP Archive**
The **Lempel–Ziv–Markov chain algorithm** (**LZMA**) is an algorithm used to perform lossless data compression. LZMA uses a dictionary compression algorithm, the compressed stream is a stream of bits. LZMA compression within the ZIP archive allows ZIP containers to contain LZMA compressed entries. The following code example shows the implementation of LZMA compression using Aspose.ZIP API.

{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-CompressionSettings-UsingLZMACompressionSettings.cs" >}}


### **BZip2 Compression within ZIP Archive**
BZip2 compression settings allow ZIP container to contain BZip2 compressed entries. The following code example shows the implementation of BZip2 compression using Aspose.ZIP API.

{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-CompressionSettings-UsingBzip2CompressionSettings.cs" >}}
### **PPMd Compression within ZIP Archive**
PPMd compression settings allow ZIP container to contain PPMd compressed entries. The following code example demonstrated the implementation of PPMd compression using Aspose.ZIP API.

{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-CompressionSettings-UsingPPMdCompressionSettings.cs" >}}


## **Decompressing Archives**
### **Decompress Archive having Single File**
{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-DecompressSingleFile-DecompressSingleFile.cs" >}}
### **Decompress Archive having Multiple Files**
{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-DecompressMultipleFiles-DecompressMultipleFiles.cs" >}}
### **Extract Stored Archive without Compression**
{{< gist "aspose-com-gists" "42ee14864d84aeae8619284450c3d628" "Examples-CSharp-CompressingAndDecompressingFiles-DecompressStoredFile-DecompressStoredFile.cs" >}}
