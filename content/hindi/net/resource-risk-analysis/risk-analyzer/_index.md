---
title: Aspose.Tasks के साथ एमएस प्रोजेक्ट जोखिमों का विश्लेषण
linktitle: Aspose के साथ जोखिमों का विश्लेषण। कार्य
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks के साथ MS प्रोजेक्ट जोखिमों का कुशलतापूर्वक विश्लेषण करना सीखें। व्यापक जोखिम प्रबंधन के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 20
url: /hi/net/resource-risk-analysis/risk-analyzer/
---
## परिचय
सफल परियोजना वितरण सुनिश्चित करने के लिए परियोजना प्रबंधन में जोखिमों का प्रबंधन करना आवश्यक है। .NET के लिए Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों में जोखिमों का विश्लेषण और उन्हें कम करने के लिए शक्तिशाली उपकरण प्रदान करता है। इस ट्यूटोरियल में, हम यह पता लगाएंगे कि Aspose का उपयोग करके MS प्रोजेक्ट जोखिमों का विश्लेषण कैसे करें। कार्य, चरण दर चरण।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. विजुअल स्टूडियो: सुनिश्चित करें कि आपके सिस्टम पर विजुअल स्टूडियो स्थापित है।
2.  .NET के लिए Aspose.Tasks: .NET के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/net/).
3. माइक्रोसॉफ्ट प्रोजेक्ट फ़ाइल: एक एमएस प्रोजेक्ट फ़ाइल तैयार करें जिसका आप जोखिमों के लिए विश्लेषण करना चाहते हैं।

## नामस्थान आयात करें
अपने C# कोड में, आवश्यक नामस्थान शामिल करें:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## चरण 1: जोखिम विश्लेषण सेटिंग्स प्रारंभ करें
जोखिम विश्लेषण के लिए पैरामीटर सेट करें, जैसे पुनरावृत्तियों की संख्या और जोखिम पैटर्न।
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## चरण 2: एमएस प्रोजेक्ट फ़ाइल लोड करें
वह एमएस प्रोजेक्ट फ़ाइल लोड करें जिसका आप जोखिमों के लिए विश्लेषण करना चाहते हैं।
```csharp
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## चरण 3: कार्य और जोखिम पैटर्न को परिभाषित करें
कार्य निर्दिष्ट करें और विश्लेषण के लिए जोखिम पैटर्न परिभाषित करें।
```csharp
var task = project.RootTask.Children.GetById(17);
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
## चरण 4: परियोजना जोखिमों का विश्लेषण करें
परियोजना पर जोखिम विश्लेषण करें.
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
var earlyFinish = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
```
## चरण 5: विश्लेषण परिणाम पुनः प्राप्त करें
अपेक्षित मान और प्रतिशत जैसे विश्लेषण परिणाम पुनर्प्राप्त करें और प्रदर्शित करें।
```csharp
Console.WriteLine("Expected value: {0}", earlyFinish.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", earlyFinish.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", earlyFinish.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", earlyFinish.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", earlyFinish.GetPercentile(90));
Console.WriteLine("Minimum: {0}", earlyFinish.Minimum);
Console.WriteLine("Maximum: {0}", earlyFinish.Maximum);
```
## चरण 6: विश्लेषण सेटिंग्स समायोजित करें (वैकल्पिक)
यदि आवश्यक हो तो विश्लेषण सेटिंग्स संशोधित करें और विश्लेषण फिर से चलाएँ।
```csharp
settings = new RiskAnalysisSettings
{
    IterationsCount = 300
};
analyzer.Settings = settings;
analysisResult = analyzer.Analyze(project);
earlyFinish = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
```
## चरण 7: विश्लेषण रिपोर्ट सहेजें
उदाहरण के लिए, विश्लेषण रिपोर्ट को पीडीएफ फ़ाइल के रूप में सहेजें।
```csharp
analysisResult.SaveReport(DataDir + "AnalysisReport_out.pdf");
```

## निष्कर्ष
अंत में, .NET के लिए Aspose.Tasks एमएस प्रोजेक्ट जोखिमों का विश्लेषण करने के लिए मजबूत क्षमताएं प्रदान करता है, जिससे प्रोजेक्ट प्रबंधकों को सूचित निर्णय लेने और संभावित मुद्दों को कम करने की अनुमति मिलती है। इस ट्यूटोरियल में उल्लिखित चरणों का पालन करके, आप आत्मविश्वास के साथ प्रोजेक्ट जोखिमों को प्रबंधित करने के लिए Aspose.कार्यों का प्रभावी ढंग से उपयोग कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं अन्य प्रोजेक्ट प्रबंधन टूल के साथ Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: हाँ, Aspose। कार्य विभिन्न परियोजना प्रबंधन प्लेटफार्मों और उपकरणों के साथ एकीकरण का समर्थन करता है।
### प्रश्न: क्या Aspose.Tasks उद्यम-स्तरीय परियोजनाओं के लिए उपयुक्त है?
उत्तर: बिल्कुल, Aspose। कार्य छोटे पैमाने और उद्यम स्तर की परियोजनाओं दोनों की जरूरतों को पूरा करने के लिए डिज़ाइन किया गया है।
### प्रश्न: क्या मैं Aspose.Tasks में जोखिम विश्लेषण मापदंडों को अनुकूलित कर सकता हूँ?
उत्तर: हां, आप अपने प्रोजेक्ट की विशिष्ट आवश्यकताओं के अनुसार जोखिम विश्लेषण सेटिंग्स को तैयार कर सकते हैं।
### प्रश्न: क्या Aspose.Tasks एकाधिक प्रोग्रामिंग भाषाओं का समर्थन करता है?
उत्तर: Aspose.Tasks मुख्य रूप से .NET भाषाओं को लक्षित करता है, लेकिन यह जावा के लिए भी समर्थन प्रदान करता है।
### प्रश्न: मुझे Aspose.Tasks के लिए अतिरिक्त सहायता कहां मिल सकती है?
 उ: आप Aspose.Tasks दस्तावेज़ का पता लगा सकते हैं या सहायता पर जा सकते हैं[मंच]( https://forum.aspose.com/c/tasks/15) सहायता के लिए।