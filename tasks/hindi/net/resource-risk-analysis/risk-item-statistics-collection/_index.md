---
title: Aspose.Tasks में MS प्रोजेक्ट जोखिम आइटम सांख्यिकी एकत्रित करें
linktitle: Aspose.Tasks में जोखिम मद सांख्यिकी का संग्रह
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइलों से जोखिम आइटम आँकड़े एकत्र करना सीखें। अपनी परियोजना प्रबंधन क्षमताओं को बढ़ाएँ।
weight: 22
url: /hi/net/resource-risk-analysis/risk-item-statistics-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में MS प्रोजेक्ट जोखिम आइटम सांख्यिकी एकत्रित करें

## परिचय
इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइलों से जोखिम आइटम आँकड़े कैसे एकत्र करें। यह लाइब्रेरी जोखिम मूल्यांकन और सांख्यिकीय विश्लेषण सहित परियोजना डेटा का विश्लेषण करने के लिए शक्तिशाली कार्यक्षमता प्रदान करती है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:
1. .NET के लिए Aspose.Tasks: Aspose.Tasks लाइब्रेरी डाउनलोड और इंस्टॉल करें। आप इसे यहां से प्राप्त कर सकते हैं[डाउनलोड पेज](https://releases.aspose.com/tasks/net/).
2. विकास परिवेश: .NET प्रोग्रामिंग के लिए एक विकास परिवेश स्थापित करें।

## नामस्थान आयात करें
कोडिंग शुरू करने से पहले, अपने प्रोजेक्ट में आवश्यक नेमस्पेस आयात करना सुनिश्चित करें:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
सबसे पहले, आपको एमएस प्रोजेक्ट फ़ाइल को अपने एप्लिकेशन में लोड करना होगा। यहां बताया गया है कि आप इसे कैसे हासिल कर सकते हैं:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## चरण 2: जोखिम विश्लेषण सेटिंग्स को परिभाषित करें
जैसा कि नीचे दिखाया गया है, पुनरावृत्तियों की संख्या सहित जोखिम विश्लेषण सेटिंग्स आरंभ करें:
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## चरण 3: एक जोखिम पैटर्न प्रारंभ करें
विश्लेषण के लिए एक जोखिम पैटर्न स्थापित करें, वितरण प्रकार, आशावादी और निराशावादी प्रतिशत और आत्मविश्वास स्तर निर्दिष्ट करें:
```csharp
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
## चरण 4: जोखिम विश्लेषण करें
 त्वरित करें`RiskAnalyzer` क्लास करें और प्रोजेक्ट का विश्लेषण करें:
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## चरण 5: सांख्यिकी पुनर्प्राप्त करें
विश्लेषण परिणाम से जोखिम मद के आँकड़े, जैसे शीघ्र समापन, पुनः प्राप्त करें:
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## चरण 6: सांख्यिकी प्रिंट करें
आँकड़ों पर पुनरावृति करें और विवरण प्रिंट करें:
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //अन्य प्रासंगिक आँकड़े मुद्रित करें...
}
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि MS प्रोजेक्ट फ़ाइलों से जोखिम आइटम आँकड़े एकत्र करने के लिए .NET के लिए Aspose.Tasks का उपयोग कैसे करें। इन चरणों का पालन करके, आप प्रभावी ढंग से परियोजना डेटा का विश्लेषण कर सकते हैं और संभावित जोखिमों का आकलन कर सकते हैं, बेहतर निर्णय लेने और परियोजना प्रबंधन में सहायता कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या Aspose.Tasks बड़ी MS प्रोजेक्ट फ़ाइलों को संभाल सकता है?
उत्तर: हाँ, Aspose.Tasks विश्वसनीय प्रदर्शन और स्केलेबिलिटी प्रदान करते हुए बड़ी MS प्रोजेक्ट फ़ाइलों को कुशलतापूर्वक संभालने में सक्षम है।
### प्रश्न: क्या Aspose.Tasks .mpp के अलावा अन्य प्रोजेक्ट फ़ाइल स्वरूपों का समर्थन करता है?
उत्तर: हाँ, Aspose.Tasks XML और MPT सहित विभिन्न प्रोजेक्ट फ़ाइल स्वरूपों का समर्थन करता है।
### प्रश्न: क्या Aspose.Tasks उद्यम-स्तरीय परियोजना प्रबंधन अनुप्रयोगों के लिए उपयुक्त है?
उत्तर: बिल्कुल, Aspose.Tasks को एंटरप्राइज़-स्तरीय परियोजना प्रबंधन अनुप्रयोगों की मांगों को पूरा करने, मजबूत सुविधाएँ और व्यापक दस्तावेज़ीकरण प्रदान करने के लिए डिज़ाइन किया गया है।
### प्रश्न: क्या मैं Aspose.Tasks में जोखिम विश्लेषण सेटिंग्स को अनुकूलित कर सकता हूँ?
उत्तर: हां, Aspose.Tasks आपकी विशिष्ट परियोजना आवश्यकताओं और परिदृश्यों के अनुरूप जोखिम विश्लेषण सेटिंग्स को कॉन्फ़िगर करने में लचीलापन प्रदान करता है।
### प्रश्न: क्या Aspose.Tasks उपयोगकर्ताओं के लिए तकनीकी सहायता उपलब्ध है?
 उत्तर: हाँ, Aspose.Tasks उपयोगकर्ता Aspose के माध्यम से तकनीकी सहायता प्राप्त कर सकते हैं[मंचों](https://forum.aspose.com/c/tasks/15), जहां वे प्रश्न पूछ सकते हैं, मुद्दों की रिपोर्ट कर सकते हैं और समुदाय के साथ बातचीत कर सकते हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
