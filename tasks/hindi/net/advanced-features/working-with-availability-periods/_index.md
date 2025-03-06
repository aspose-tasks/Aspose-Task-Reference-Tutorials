---
title: Aspose.Tasks में उपलब्धता अवधि के साथ कार्य करना
linktitle: Aspose.Tasks में उपलब्धता अवधि के साथ कार्य करना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके संसाधन उपलब्धता अवधि को कुशलतापूर्वक प्रबंधित करना सीखें। यह ट्यूटोरियल आपके .NET प्रोजेक्ट्स में उपलब्धता अवधि के साथ काम करने के लिए चरण-दर-चरण मार्गदर्शिका प्रदान करता है।
weight: 17
url: /hi/net/advanced-features/working-with-availability-periods/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में उपलब्धता अवधि के साथ कार्य करना

## परिचय

इस ट्यूटोरियल में, हम जानेंगे कि .NET के लिए Aspose.Tasks में उपलब्धता अवधि के साथ कैसे काम किया जाए। परियोजना प्रबंधन परिदृश्यों में संसाधनों को कुशलतापूर्वक प्रबंधित करने के लिए उपलब्धता अवधि महत्वपूर्ण हैं। हम चरण दर चरण प्रक्रिया में आपका मार्गदर्शन करेंगे.

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:

1. विजुअल स्टूडियो: .NET विकास के लिए विजुअल स्टूडियो या कोई अन्य पसंदीदा आईडीई स्थापित करें।
2.  .NET के लिए Aspose.Tasks: .NET लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/net/).
3. C# प्रोग्रामिंग की बुनियादी समझ: C# प्रोग्रामिंग भाषा की बुनियादी बातों से परिचित होना मददगार होगा।

## नामस्थान आयात करें

कोड में गोता लगाने से पहले, आवश्यक नामस्थान आयात करना सुनिश्चित करें:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

आइए उदाहरण कोड को कई चरणों में विभाजित करें:

## चरण 1: एक नया प्रोजेक्ट इंस्टेंस बनाएं

```csharp
var project = new Project();
```

यह लाइन प्रोजेक्ट क्लास का एक नया उदाहरण प्रारंभ करती है, जो Aspose.Tasks में एक प्रोजेक्ट का प्रतिनिधित्व करती है।

## चरण 2: एक संसाधन जोड़ें

```csharp
var resource = project.Resources.Add("Work Resource");
```

यहां, हम प्रोजेक्ट में "कार्य संसाधन" नाम से एक नया संसाधन जोड़ते हैं।

## चरण 3: उपलब्धता अवधि परिभाषित करें

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

 हम कॉल करते हैं`GetPeriods()` उपलब्धता अवधियों का संग्रह पुनः प्राप्त करने की विधि।

## चरण 4: संसाधन में उपलब्धता अवधि जोड़ें

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

हम पिछले चरण में प्राप्त उपलब्धता अवधि के संग्रह के माध्यम से पुनरावृति करते हैं और उन्हें संसाधन में जोड़ते हैं।

## चरण 5: उपलब्धता अवधि विवरण प्रदर्शित करें

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

अंत में, हम संसाधन से जुड़ी उपलब्धता अवधि के माध्यम से लूप करते हैं और आरंभ तिथि, समाप्ति तिथि और उपलब्ध इकाइयों सहित उनके विवरण प्रिंट करते हैं।

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Tasks में उपलब्धता अवधि के साथ कैसे काम किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने प्रोजेक्ट प्रबंधन अनुप्रयोगों में संसाधन उपलब्धता को कुशलतापूर्वक प्रबंधित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं व्यावसायिक परियोजनाओं में .NET के लिए Aspose.Tasks का उपयोग कर सकता हूँ?

 A1: हाँ, .NET के लिए Aspose.Tasks का उपयोग व्यावसायिक परियोजनाओं में किया जा सकता है। आप लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).

### Q2: क्या .NET के लिए Aspose.Tasks के लिए कोई निःशुल्क परीक्षण उपलब्ध है?

उ2: हाँ, आप .NET के लिए Aspose.Tasks का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q3: मुझे .NET के लिए Aspose.Tasks के लिए दस्तावेज़ कहाँ मिल सकते हैं?

 A3: आप दस्तावेज़ पा सकते हैं[यहाँ](https://reference.aspose.com/tasks/net/).

### Q4: मैं .NET के लिए Aspose.Tasks के लिए समर्थन कैसे प्राप्त कर सकता हूं?

 उ4: आप सामुदायिक मंच से समर्थन प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15).

### Q5: क्या आप .NET के लिए Aspose.Tasks के लिए अस्थायी लाइसेंस प्रदान करते हैं?

 A5: हाँ, अस्थायी लाइसेंस उपलब्ध हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
