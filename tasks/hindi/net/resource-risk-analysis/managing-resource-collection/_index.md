---
title: Aspose.Tasks में प्रोजेक्ट संसाधन संग्रह का प्रबंधन करना
linktitle: Aspose.Tasks में संसाधन संग्रह का प्रबंधन करना
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks API का उपयोग करके .NET में Microsoft प्रोजेक्ट संसाधन संग्रह को कुशलतापूर्वक प्रबंधित करना सीखें। उत्पादकता और लचीलापन बढ़ाएँ.
type: docs
weight: 13
url: /hi/net/resource-risk-analysis/managing-resource-collection/
---
## परिचय
इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट संसाधन संग्रह को प्रभावी ढंग से कैसे प्रबंधित किया जाए। Aspose.Tasks एक शक्तिशाली एपीआई है जो डेवलपर्स को Microsoft प्रोजेक्ट फ़ाइलों के साथ प्रोग्रामेटिक रूप से काम करने में सक्षम बनाता है, जिससे प्रोजेक्ट डेटा के निर्बाध एकीकरण और हेरफेर की अनुमति मिलती है।
## आवश्यक शर्तें
इस ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1. C# और .NET फ्रेमवर्क का ज्ञान: यह ट्यूटोरियल C# प्रोग्रामिंग भाषा और .NET फ्रेमवर्क से परिचित है।
2. .NET के लिए Aspose.Tasks की स्थापना: सुनिश्चित करें कि आपने .NET के लिए Aspose.Tasks स्थापित कर लिया है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
3. विकास पर्यावरण सेटअप: विजुअल स्टूडियो या किसी अन्य पसंदीदा आईडीई के साथ अपना विकास वातावरण सेट करें।

## नामस्थान आयात करें
शुरू करने से पहले, Aspose.Tasks कार्यात्मकताओं तक पहुंचने के लिए आवश्यक नामस्थान आयात करें:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
सबसे पहले, Microsoft Project फ़ाइल को Aspose.Tasks प्रोजेक्ट ऑब्जेक्ट में लोड करें:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "SampleProject.mpp");
```
## चरण 2: खाली संसाधन जोड़ें
इसके बाद, आइए प्रोजेक्ट में एक खाली संसाधन जोड़ें:
```csharp
var resource = project.Resources.Add();
resource.Set(Rsc.Type, ResourceType.Work);
```
## चरण 3: नाम के साथ संसाधन जोड़ें
अब, प्रोजेक्ट में निर्दिष्ट नाम के साथ एक संसाधन जोड़ें:
```csharp
var developer = project.Resources.Add("Developer");
developer.Set(Rsc.Type, ResourceType.Work);
```
## चरण 4: दूसरे संसाधन से पहले संसाधन जोड़ें
किसी संसाधन को उसकी आईडी के आधार पर किसी अन्य संसाधन से पहले निर्दिष्ट नाम से जोड़ें:
```csharp
var manager = project.Resources.Add("Manager", developer.Get(Rsc.Id));
manager.Set(Rsc.Type, ResourceType.Work);
```
## चरण 5: आईडी या यूआईडी द्वारा संसाधनों तक पहुंच
आप संसाधनों तक उनकी आईडी या यूआईडी द्वारा पहुंच सकते हैं:
```csharp
var devResource = project.Resources.GetById(4);
devResource.Set(Rsc.Code, "12345");
var manResource = project.Resources.GetByUid(4);
manResource.Set(Rsc.Code, "54321");
```
## चरण 6: संसाधन जानकारी मुद्रित करना
प्रोजेक्ट संसाधनों के बारे में जानकारी प्रिंट करें:
```csharp
Console.WriteLine("Print the resources of " + project.Resources.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Count of resources: " + project.Resources.Count);
foreach (var rsc in project.Resources)
{
    Console.WriteLine("Resource Name: " + rsc.Get(Rsc.Name));
}
```
## चरण 7: संसाधन हटाना
प्रोजेक्ट से संसाधन हटाएँ:
```csharp
List<Resource> list = project.Resources.ToList();
foreach (var rsc in list)
{
    rsc.Delete();
}
```

## निष्कर्ष
.NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट संसाधन संग्रह का प्रबंधन करना डेवलपर्स को प्रोजेक्ट संसाधनों को प्रोग्रामेटिक रूप से कुशलतापूर्वक संभालने के लिए उपकरणों का एक मजबूत सेट प्रदान करता है। इस ट्यूटोरियल में उल्लिखित चरणों का पालन करके, आप अपनी परियोजनाओं के भीतर संसाधनों में निर्बाध रूप से हेरफेर कर सकते हैं, जिससे परियोजना प्रबंधन कार्यों में उत्पादकता और लचीलापन बढ़ सकता है।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या Aspose.Tasks बड़े पैमाने की प्रोजेक्ट फ़ाइलों को संभाल सकता है?

उत्तर: हां, Aspose.Tasks को उच्च प्रदर्शन और विश्वसनीयता प्रदान करते हुए बड़े पैमाने पर प्रोजेक्ट फ़ाइलों को कुशलतापूर्वक संभालने के लिए डिज़ाइन किया गया है।

### प्रश्न: क्या Aspose.Tasks माइक्रोसॉफ्ट प्रोजेक्ट के विभिन्न संस्करणों के साथ संगत है?

उत्तर: Aspose.Tasks विभिन्न परिवेशों में अनुकूलता सुनिश्चित करते हुए, Microsoft प्रोजेक्ट के विभिन्न संस्करणों का समर्थन करता है।

### प्रश्न: क्या मैं Aspose.Tasks का उपयोग करके संसाधन गुणों को अनुकूलित कर सकता हूँ?

उत्तर: बिल्कुल, Aspose.Tasks विशिष्ट परियोजना आवश्यकताओं के अनुसार संसाधन गुणों को अनुकूलित करने के लिए व्यापक क्षमताएं प्रदान करता है।

### प्रश्न: क्या Aspose.Tasks समवर्ती संचालन के लिए मल्टी-थ्रेडिंग का समर्थन करता है?

उत्तर: हां, Aspose.Tasks मल्टी-थ्रेडिंग का समर्थन करता है, जिससे प्रदर्शन में सुधार के लिए प्रोजेक्ट डेटा पर समवर्ती संचालन की अनुमति मिलती है।

### प्रश्न: क्या Aspose.Tasks उपयोगकर्ताओं के लिए तकनीकी सहायता उपलब्ध है?

 उत्तर: हां, Aspose.Tasks उपयोगकर्ता फोरम के माध्यम से तकनीकी सहायता प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15).