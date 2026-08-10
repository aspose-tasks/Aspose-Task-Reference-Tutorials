---
date: 2026-03-24
description: Aspose.Tasks for .NET में गणना कैसे सेट करें, इसका सीखें, सारांश मानों
  की गणना करने, गणना सूत्र परिभाषित करने और रोलअप सारांश को कॉन्फ़िगर करने के उदाहरणों
  के साथ।
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks में गणना प्रकार कैसे सेट करें
url: /hi/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में Calculation Type कैसे सेट करें

## परिचय

यदि आपको Microsoft Project फ़ाइल में टास्क और समरी रो के लिए **how to set calculation** नियमों की आवश्यकता है, तो यह ट्यूटोरियल Aspose.Tasks for .NET का उपयोग करके ठीक वही दिखाता है। हम एक पूर्ण **calculation type example** के माध्यम से चलेंगे, **calculate summary values** को कैसे प्रदर्शित किया जाए दिखाएंगे, और **define calculation formula** तथा विस्तारित एट्रिब्यूट्स के लिए **configure rollup summary** को समझाएंगे। अंत तक, आप प्रोजेक्ट में एक टास्क जोड़ सकेंगे, कस्टम कैल्कुलेशन लॉजिक सेट कर सकेंगे, और रोल‑अप व्यवहार को आत्मविश्वास के साथ नियंत्रित कर सकेंगे।

## त्वरित उत्तर
- **What is the primary purpose?** प्रोजेक्ट फ़ाइल में टास्क और समरी वैल्यूज़ की गणना कैसे की जाती है, इसे नियंत्रित करना।  
- **Which API class is used?** `ExtendedAttributeDefinition` के साथ `CalculationType` और `SummaryRowsCalculationType`।  
- **Can I use a formula?** हाँ – `CalculationType = CalculationType.Formula` सेट करें और एक फ़ॉर्मूला स्ट्रिंग प्रदान करें।  
- **How do I roll‑up summary values?** `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` उपयोग करें और `RollupType` जैसे `Average` निर्दिष्ट करें।  
- **Do I need a license?** प्रोडक्शन उपयोग के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है।

## Calculation Type क्या है और कैसे सेट करें?

`CalculationType` Aspose.Tasks को बताता है कि विस्तारित एट्रिब्यूट का मान कैसे गणना किया जाए। आप स्थिर मान, फ़ॉर्मूला चुन सकते हैं, या लाइब्रेरी को चाइल्ड टास्क से मान रोल‑अप करने दे सकते हैं। गणना को सही ढंग से सेट करना आवश्यक है जब आप चाहते हैं कि प्रोजेक्ट कस्टम बिज़नेस नियमों को मैन्युअल अपडेट के बिना दर्शाए।

## सारांश मानों की गणना के लिए Calculation Type का उपयोग क्यों करें?

जब प्रोजेक्ट में समरी टास्क होते हैं, तो अक्सर आपको समरी रो में संकलित डेटा (जैसे कुल लागत, औसत अवधि) दिखाने की आवश्यकता होती है। `SummaryRowsCalculationType` और `RollupType` के माध्यम से **calculate summary values** को कॉन्फ़िगर करके, Aspose.Tasks स्वचालित रूप से इन एग्रीगेट्स को सिंक रख सकता है जब आप व्यक्तिगत टास्क को संशोधित करते हैं।

## पूर्वापेक्षाएँ

