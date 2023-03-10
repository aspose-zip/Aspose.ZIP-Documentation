---
title: Cancel ZIP archive creation
type: docs
weight: 68
url: /net/cancel-archive-creation/
---

It may happen you want to cancel zip archive creation for various reasons. It just can take too long or you do not actually need some entries there.

## **Overview**
There is an [EventsBag](https://reference.aspose.com/zip/net/aspose.zip.saving/eventsbag) class which are container for archive-related events. Now it supports one event - [EntryCompressed](https://reference.aspose.com/zip/net/aspose.zip.saving/eventsbag/events/entrycompressed). It raises after an archive entry has been compressed, and it cancelable. 

## **Canceling long archive creation**
Lets say you want your ZIP archive to be composed in about a minute. 
After some entry has been compressed check the time taken from the beginning of compression, and if it took more than a minute, cancel the process. The result archive would have already compressed entries including the one triggred the event.

{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "CancelTooLongZipCreation.cs" >}}

## **Canceling after certain entry**

If you want to cancel after particular entry has been compressed use following snippet:
{{< gist "aspose-zip-gists" "d69b478235af94b9860be5443f24d031" "CancelAfterCertainEntry.cs" >}}