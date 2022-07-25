---
title: Licensing
type: docs
weight: 50
url: /net/licensing/
---

## **Evaluate Aspose.ZIP**
You can download Aspose.ZIP for .NET free of cost for evaluation. The evaluation version provides almost all functionality of the product with certain limitations. The same evaluation version becomes licensed when you purchase a license and add a couple of lines of code to [apply the license](/zip/net/licensing/#licensing-applylicenseusingfileorstreamobject).

If you want to test Aspose.ZIP without evaluation version limitations, you can also request a 30 Day Temporary License. Please refer to [How to get a Temporary License?](https://purchase.aspose.com/temporary-license)
### **Evaluation Version Limitations**
The evaluation version of Aspose.ZIP (without a license specified) provides full product functionality except for some evaluation limitations.

|**Usage context**|**Restrictions**|
| :- | :- |
|Size of data to compress|No more than 5,032,768 bytes of each entry to be compressed|
|Size of data to decompress|No more than 5,000,000 bytes of each entry to be decompressed|
|CRC verification on decompression|Not performed|
|MAC verification on decompression in an encrypted file|Not performed|
|Number of entries compressed|No more than 10|
|Extraction by running self-extracted archive|No more then 10 files no more than 5,000,000 bytes each|
## **Applying a License**
You can easily download an evaluation version of Aspose.ZIP from its [download page](https://www.nuget.org/packages/Aspose.ZIP/). The evaluation version provides absolutely the same capabilities as the licensed version of Aspose.ZIP. Furthermore, the evaluation version simply becomes licensed when you purchase a license and add a couple of lines of code to apply the license.
### **About the License**
The license is a plain-text XML file that contains details such as the product name, number of developers it is licensed to, subscription expiry date and so on. The file is digitally signed, so don't modify the file. Even the inadvertent addition of an extra line break into the file will invalidate it.

You need to set a license before utilizing Aspose.ZIP if you want to avoid its evaluation limitations. It is only required to set a license once per application (or process).
### **Apply License Using File or Stream Object**
#### **Setting a License in Aspose.ZIP for .NET**
In Aspose.Zip, the license can be loaded from a file, stream or an embedded resource. Aspose.ZIP tries to find the license at the following locations:

- Explicit path
- The folder that contains the DLL of the component (included in Aspose.ZIP)
- The folder that contains the assembly that called the DLL of the component (included in Aspose.ZIP)
- The folder that contains the entry assembly (your .exe)
- An embedded resource in the assembly that called the DLL of the component (included in Aspose.ZIP) There are two common methods to set the license, which are discussed below:
#### **Apply License using File or Stream Object**
The easiest way to set a license is to put the license file in the same folder as that of the DLL of the component (included in Aspose.ZIP) and specify just the file name without its path.

{{< highlight java >}}

 // Instantiate an instance of license and set the license file through its path

Aspose.ZIP.License license = new Aspose.ZIP.License();

license.SetLicense("Aspose.ZIP.lic");

{{< /highlight >}}

{{< highlight java >}}

 // Instantiate an instance of license and set the license through a stream

Aspose.ZIP.License license = new Aspose.ZIP.License();

license.SetLicense(myStream);

{{< /highlight >}}



When you call the SetLicense method, the license name should be the same as that of your license file name. For example, you may change the license file name to "Aspose.ZIP.lic.xml". Then in your code, you should use the modified license name (that is Aspose.ZIP.lic.xml) for the SetLicense method.
## **Including the License File as an Embedded Resource**
Another neat way of packaging the license with your application and making sure it will not be lost, is to include it as an embedded resource into one of the assemblies that call the DLL of the component (included in Aspose.ZIP). To include the license file as an embedded resource, perform the following steps:

- In Visual Studio .NET, including the license (.lic) file into the project using the File | Add Existing Item... menu
- Select the file in the Solution Explorer and set Build Action to Embedded Resource in the Properties window
- To access the license embedded in the assembly (as an embedded resource), it is not needed to call GetExecutingAssembly and GetManifestResourceStream methods of the System.Reflection.Assembly class of Microsoft .NET Framework. All is needed to do, is to just add the license file as an embedded resource to your project and pass the name of the license file into the SetLicense License method. The Licenseclass will automatically find the license file in the embedded resources.

Please review the example given below to understand this method of setting a license (embedded) in your applications.

{{< highlight java >}}

 // Instantiate the License class

Aspose.ZIP.License license = new Aspose.ZIP.License();

// Pass only the name of the license file embedded in the assembly

license.SetLicense("Aspose.ZIP.lic");

{{< /highlight >}}