1. C# और .NET फ्रेमवर्क का बुनियादी ज्ञान।  
2. आपके मशीन पर Visual Studio (कोई भी नवीनतम संस्करण) स्थापित होना चाहिए।  
3. Aspose.Tasks for .NET लाइब्रेरी स्थापित – आप इसे [here](https://releases.aspose.com/tasks/net/) से डाउनलोड कर सकते हैं।  
4. संदर्भ के लिए आधिकारिक Aspose.Tasks for .NET दस्तावेज़ीकरण तक पहुँच, उपलब्ध [here](https://reference.aspose.com/tasks/net/)।

## नेमस्पेस आयात करें

उदाहरण में डुबकी लगाने से पहले, आवश्यक नेमस्पेस आयात करना सुनिश्चित करें:

```csharp
using Aspose.Tasks;
using System;
```

## चरण 1: नया प्रोजेक्ट बनाएं

पहले, हम एक खाली `Project` ऑब्जेक्ट बनाते हैं जो हमारे टास्क और कस्टम एट्रिब्यूट्स को रखेगा।

```csharp
var project = new Project();
```

## चरण 2: प्रोजेक्ट में टास्क जोड़ें

अब हम एक साधारण टास्क बनाकर, उसकी शुरूआत तिथि सेट करके, और एक‑दिन की अवधि देकर **add task project** डेटा जोड़ते हैं।

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## चरण 3: विस्तारित एट्रिब्यूट के लिए Calculation Type परिभाषित करें (फ़ॉर्मूला उदाहरण)

यहाँ हम एक विस्तारित एट्रिब्यूट परिभाषा बनाते हैं जिसका मान फ़ॉर्मूला से गणना किया जाता है। यह एक **calculation type example** दर्शाता है और दिखाता है कि **define calculation formula** कैसे किया जाए।

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## चरण 4: समरी रो के लिए Calculation Type परिभाषित करें (Rollup Summary कॉन्फ़िगर करें)

अगला, हम एक और विस्तारित एट्रिब्यूट परिभाषा बनाते हैं जो Aspose.Tasks को *Average* रोल‑अप प्रकार का उपयोग करके **configure rollup summary** करने को बताता है। यह लागत, कार्य, या कस्टम फ़ील्ड्स के लिए **calculate summary values** करने का सामान्य तरीका है।

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## सामान्य समस्याएँ और ट्रबलशूटिंग

| लक्षण | संभावित कारण | समाधान |
|---------|--------------|-----|
| फ़ॉर्मूला `null` लौटाता है | फ़ॉर्मूला में गलत फ़ील्ड रेफ़रेंस | ब्रैकेट्स के अंदर फ़ील्ड नाम की जाँच करें (उदाहरण: `[Start]` न कि `[stARt]`)। |
| समरी रो 0 दिखाते हैं | `SummaryRowsCalculationType` सेट नहीं है या गलत `RollupType` | सुनिश्चित करें कि `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` है और उपयुक्त `RollupType` चुनें। |
| एट्रिब्यूट्स जोड़ने के बाद प्रोजेक्ट लोड नहीं होता | एट्रिब्यूट परिभाषा और टास्क उपयोग में असंगति | एट्रिब्यूट परिभाषा को किसी टास्क को असाइन करने **से पहले** जोड़ें। |

## निष्कर्ष

इस ट्यूटोरियल में, हमने Aspose.Tasks for .NET में **how to set calculation** नियमों को कवर किया है, सरल टास्क बनाने से लेकर फ़ॉर्मूला‑आधारित और रोल‑अप‑आधारित Calculation Type को परिभाषित करने तक। इन सेटिंग्स में निपुण होकर आप **calculate summary values** पर सूक्ष्म नियंत्रण प्राप्त करते हैं, जिससे मैन्युअल स्प्रेडशीट कार्य के बिना समृद्ध प्रोजेक्ट एनालिटिक्स संभव हो जाता है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: Aspose.Tasks में Calculation Type क्या है?

A1: Aspose.Tasks में Calculation Type निर्धारित करता है कि प्रोजेक्ट के भीतर टास्क और समरी टास्क के मान कैसे गणना किए जाते हैं, जिसमें फ़ॉर्मूला और रोल‑अप जैसे विकल्प उपलब्ध होते हैं।

### Q2: विस्तारित एट्रिब्यूट के लिए Calculation Type कैसे सेट करें?

A2: आप विस्तारित एट्रिब्यूट की `CalculationType` प्रॉपर्टी को उपयुक्त रूप से परिभाषित करके Calculation Type सेट कर सकते हैं।

### Q3: क्या मैं प्रोजेक्ट में समरी रो के लिए Calculation Type को कस्टमाइज़ कर सकता हूँ?

A3: हाँ, Aspose.Tasks आपको समरी रो के लिए Calculation Type निर्दिष्ट करने की अनुमति देता है, जिससे आप अपनी आवश्यकताओं के अनुसार मान गणना को अनुकूलित कर सकते हैं।

### Q4: क्या समरी टास्क गणनाओं के लिए विभिन्न Rollup Types उपलब्ध हैं?

A4: हाँ, Aspose.Tasks विभिन्न Rollup Types जैसे Average, Sum, और Count प्रदान करता है जो समरी टास्क के मानों की गणना के लिए उपयोग किए जा सकते हैं।

### Q5: Aspose.Tasks for .NET पर अधिक संसाधन कहाँ मिल सकते हैं?

A5: आप व्यापक मार्गदर्शन और सहायता के लिए [Aspose.Tasks for .NET](https://reference.aspose.com/tasks/net/) पर उपलब्ध दस्तावेज़ीकरण और कम्युनिटी सपोर्ट फ़ोरम का अन्वेषण कर सकते हैं।

---

**अंतिम अपडेट:** 2026-03-24  
**परीक्षण किया गया:** Aspose.Tasks for .NET (latest release)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}