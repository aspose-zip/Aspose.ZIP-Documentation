---
title: Unlock ZIP password
type: docs
weight: 41
url: /net/unlock-zip-password/
---

### **Forgotten password**

It is common to forget password "partly", i. e. remember some characters of it while forgetting others.
Aspose.ZIP API lets you play with such half-forgotten passwords to unlock the archive. This article shows guessing the decryption password of the AES-encrypted zip archive.

### **Identifying password template**

Let's say your password starts with "T0p$ecret" symbols followed by capital English letter and two digits. So, we can describe a template like this: 
```c#
string template = "T0p$ecret{0}{1}";
```
where former placeholder is for capital english letter, latter is for two-digit number.

### **Verifying single password** 
This simple decryption code 
```c#
 using (var a = new Archive("encrypted.zip", new ArchiveLoadOptions() {DecryptionPassword = password}))
    a.ExtractToDirectory(".");
```
raises an [InvalidDataException](https://docs.microsoft.com/en-us/dotnet/api/system.io.invaliddataexception) if wrong password has been supplied.

### **Brute force attack on the archive**

So compose and test passwords one by one. If there will be success program prints the proper password to the console.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "GuessPassword.cs" >}}