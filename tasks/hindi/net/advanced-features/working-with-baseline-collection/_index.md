---
title: Aspose.Tasks में बेसलाइन संग्रह के साथ कार्य करना
linktitle: Aspose.Tasks में बेसलाइन संग्रह के साथ कार्य करना
second_title: Aspose.Tasks .NET API
description: जानें कि .NET के लिए Aspose.Tasks में बेसलाइन को कुशलतापूर्वक कैसे प्रबंधित किया जाए। चरण-दर-चरण मार्गदर्शन के लिए हमारे व्यापक ट्यूटोरियल का अनुसरण करें।
weight: 20
url: /hi/net/advanced-features/working-with-baseline-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में बेसलाइन संग्रह के साथ कार्य करना

## परिचय

.NET के लिए Aspose.Tasks एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को उनके .NET अनुप्रयोगों में Microsoft प्रोजेक्ट फ़ाइलों के साथ निर्बाध रूप से काम करने में सक्षम बनाती है। इसकी कई विशेषताओं में से, यह परियोजनाओं के भीतर बेसलाइन के प्रबंधन के लिए मजबूत समर्थन प्रदान करता है। परियोजना प्रबंधन के लिए बेसलाइन आवश्यक हैं क्योंकि वे आपको मूल परियोजना योजना की वर्तमान स्थिति के साथ तुलना करने की अनुमति देते हैं, जिससे परियोजना की प्रगति की बेहतर ट्रैकिंग और विश्लेषण संभव हो पाता है।

## आवश्यक शर्तें

इससे पहले कि हम Aspose.Tasks में बेसलाइन संग्रह के साथ काम करें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

1. विजुअल स्टूडियो: अपने सिस्टम पर विजुअल स्टूडियो आईडीई स्थापित करें।
2.  .NET के लिए Aspose.Tasks: .NET लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें।[लिंक को डाउनलोड करें](https://releases.aspose.com/tasks/net/).
3. C# की बुनियादी समझ: C# प्रोग्रामिंग भाषा से खुद को परिचित करें।
4. Microsoft प्रोजेक्ट फ़ाइल: परीक्षण उद्देश्यों के लिए Microsoft प्रोजेक्ट फ़ाइल (.mpp) तैयार रखें।

## नामस्थान आयात करें

Aspose.Tasks में बेसलाइन संग्रह के साथ काम करना शुरू करने के लिए, आपको निम्नलिखित नामस्थान आयात करने की आवश्यकता है:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

अब, आइए प्रत्येक उदाहरण को कई चरणों में तोड़ें:

## चरण 1: प्रोजेक्ट फ़ाइल लोड करें

सबसे पहले, Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट फ़ाइल लोड करें:

```csharp
// वें दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## चरण 2: संसाधन प्राप्त करें

इसके बाद, प्रोजेक्ट से वांछित संसाधन पुनः प्राप्त करें:

```csharp
var resource = project.Resources.GetByUid(1);
```

## चरण 3: आधारभूत जानकारी प्रदर्शित करें

अब, संसाधन से जुड़ी आधार रेखाओं के बारे में जानकारी प्रदर्शित करें:

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## चरण 4: आधार रेखाओं के माध्यम से पुनरावृति करें

संसाधन से जुड़ी प्रत्येक आधार रेखा को दोहराएँ और प्रासंगिक जानकारी प्रिंट करें:

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## चरण 5: बेसलाइन हटाएँ

संसाधन से संबद्ध सभी आधार रेखाएँ हटाएँ:

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया कि .NET के लिए Aspose.Tasks में बेसलाइन संग्रह के साथ कैसे काम किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप आसानी से अपने .NET अनुप्रयोगों के भीतर बेसलाइन प्रबंधित कर सकते हैं, जिससे प्रभावी प्रोजेक्ट ट्रैकिंग और विश्लेषण की अनुमति मिलती है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या Aspose.Tasks बड़ी परियोजना फ़ाइलों को संभाल सकता है?

A1: हाँ, Aspose.Tasks को सुचारू प्रदर्शन सुनिश्चित करते हुए बड़ी प्रोजेक्ट फ़ाइलों को कुशलतापूर्वक संभालने के लिए अनुकूलित किया गया है।

### Q2: क्या Aspose.Tasks Microsoft प्रोजेक्ट के सभी संस्करणों के साथ संगत है?

A2: Aspose.Tasks विभिन्न वातावरणों में अनुकूलता सुनिश्चित करते हुए, Microsoft प्रोजेक्ट के विभिन्न संस्करणों का समर्थन करता है।

### Q3: क्या मैं Aspose.Tasks में बेसलाइन को कस्टमाइज़ कर सकता हूँ?

उ3: हाँ, आप .NET के लिए Aspose.Tasks का उपयोग करके अपनी परियोजना आवश्यकताओं के अनुसार बेसलाइन को अनुकूलित कर सकते हैं।

### Q4: क्या Aspose.Tasks क्लाउड प्लेटफ़ॉर्म के लिए समर्थन प्रदान करता है?

A4: हां, Aspose.Tasks लोकप्रिय क्लाउड प्लेटफ़ॉर्म के साथ एकीकरण के लिए समर्थन प्रदान करता है, जो तैनाती में लचीलापन प्रदान करता है।

### Q5: क्या Aspose.Tasks उपयोगकर्ताओं के लिए मदद मांगने और ज्ञान साझा करने के लिए कोई सामुदायिक मंच है?

 A5: हाँ, आप यहाँ जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) समुदाय के साथ जुड़ने और विशेषज्ञों से सहायता प्राप्त करने के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
