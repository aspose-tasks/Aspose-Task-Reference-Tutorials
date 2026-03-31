---
date: 2026-03-21
description: जानें कि कैसे संसाधनों की उपलब्धता अवधि को प्रबंधित किया जाए और Aspose.Tasks
  for .NET के साथ प्रभावी प्रोजेक्ट संसाधन उपलब्धता हासिल की जाए। यह चरण‑दर‑चरण गाइड
  दिखाता है कि उपलब्धता अवधि को कैसे जोड़ा, अपडेट किया और हटाया जाए।
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: प्रोजेक्ट संसाधन उपलब्धता – Aspose.Tasks में उपलब्धता अवधि का प्रबंधन
url: /hi/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# प्रोजेक्ट रिसोर्स उपलब्धता: Aspose.Tasks में उपलब्धता अवधि का संग्रह

**प्रोजेक्ट रिसोर्स उपलब्धता** को प्रबंधित करना सफल प्रोजेक्ट योजना का एक मुख्य हिस्सा है। इस ट्यूटोरियल में आप **उपलब्धता को प्रबंधित करने** के बारे में चरण‑दर‑चरण सीखेंगे, Aspose.Tasks for .NET API का उपयोग करके, प्रोजेक्ट लोड करने से लेकर रिसोर्स के बीच अवधि कॉपी करने तक।

## त्वरित उत्तर
- **उपलब्धता अवधियों के लिए मुख्य क्लास कौन सी है?** `AvailabilityPeriod` in the `Aspose.Tasks` namespace.  
- **क्या मैं मौजूदा अवधियों को साफ़ कर सकता हूँ?** हाँ, `resource.AvailabilityPeriods.Clear()` को कॉल करें।  
- **नया अवधि कैसे जोड़ूँ?** एक `AvailabilityPeriod` ऑब्जेक्ट बनाएं और `Add` या `Insert` का उपयोग करें।  
- **क्या अवधि को किसी अन्य रिसोर्स में कॉपी किया जा सकता है?** बिल्कुल – `CopyTo` का उपयोग करें और फिर प्रत्येक आइटम को लक्ष्य रिसोर्स में जोड़ें।  
- **क्या उत्पादन उपयोग के लिए लाइसेंस आवश्यक है?** हाँ, गैर‑ट्रायल डिप्लॉयमेंट के लिए एक व्यावसायिक Aspose.Tasks लाइसेंस आवश्यक है।

## प्रोजेक्ट रिसोर्स उपलब्धता क्या है?
प्रोजेक्ट रिसोर्स उपलब्धता उन तिथियों और इकाइयों (क्षमता का प्रतिशत) को परिभाषित करती है जब कोई रिसोर्स कार्यों को असाइन किया जा सकता है। इन अवधियों को नियंत्रित करके आप ओवर‑एलोकेशन को रोकते हैं और शेड्यूल की सटीकता को सुधारते हैं।

## उपलब्धता अवधियों को प्रबंधित करने के लिए Aspose.Tasks क्यों उपयोग करें?
- **पूर्ण .NET एकीकरण** – कोई COM इंटरऑप नहीं, शुद्ध प्रबंधित कोड।  
- **सूक्ष्म‑स्तरीय नियंत्रण** – सटीक प्रारंभ/समाप्ति तिथियां और अंशात्मक इकाइयाँ सेट करें।  
- **आसान कॉपी** – मैन्युअल पार्सिंग के बिना रिसोर्स के बीच उपलब्धता डेटा को स्थानांतरित करें।  
- **प्रदर्शन‑अनुकूलित** – बड़े MPP फ़ाइलों के साथ भी कुशलता से काम करता है।

