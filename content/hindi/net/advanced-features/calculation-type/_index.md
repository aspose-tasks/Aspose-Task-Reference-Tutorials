---
title: Aspose.Tasks में गणना प्रकार
linktitle: Aspose.Tasks में गणना प्रकार
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks लाइब्रेरी में गणना प्रकार के साथ .NET परियोजनाओं में मूल्य गणना को अनुकूलित करना सीखें।
type: docs
weight: 30
url: /hi/net/advanced-features/calculation-type/
---
## परिचय

इस ट्यूटोरियल में, हम .NET के लिए Aspose.Tasks में गणना प्रकार सुविधा का पता लगाएंगे। Aspose.Tasks एक शक्तिशाली लाइब्रेरी है जो .NET डेवलपर्स को उनके सिस्टम पर स्थापित Microsoft प्रोजेक्ट की आवश्यकता के बिना Microsoft प्रोजेक्ट फ़ाइलों के साथ काम करने में सक्षम बनाती है। गणना प्रकार हमें यह परिभाषित करने की अनुमति देता है कि किसी प्रोजेक्ट के भीतर कार्यों और सारांश कार्यों के लिए मूल्यों की गणना कैसे की जाती है।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

1. C# और .NET फ्रेमवर्क का बुनियादी ज्ञान।
2. आपके सिस्टम पर विज़ुअल स्टूडियो स्थापित है।
3.  .NET लाइब्रेरी के लिए Aspose.Tasks स्थापित। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
4.  संदर्भ के लिए .NET दस्तावेज़ के लिए Aspose.Tasks तक पहुंच उपलब्ध है[यहाँ](https://reference.aspose.com/tasks/net/).

## नामस्थान आयात करें

उदाहरण में गोता लगाने से पहले, आवश्यक नामस्थान आयात करना सुनिश्चित करें:

```csharp
using Aspose.Tasks;
using System;


```

## चरण 1: एक नया प्रोजेक्ट बनाएं

सबसे पहले, आइए एक नया प्रोजेक्ट ऑब्जेक्ट बनाएं:

```csharp
var project = new Project();
```

## चरण 2: एक कार्य जोड़ें

अब, आइए अपने प्रोजेक्ट में एक कार्य जोड़ें:

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## चरण 3: विस्तारित विशेषता के लिए गणना प्रकार को परिभाषित करें

हम गणना प्रकार को फॉर्मूला पर सेट करके एक विस्तारित विशेषता परिभाषा बनाएंगे:

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## चरण 4: सारांश पंक्तियों के लिए गणना प्रकार को परिभाषित करें

इसके बाद, हम एक और विस्तारित विशेषता परिभाषा बनाएंगे जहां सारांश कार्यों के मूल्यों की गणना औसत रोलअप प्रकार का उपयोग करके की जाती है:

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया है कि .NET के लिए Aspose.Tasks में गणना प्रकार के साथ कैसे काम किया जाए। विस्तारित विशेषताओं के लिए गणना प्रकारों को परिभाषित करके, हम अनुकूलित कर सकते हैं कि किसी प्रोजेक्ट के भीतर कार्यों और सारांश कार्यों के लिए मूल्यों की गणना कैसे की जाती है, जिससे अधिक लचीलापन और नियंत्रण मिलता है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: Aspose.Tasks में गणना प्रकार क्या है?

A1: Aspose.Tasks में गणना प्रकार यह निर्धारित करता है कि किसी प्रोजेक्ट के भीतर कार्यों और सारांश कार्यों के लिए मूल्यों की गणना कैसे की जाती है, फॉर्मूला और रोलअप जैसे विकल्प पेश करते हैं।

### Q2: मैं किसी विस्तारित विशेषता के लिए गणना प्रकार कैसे सेट करूं?

A2: आप किसी विस्तारित विशेषता के लिए गणना प्रकार की संपत्ति को तदनुसार परिभाषित करके गणना प्रकार सेट कर सकते हैं।

### Q3: क्या मैं किसी प्रोजेक्ट में सारांश पंक्तियों के लिए गणना प्रकार को अनुकूलित कर सकता हूँ?

A3: हां, Aspose.Tasks आपको सारांश पंक्तियों के लिए गणना प्रकार निर्दिष्ट करने की अनुमति देता है, जिससे आप अपनी आवश्यकताओं के आधार पर मूल्य गणना को अनुकूलित कर सकते हैं।

### Q4: क्या सारांश कार्य गणना के लिए विभिन्न रोलअप प्रकार उपलब्ध हैं?

A4: हां, Aspose.Tasks सारांश कार्यों के मूल्यों की गणना के लिए औसत, योग और गणना जैसे विभिन्न रोलअप प्रकार प्रदान करता है।

### Q5: मुझे .NET के लिए Aspose.Tasks पर और अधिक संसाधन कहां मिल सकते हैं?

 A5: आप पर उपलब्ध दस्तावेज़ीकरण और सामुदायिक सहायता मंचों का पता लगा सकते हैं[.NET के लिए Aspose.Tasks](https://reference.aspose.com/tasks/net/) व्यापक मार्गदर्शन और सहायता के लिए।