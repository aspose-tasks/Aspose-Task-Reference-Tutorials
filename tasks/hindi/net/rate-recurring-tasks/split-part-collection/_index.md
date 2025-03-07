---
title: Aspose.Tasks में स्प्लिट पार्ट्स का MS प्रोजेक्ट एकत्रित करें
linktitle: Aspose.Tasks में विभाजित भागों का संग्रह
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट में विभाजित भागों को एकत्रित करना सीखें। यह व्यापक ट्यूटोरियल चरण-दर-चरण प्रक्रिया में आपका मार्गदर्शन करता है।
weight: 19
url: /hi/net/rate-recurring-tasks/split-part-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में स्प्लिट पार्ट्स का MS प्रोजेक्ट एकत्रित करें

## परिचय
इस ट्यूटोरियल में, हम .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट में विभाजित भागों को कैसे एकत्रित करें, इस पर विस्तार से चर्चा करेंगे। कार्यों को भागों में विभाजित करना परियोजना प्रबंधन का एक महत्वपूर्ण पहलू हो सकता है, और Aspose.Tasks इसे कुशलतापूर्वक संभालने के लिए सुविधाजनक तरीके प्रदान करता है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:
1. .NET के लिए Aspose.Tasks की स्थापना: सुनिश्चित करें कि आपने .NET के लिए Aspose.Tasks स्थापित कर लिया है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
2. C# का बुनियादी ज्ञान: C# प्रोग्रामिंग भाषा से परिचित होना फायदेमंद होगा क्योंकि हम C# में कोड स्निपेट लिखेंगे।

## नामस्थान आयात करें
अपने C# प्रोजेक्ट में, आवश्यक नामस्थान शामिल करें:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## चरण 1: अपना प्रोजेक्ट सेट करें
सबसे पहले, अपने पसंदीदा IDE में एक नया प्रोजेक्ट बनाएं और सुनिश्चित करें कि .NET के लिए Aspose.Tasks को सही ढंग से संदर्भित किया गया है।
## चरण 2: प्रोजेक्ट ऑब्जेक्ट को प्रारंभ करें
```csharp
// दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
अपनी एमएस प्रोजेक्ट फ़ाइल के पथ के साथ एक नया प्रोजेक्ट ऑब्जेक्ट प्रारंभ करें।
## चरण 3: कार्य को पुनः प्राप्त करें और विभाजित भागों पर पुनरावृति करें
```csharp
var task = project.RootTask.Children.GetById(1);
// विभाजित भागों पर पुनरावृति करें
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
प्रोजेक्ट से कार्य को पुनः प्राप्त करें और उसके विभाजित भागों पर पुनरावृति करें, उनकी आरंभ और समाप्ति तिथियों को प्रिंट करें।
## चरण 4: सूचकांक द्वारा भाग को विभाजित करें
```csharp
// अनुक्रमणिका द्वारा भाग प्राप्त करें
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
सूचकांक द्वारा एक विशिष्ट विभाजित भाग को पुनः प्राप्त करें और उसकी आरंभ तिथि का प्रिंट आउट लें।

## निष्कर्ष
एमएस प्रोजेक्ट फ़ाइलों में विभाजित भागों को प्रबंधित करने से प्रोजेक्ट प्रबंधन दक्षता में उल्लेखनीय वृद्धि हो सकती है। .NET के लिए Aspose.Tasks विभाजित कार्यों को निर्बाध रूप से संभालने के लिए सहज एपीआई प्रदान करके इस प्रक्रिया को सरल बनाता है।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं रनटाइम के दौरान कार्यों को गतिशील रूप से विभाजित कर सकता हूँ?
उ: हां, आप .NET के लिए Aspose.Tasks का उपयोग करके कार्यों को प्रोग्रामेटिक रूप से विभाजित कर सकते हैं।
### प्रश्न: क्या Aspose.Tasks MS प्रोजेक्ट फ़ाइलों के सभी संस्करणों का समर्थन करता है?
उत्तर: Aspose.Tasks MS प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों का समर्थन करता है, जो विभिन्न प्लेटफार्मों पर अनुकूलता सुनिश्चित करता है।
### प्रश्न: क्या परीक्षण उद्देश्यों के लिए कोई परीक्षण संस्करण उपलब्ध है?
 उत्तर: हाँ, आप नि:शुल्क परीक्षण संस्करण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/) मूल्यांकन के लिए।
### प्रश्न: मैं अपनी परियोजनाओं के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 उत्तर: अस्थायी लाइसेंस यहां से प्राप्त किया जा सकता है[यहाँ](https://purchase.aspose.com/temporary-license/) अल्पकालिक उपयोग के लिए.
### प्रश्न: मैं Aspose.Tasks के संबंध में सहायता या सहायता कहां से मांग सकता हूं?
 उत्तर: आप Aspose.Tasks फोरम पर जा सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15)समुदाय या Aspose सहायता टीम से सहायता लेने के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