## पूर्वापेक्षाएँ
1. **Visual Studio** – कोई भी नवीनतम संस्करण (2019, 2022, या बाद का)।  
2. **Aspose.Tasks for .NET** – डाउनलोड करें [here](https://releases.aspose.com/tasks/net/)।  
3. **Basic C# knowledge** – आपको क्लास, कलेक्शन और LINQ के साथ सहज होना चाहिए।

## Import Namespaces

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

हम कोर Aspose.Tasks नेमस्पेस को साथ ही उन मानक .NET कलेक्शनों को इम्पोर्ट करते हैं जिनकी हमें बाद में आवश्यकता होगी।

## Step 1: Initialize the Project and Resource

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

यहाँ हम मौजूदा MPP फ़ाइल लोड करते हैं और उस रिसोर्स को प्राप्त करते हैं जिसकी उपलब्धता को हम संपादित करना चाहते हैं (ID = 1)।

## Step 2: Clear Existing Availability Periods

```csharp
resource.AvailabilityPeriods.Clear();
```

क्लियर करने से पहले परिभाषित सभी अवधियां हट जाती हैं, जिससे हमें एक साफ़ स्लेट मिलती है।

## Step 3: Add Availability Periods

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

हम `AvailabilityPeriod` ऑब्जेक्ट्स का एक कलेक्शन प्राप्त करते हैं (मान लिया गया है कि `GetPeriods` हेल्पर कहीं और परिभाषित है) और प्रत्येक को जोड़ते हैं, यह जाँचते हुए कि कलेक्शन लिखने योग्य है।

## Step 4: Insert a New Availability Period

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

यह 2013 वर्ष के लिए एक कस्टम अवधि बनाता है और यदि वह पहले से मौजूद नहीं है तो इसे स्थिति 1 (दूसरा स्लॉट) पर इन्सर्ट करता है।

## Step 5: Display Availability Periods

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

एक त्वरित कंसोल डम्प कुल गिनती और प्रत्येक अवधि के विवरण दिखाता है – डिबगिंग या सत्यापन के लिए उपयोगी।

## Step 6: Copy Availability Periods to Another Resource

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

हम पूरे कलेक्शन को एक एरे में कॉपी करते हैं, लक्ष्य रिसोर्स की अवधियों को साफ़ करते हैं, और फिर उन्हें पुनः भरते हैं। यह दर्शाता है कि कैसे उपलब्धता डेटा को रिसोर्सों के बीच डुप्लिकेट किया जा सकता है।

## Step 7: Update and Remove Availability Periods

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

यहाँ हम अंतिम‑से‑पहले अवधि के `AvailableUnits` को समायोजित करते हैं और फिर वह 2013 अवधि हटाते हैं जिसे हमने पहले जोड़ा था।

## Common Issues and Solutions
- **Read‑only collection error** – सुनिश्चित करें कि प्रोजेक्ट रीड‑ओनली मोड में नहीं खुला है या नए आइटम जोड़ने से पहले आपने `resource.AvailabilityPeriods.Clear()` कॉल किया है।  
- **Overlapping periods** – Aspose.Tasks स्वचालित रूप से ओवरलैप को मर्ज नहीं करता; आपको उन्हें पहचानने और हल करने के लिए कस्टम लॉजिक लिखना पड़ सकता है।  
- **Incorrect date format** – हमेशा `DateTime` ऑब्जेक्ट्स का उपयोग करें; स्ट्रिंग पार्सिंग से लोकेल‑विशिष्ट बग्स उत्पन्न हो सकते हैं।

## Frequently Asked Questions

**Q: क्या मैं उपलब्धता अवधियों में कस्टम फ़ील्ड जोड़ सकता हूँ?**  
A: नहीं, Aspose.Tasks for .NET में उपलब्धता अवधियों में कस्टम फ़ील्ड समर्थित नहीं हैं।

**Q: क्या उपलब्धता अवधियां विशिष्ट कार्यों से जुड़ी होती हैं?**  
A: नहीं, वे रिसोर्स से जुड़ी होती हैं और यह निर्धारित करती हैं कि रिसोर्स सामान्यतः कार्यों के लिए कब उपलब्ध है।

**Q: क्या मैं बाहरी स्रोतों से उपलब्धता अवधियां आयात कर सकता हूँ?**  
A: हाँ, आप CSV, XML, या डेटाबेस से अवधि आयात कर सकते हैं, `AvailabilityPeriod` ऑब्जेक्ट बनाकर उन्हें कलेक्शन में जोड़ें।

**Q: ओवरलैपिंग उपलब्धता अवधियों को कैसे संभालूँ?**  
A: ओवरलैप स्वचालित रूप से हल नहीं होते; आपको कस्टम वैलिडेशन लागू करके टकराव वाले अवधि को मर्ज या अस्वीकार करना होगा।

**Q: क्या किसी रिसोर्स के पास उपलब्धता अवधियों की संख्या पर कोई सीमा है?**  
A: कोई हार्ड‑कोडेड सीमा नहीं है, लेकिन बहुत बड़े कलेक्शन से प्रदर्शन प्रभावित हो सकता है; संभव हो तो अवधियों को समेकित करने पर विचार करें।

## निष्कर्ष

इस गाइड में हमने Aspose.Tasks for .NET के साथ **प्रोजेक्ट रिसोर्स उपलब्धता** को प्रबंधित करने के सभी आवश्यक चरणों को कवर किया—प्रोजेक्ट को इनिशियलाइज़ करने और पुराना डेटा साफ़ करने से लेकर अवधि जोड़ने, इन्सर्ट करने, कॉपी करने, अपडेट करने और हटाने तक। इन चरणों में निपुणता आपको रिसोर्स कैलेंडर को सटीक रखने और प्रोजेक्ट शेड्यूल को यथार्थवादी बनाने में मदद करती है।

---

**अंतिम अपडेट:** 2026-03-21  
**परीक्षण किया गया:** Aspose.Tasks for .NET (latest release)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}