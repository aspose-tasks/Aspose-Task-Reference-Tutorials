---
title: Aspose.Tasks में जोखिम वाली वस्तुओं के आँकड़े
linktitle: Aspose.Tasks में जोखिम वाली वस्तुओं के आँकड़े
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइलों में जोखिम विश्लेषण की शक्ति को अनलॉक करें। अंतर्दृष्टि प्राप्त करें, अनिश्चितताओं को कम करें और परियोजना को सहजता से सफलता प्रदान करें।
type: docs
weight: 21
url: /hi/net/resource-risk-analysis/risk-item-statistics/
---
## परिचय
क्या आप .NET के लिए Aspose.Tasks का उपयोग करके अपने प्रोजेक्ट प्रबंधन कौशल को बढ़ाना चाह रहे हैं? एमएस प्रोजेक्ट फ़ाइलों में जोखिम वस्तुओं के आंकड़े प्राप्त करने पर हमारे चरण-दर-चरण ट्यूटोरियल के साथ जोखिम विश्लेषण के क्षेत्र में गहराई से उतरें। Aspose.Tasks की शक्तिशाली क्षमताओं का लाभ उठाकर, आप परियोजना अनिश्चितताओं में अमूल्य अंतर्दृष्टि प्राप्त कर सकते हैं और जोखिमों को प्रभावी ढंग से कम करने के लिए सूचित निर्णय ले सकते हैं।
## आवश्यक शर्तें
इससे पहले कि हम इस यात्रा पर निकलें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1.  .NET लाइब्रेरी के लिए Aspose.Tasks: लाइब्रेरी को डाउनलोड और इंस्टॉल करें[.NET दस्तावेज़ीकरण के लिए Aspose.Tasks](https://reference.aspose.com/tasks/net/). यह लाइब्रेरी आपको एमएस प्रोजेक्ट फ़ाइलों को प्रोग्रामेटिक रूप से हेरफेर करने के लिए मजबूत टूल से लैस करती है।
2. .NET विकास वातावरण: अपने प्रोजेक्ट्स में Aspose.Tasks के निर्बाध एकीकरण की सुविधा के लिए विजुअल स्टूडियो या अपनी पसंद के किसी अन्य IDE सहित अपना .NET विकास वातावरण स्थापित करें।

## नामस्थान आयात करें
Aspose.Tasks की कार्यक्षमताओं का उपयोग करने के लिए अपने प्रोजेक्ट में आवश्यक नामस्थान शामिल करें:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## चरण 1: डेटा निर्देशिका को परिभाषित करें
```csharp
String DataDir = "Your Document Directory";
```
 प्रतिस्थापित करना सुनिश्चित करें`"Your Document Directory"` आपकी दस्तावेज़ निर्देशिका के पथ के साथ जहां आपकी MS प्रोजेक्ट फ़ाइलें स्थित हैं।
## चरण 2: जोखिम विश्लेषण सेटिंग्स कॉन्फ़िगर करें
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 समायोजित`IterationsCount`जोखिम विश्लेषण की सटीकता को नियंत्रित करने के लिए आपकी परियोजना आवश्यकताओं के आधार पर पैरामीटर।
## चरण 3: एमएस प्रोजेक्ट फ़ाइल लोड करें
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 वांछित एमएस प्रोजेक्ट फ़ाइल को इसमें लोड करें`project` आगे के विश्लेषण के लिए वस्तु.
## चरण 4: कार्य को परिभाषित करें और जोखिम पैटर्न आरंभ करें
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
जोखिम विश्लेषण के लिए कार्य निर्दिष्ट करें और वितरण प्रकार, आशावादी और निराशावादी अवधि और आत्मविश्वास स्तर जैसे उचित मापदंडों के साथ जोखिम पैटर्न को कॉन्फ़िगर करें।
## चरण 5: परियोजना जोखिमों का विश्लेषण करें
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
परिभाषित सेटिंग्स और प्रोजेक्ट डेटा का उपयोग करके जोखिम विश्लेषण प्रक्रिया शुरू करें।
## चरण 6: आंकड़े पुनर्प्राप्त करें और प्रदर्शित करें
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
Console.WriteLine("Short statistic: " + statistics);
Console.WriteLine();
Console.WriteLine("Statistic details: ");
Console.WriteLine("Item Type: {0}", statistics.ItemType);
Console.WriteLine("Expected value: {0}", statistics.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", statistics.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", statistics.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", statistics.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", statistics.GetPercentile(90));
Console.WriteLine("Minimum: {0}", statistics.Minimum);
Console.WriteLine("Maximum: {0}", statistics.Maximum);
```
अपेक्षित मूल्य, मानक विचलन, प्रतिशत, न्यूनतम और अधिकतम मूल्यों सहित एमएस प्रोजेक्ट फ़ाइल में जोखिम वस्तुओं से संबंधित विभिन्न सांख्यिकीय मीट्रिक पुनर्प्राप्त और प्रदर्शित करें।

## निष्कर्ष
अंत में, .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइलों में जोखिम विश्लेषण में महारत हासिल करने से परियोजना प्रबंधकों और हितधारकों के लिए संभावनाओं का एक दायरा खुल जाता है। हमारे व्यापक ट्यूटोरियल का अनुसरण करके, आप आत्मविश्वास के साथ अनिश्चितताओं से पार पा सकते हैं और सफल परियोजना परिणाम सुनिश्चित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं विस्तारित कार्यक्षमता के लिए Aspose.Tasks को अन्य .NET लाइब्रेरीज़ के साथ एकीकृत कर सकता हूँ?
बिल्कुल! Aspose.Tasks विभिन्न .NET पुस्तकालयों के साथ निर्बाध रूप से एकीकृत होता है, जिससे आप अपनी परियोजना आवश्यकताओं के अनुसार इसकी क्षमताओं को बढ़ा सकते हैं।
### क्या .NET के लिए Aspose.Tasks का कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप Aspose.Tasks तक पहुंच कर इसकी विशेषताओं का पता लगा सकते हैं[मुफ्त परीक्षण](https://releases.aspose.com/) हमारी वेबसाइट पर उपलब्ध है।
### Aspose.Tasks के लिए अद्यतन और संवर्द्धन कितनी बार जारी किए जाते हैं?
हम समय-समय पर अपडेट और संवर्द्धन जारी करके Aspose.Tasks में लगातार सुधार करने का प्रयास करते हैं, यह सुनिश्चित करते हुए कि आपके पास हमेशा नवीनतम सुविधाओं और अनुकूलन तक पहुंच हो।
### क्या मैं Aspose.Tasks के लिए तकनीकी सहायता प्राप्त कर सकता हूँ?
निश्चित रूप से! हमारी समर्पित सहायता टीम आसानी से उपलब्ध है[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) आपकी कार्यान्वयन यात्रा के दौरान आपके सामने आने वाले किसी भी प्रश्न या चुनौती में आपकी सहायता करने के लिए।
### क्या आप अल्पकालिक परियोजनाओं के लिए अस्थायी लाइसेंस प्रदान करते हैं?
 हाँ, यदि आपको किसी अल्पकालिक परियोजना के लिए Aspose.Tasks की आवश्यकता है, तो आप हमारी सुविधा का लाभ उठा सकते हैं[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) बिना किसी दीर्घकालिक प्रतिबद्धता के आपकी लाइसेंसिंग आवश्यकताओं को पूरा करने का विकल्प।