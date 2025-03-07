---
title: Aspose.Tasks में MS प्रोजेक्ट आउटलाइन कोड हैंडलिंग परिभाषाएँ
linktitle: Aspose.Tasks में रूपरेखा कोड परिभाषाओं को संभालना
second_title: Aspose.Tasks .NET API
description: जानें कि .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट आउटलाइन कोड परिभाषाओं को कैसे संभालना है, जो आपके प्रोजेक्ट प्रबंधन अनुप्रयोगों को सशक्त बनाता है।
weight: 12
url: /hi/net/outline-code-page-settings/outline-code-definitions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में MS प्रोजेक्ट आउटलाइन कोड हैंडलिंग परिभाषाएँ

## परिचय
माइक्रोसॉफ्ट प्रोजेक्ट परियोजनाओं के प्रबंधन के लिए एक शक्तिशाली उपकरण है, और .NET के लिए Aspose.Tasks प्रोजेक्ट फ़ाइलों को प्रोग्रामेटिक रूप से हेरफेर करने के लिए व्यापक समर्थन प्रदान करता है। परियोजना प्रबंधन का एक आवश्यक पहलू रूपरेखा कोड का उपयोग करके कार्यों को व्यवस्थित करना है। इस ट्यूटोरियल में, हम जानेंगे कि .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट आउटलाइन कोड परिभाषाओं को कैसे प्रबंधित किया जाए।
## आवश्यक शर्तें
इससे पहले कि हम कार्यान्वयन में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
### 1. .NET के लिए Aspose.Tasks की स्थापना
 सुनिश्चित करें कि आपने अपने विकास परिवेश में .NET के लिए Aspose.Tasks स्थापित किया है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
### 2. C# और .NET फ्रेमवर्क की बुनियादी समझ
अपने आप को C# प्रोग्रामिंग भाषा और .NET फ्रेमवर्क से परिचित कराएं क्योंकि इस ट्यूटोरियल के लिए मध्यवर्ती स्तर के C# ज्ञान की आवश्यकता होती है।
### 3. एकीकृत विकास पर्यावरण (आईडीई)
कोडिंग और डिबगिंग के लिए अपने सिस्टम पर विज़ुअल स्टूडियो जैसा एक आईडीई स्थापित करें।
## नामस्थान आयात करें
इससे पहले कि हम कोडिंग शुरू करें, आइए .NET के लिए Aspose.Tasks के साथ काम करने के लिए आवश्यक नेमस्पेस आयात करें।
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
अब, स्पष्ट समझ के लिए दिए गए उदाहरण को कई चरणों में तोड़ते हैं।
## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
सबसे पहले, हमें एमएस प्रोजेक्ट फ़ाइल को अपने एप्लिकेशन में लोड करना होगा।
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## चरण 2: रूपरेखा कोड परिभाषा बनाएं
अब, आइए एक नई रूपरेखा कोड परिभाषा बनाएं।
```csharp
var outline = new OutlineCodeDefinition();
```
## चरण 3: फ़ील्ड संख्या और नाम सेट करें
आउटलाइन कोड के लिए फ़ील्ड संख्या और नाम सेट करें।
```csharp
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.FieldName = "Outline Code1";
```
## चरण 4: GUID और अन्य गुण सेट करें
GUID और आउटलाइन कोड के अन्य गुण सेट करें।
```csharp
outline.Guid = "e6afac06-0d86-4359-a96c-db705e3d2ca8";
outline.LeafOnly = false;
outline.Alias = "My Outline Code";
outline.PhoneticAlias = "Outline Code";
outline.AllLevelsRequired = true;
outline.Enterprise = false;
outline.EnterpriseOutlineCodeAlias = 0;
```
## चरण 5: आउटलाइन मास्क जोड़ें
आउटलाइन कोड में एक आउटलाइन मास्क जोड़ें।
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
## चरण 6: अन्य गुण सेट करें
आउटलाइन कोड के अतिरिक्त गुण सेट करें.
```csharp
outline.OnlyTableValuesAllowed = false;
outline.ResourceSubstitutionEnabled = false;
outline.ShowIndent = false;
```
## चरण 7: रूपरेखा मूल्य जोड़ें
अंत में, आइए आउटलाइन कोड में एक आउटलाइन मान जोड़ें।
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
outline.Values.Add(value);
```
## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट आउटलाइन कोड परिभाषाओं को कैसे संभालना है। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप प्रोग्रामेटिक रूप से अपनी प्रोजेक्ट फ़ाइलों में रूपरेखा कोड में कुशलतापूर्वक हेरफेर कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### Q1: क्या मैं MS प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों के साथ .NET के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: हाँ, .NET के लिए Aspose.Tasks MPP और XML प्रारूपों सहित MS प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों का समर्थन करता है।
### Q2: क्या .NET के लिए Aspose.Tasks .NET कोर के साथ संगत है?
उत्तर: हाँ, .NET के लिए Aspose.Tasks .NET कोर के साथ संगत है, जो आपको क्रॉस-प्लेटफ़ॉर्म एप्लिकेशन विकसित करने की अनुमति देता है।
### Q3: क्या मैं .NET के लिए Aspose.Tasks का उपयोग करके संसाधन असाइनमेंट में हेरफेर कर सकता हूँ?
उत्तर: हाँ, .NET के लिए Aspose.Tasks संसाधन असाइनमेंट में हेरफेर करने के लिए व्यापक सुविधाएँ प्रदान करता है, जिसमें असाइनमेंट जोड़ना, अपडेट करना और हटाना शामिल है।
### Q4: क्या .NET के लिए Aspose.Tasks MS प्रोजेक्ट फ़ाइलों से कस्टम फ़ील्ड पढ़ने का समर्थन करता है?
उत्तर: बिल्कुल, .NET के लिए Aspose.Tasks MS प्रोजेक्ट फ़ाइलों से आउटलाइन कोड सहित कस्टम फ़ील्ड को पढ़ने और लिखने का समर्थन करता है।
### Q5: क्या .NET के लिए Aspose.Tasks के लिए कोई सामुदायिक मंच है?
 उत्तर: हां, आप .NET के लिए Aspose.Tasks के सामुदायिक मंच में शामिल हो सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15) प्रश्न पूछने, ज्ञान साझा करने और अन्य डेवलपर्स के साथ सहयोग करने के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
