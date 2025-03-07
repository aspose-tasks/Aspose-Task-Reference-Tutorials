---
title: Aspose.Tasks के साथ एमएस प्रोजेक्ट रूपरेखा मूल्यों में महारत हासिल करना
linktitle: Aspose.Tasks में रूपरेखा मूल्यों का प्रबंधन
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट रूपरेखा मानों को कुशलतापूर्वक प्रबंधित करना सीखें। प्रोजेक्ट की रूपरेखा को आसानी से अनुकूलित करें।
weight: 16
url: /hi/net/outline-code-page-settings/outline-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ एमएस प्रोजेक्ट रूपरेखा मूल्यों में महारत हासिल करना

## परिचय
इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.Tasks लाइब्रेरी का उपयोग करके Microsoft प्रोजेक्ट रूपरेखा मानों को कैसे प्रबंधित किया जाए। Aspose.Tasks के साथ, आप आसानी से रूपरेखा कोड में हेरफेर कर सकते हैं, नई रूपरेखा मान बना सकते हैं, और अपनी आवश्यकताओं के अनुसार परियोजना रूपरेखा को अनुकूलित कर सकते हैं।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1.  .NET के लिए Aspose.Tasks की स्थापना: .NET लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/net/).
2. विकास पर्यावरण: सुनिश्चित करें कि आपके पास .NET फ्रेमवर्क संगतता के साथ विजुअल स्टूडियो जैसा विकास वातावरण स्थापित है।
3. C# प्रोग्रामिंग की बुनियादी समझ: C# प्रोग्रामिंग भाषा की बुनियादी बातों से खुद को परिचित करें, क्योंकि हम Aspose.Tasks लाइब्रेरी के साथ काम करने के लिए C# का उपयोग करेंगे।

## नामस्थान आयात करें
अपने C# कोड में आवश्यक नामस्थान आयात करके प्रारंभ करें:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
यह चरण एक नई प्रोजेक्ट ऑब्जेक्ट को प्रारंभ करता है और निर्दिष्ट निर्देशिका से Microsoft प्रोजेक्ट फ़ाइल को लोड करता है।
## चरण 2: रूपरेखा कोड परिभाषाएँ परिभाषित करें
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
यहां, हम दो आउटलाइनकोडडिफिनिशन ऑब्जेक्ट को परिभाषित करते हैं और उन्हें प्रोजेक्ट के आउटलाइनकोड संग्रह में जोड़ते हैं।
## चरण 3: आउटलाइन मास्क को परिभाषित करें
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
यह चरण आउटलाइन कोड परिभाषा के लिए एक आउटलाइनमास्क सेट करता है।
## चरण 4: रूपरेखा मान बनाएँ
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
इस चरण में, हम दो आउटलाइनवैल्यू ऑब्जेक्ट बनाते हैं और उनके गुण जैसे मूल्य, मूल्य आईडी, प्रकार, विवरण और पतन स्थिति सेट करते हैं।

## निष्कर्ष
.NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट रूपरेखा मानों को प्रबंधित करना प्रदान की गई कार्यक्षमताओं के साथ सीधा है। इस ट्यूटोरियल में उल्लिखित चरणों का पालन करके, आप अपनी आवश्यकताओं के अनुसार प्रोजेक्ट रूपरेखा को अनुकूलित करने के लिए रूपरेखा कोड और मानों में कुशलतापूर्वक हेरफेर कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं अन्य .NET फ्रेमवर्क के साथ Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: हां, Aspose.Tasks विभिन्न .NET फ्रेमवर्क के साथ संगत है, जो आपके विकास परिवेश में लचीलापन सुनिश्चित करता है।
### प्रश्न: क्या Aspose.Tasks के लिए कोई परीक्षण संस्करण उपलब्ध है?
 उत्तर: हां, आप Aspose.Tasks के निःशुल्क परीक्षण संस्करण तक पहुंच सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मैं Aspose.Tasks के लिए समर्थन कैसे प्राप्त कर सकता हूं?
 उत्तर: समर्थन और सहायता के लिए, आप Aspose.Tasks फोरम पर जा सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15).
### प्रश्न: क्या मैं Aspose.Tasks के लिए अस्थायी लाइसेंस खरीद सकता हूँ?
उत्तर: हां, आप Aspose.Tasks के लिए एक अस्थायी लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### प्रश्न: मुझे Aspose.Tasks के लिए विस्तृत दस्तावेज़ कहां मिल सकते हैं?
 उ: आप उपलब्ध व्यापक दस्तावेज़ का संदर्भ ले सकते हैं[यहाँ](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
