---
title: Aspose.Tasks .NET में चरण-दर-चरण WBS कोड कॉन्फ़िगरेशन
linktitle: Aspose.Tasks में WBS कोड मास्क कॉन्फ़िगर करना
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks का उपयोग करके .NET प्रोजेक्ट में चरण-दर-चरण WBS कोड मास्क कॉन्फ़िगरेशन का अन्वेषण करें। परियोजना प्रबंधन क्षमताओं को सहजता से बढ़ाएं।
weight: 14
url: /hi/net/view-wbs-code-configuration/wbs-code-masks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks .NET में चरण-दर-चरण WBS कोड कॉन्फ़िगरेशन

## परिचय
.NET के लिए Aspose.Tasks एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को .NET अनुप्रयोगों में प्रोजेक्ट प्रबंधन डेटा में कुशलतापूर्वक हेरफेर करने का अधिकार देती है। इस ट्यूटोरियल में, हम Aspose.Tasks का उपयोग करके वर्क ब्रेकडाउन स्ट्रक्चर (WBS) कोड मास्क को कॉन्फ़िगर करने की प्रक्रिया का पता लगाएंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
-  .NET लाइब्रेरी के लिए Aspose.Tasks: लाइब्रेरी को यहां से डाउनलोड और इंस्टॉल करें[.NET दस्तावेज़ीकरण के लिए Aspose.कार्य](https://reference.aspose.com/tasks/net/).
- विकास परिवेश: सुनिश्चित करें कि आपके पास एक कार्यशील .NET विकास परिवेश स्थापित है।
- दस्तावेज़ निर्देशिका: प्रोजेक्ट फ़ाइलों को संग्रहीत करने के लिए अपने सिस्टम पर एक निर्देशिका चुनें।
## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में, Aspose.Tasks के साथ काम करने के लिए आवश्यक नामस्थान शामिल करें:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## चरण 1: एक प्रोजेक्ट इंस्टेंस बनाएं
एक नया प्रोजेक्ट इंस्टेंस बनाकर शुरुआत करें:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## चरण 2: WBS कोड परिभाषा को परिभाषित करें
अपने प्रोजेक्ट के लिए WBS कोड परिभाषा सेट करें:
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## चरण 3: WBS कोड मास्क जोड़ें
WBS कोड मास्क को परिभाषित करें और उन्हें प्रोजेक्ट में जोड़ें:
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## चरण 4: कार्य बनाएँ
प्रोजेक्ट में कार्य जोड़ें:
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## चरण 5: पुनर्गणना करें
यह सुनिश्चित करने के लिए प्रोजेक्ट की पुनर्गणना करें कि WBS कोड सही ढंग से लागू किए गए हैं:
```csharp
project.Recalculate();
```
## चरण 6: WBS मास्क जानकारी प्रदर्शित करें
कंसोल पर WBS मास्क के बारे में आउटपुट जानकारी:
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## चरण 7: प्रोजेक्ट सहेजें
जोड़े गए WBS कोड के साथ प्रोजेक्ट को सहेजें:
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
बधाई हो! आपने अपने Aspose.Tasks प्रोजेक्ट में WBS कोड मास्क को सफलतापूर्वक कॉन्फ़िगर कर लिया है।
## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Tasks का उपयोग करके WBS कोड मास्क को कॉन्फ़िगर करने की चरण-दर-चरण प्रक्रिया का पता लगाया है। यह शक्तिशाली लाइब्रेरी डेवलपर्स को उनके .NET अनुप्रयोगों के भीतर परियोजना प्रबंधन क्षमताओं को बढ़ाने का एक सहज तरीका प्रदान करती है।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Tasks का निःशुल्क उपयोग कर सकता हूँ?
 Aspose.Tasks एक निःशुल्क परीक्षण प्रदान करता है, जिसे आप डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मुझे अतिरिक्त सहायता कहां मिल सकती है?
 दौरा करना[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) सामुदायिक समर्थन के लिए.
### मैं अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?
 आपको अस्थायी लाइसेंस मिल सकता है[यहाँ](https://purchase.aspose.com/temporary-license/).
### क्या कोई विस्तृत दस्तावेज उपलब्ध है?
 हाँ, व्यापक दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/tasks/net/).
### मैं Aspose.Tasks कहाँ से खरीद सकता हूँ?
 Aspose.कार्य खरीदें[यहाँ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
