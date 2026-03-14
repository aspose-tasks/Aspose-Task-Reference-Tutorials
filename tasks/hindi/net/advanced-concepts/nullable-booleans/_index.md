---
date: 2026-03-14
description: Aspose.Tasks for .NET में nullable बूलियन का उपयोग कैसे करें, जिसमें
  nullable बूलियन मानों को बदलना और nullable बूलियन प्रॉपर्टी सेट करना शामिल है।
linktitle: How to Use Nullable Booleans in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks में Nullable Booleans का उपयोग कैसे करें
url: /hi/net/advanced-concepts/nullable-booleans/
weight: 21
---

:" => "लेखक:"

Now ensure we keep code block placeholders unchanged.

Also keep markdown formatting.

Now produce final content with shortcodes at top and bottom unchanged.

Let's construct final output.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में Nullable Booleans का उपयोग कैसे करें

इस ट्यूटोरियल में हम **nullable** booleans को Aspose.Tasks .NET API के साथ काम करते समय कैसे उपयोग करें, दिखाएंगे। Nullable booleans आपको तीन संभावित स्थितियाँ देती हैं—`true`, `false`, या *undefined*—जो विशेष रूप से उन प्रोजेक्ट‑लेवल सेटिंग्स के लिए उपयोगी है जो स्पष्ट रूप से निर्दिष्ट नहीं की गई हों। आप देखेंगे कि nullable boolean मान कैसे बनाते हैं, बदलते हैं, और **set nullable boolean** मान कैसे सेट करते हैं, तथा nullable booleans को सही ढंग से संभालना आपके शेड्यूलिंग एप्लिकेशन में अप्रत्याशित व्यवहार को कैसे रोक सकता है।

## त्वरित उत्तर
- **Nullable Boolean क्या है?** एक प्रकार जो `true`, `false` या अपरिभाषित (undefined) रख सकता है।  
- **Aspose.Tasks में nullable booleans का उपयोग क्यों करें?** ये आपको वैकल्पिक प्रोजेक्ट प्रॉपर्टीज़ को डिफ़ॉल्ट अनुमानित किए बिना दर्शाने की अनुमति देते हैं।  
- **Nullable Boolean को सामान्य bool में कैसे बदलें?** पहले implicit conversion का उपयोग करें या `IsDefined` जांचें।  
- **मुख्य क्लास कौन सी है?** `Aspose.Tasks` नेमस्पेस में `NullableBool`।  
- **क्या लाइसेंस चाहिए?** हाँ, प्रोडक्शन उपयोग के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है।

## Nullable Boolean क्या है?

एक nullable boolean (`NullableBool`) नियमित `bool` प्रकार को एक *IsDefined* फ़्लैग जोड़कर विस्तारित करता है। जब `IsDefined` `false` होता है, तो मान को अपरिभाषित माना जाता है, जिससे आप “false” और “not set” के बीच अंतर कर सकते हैं।

## प्रोजेक्ट सेटिंग्स में Nullable Booleans को क्यों संभालें?

कई प्रोजेक्ट विकल्प—जैसे **ActualsInSync** या **HonorConstraints**—वैकल्पिक होते हैं। साधारण `bool` का उपयोग करने से आपको `true` या `false` चुनना पड़ता है, जो उपयोगकर्ता की मंशा को अनजाने में ओवरराइड कर सकता है। **Nullable booleans को संभालकर**, आप मूल स्थिति को संरक्षित रखते हैं और आकस्मिक कॉन्फ़िगरेशन बदलावों से बचते हैं।

## पूर्वापेक्षाएँ

शुरू करने से पहले, सुनिश्चित करें कि आपके पास हैं:

1. **Visual Studio** (या कोई भी .NET‑संगत IDE)।  
2. **Aspose.Tasks for .NET** – इसे [यहाँ](https://releases.aspose.com/tasks/net/) से डाउनलोड करें।

## नेमस्पेस इम्पोर्ट करें

पहले, आवश्यक नेमस्पेस इम्पोर्ट करें:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
```

अब हम प्रत्येक उदाहरण को चरण‑दर‑चरण देखते हैं।

## `NullableBool` के साथ काम करना

### चरण 1: नया `Project` इंस्टेंस बनाएं।

```csharp
var project = new Project();
```

### चरण 2: निर्दिष्ट मानों के साथ `NullableBool` ऑब्जेक्ट बनाएं।

```csharp
var actualsInSync = new NullableBool(false, false);
```

### चरण 3: `NullableBool` ऑब्जेक्ट के मान और परिभाषित स्थिति की जाँच करें।

```csharp
Console.WriteLine("'ActualsInSync' Value: " + actualsInSync.Value);
Console.WriteLine("'ActualsInSync' Is Defined: " + actualsInSync.IsDefined);
```

### चरण 4: प्रोजेक्ट पर **nullable boolean** सेट करें।

```csharp
project.Set(Prj.ActualsInSync, actualsInSync);
```

### चरण 5: एकल मान के साथ दूसरा `NullableBool` ऑब्जेक्ट बनाएं।

```csharp
var honorConstraints = new NullableBool(true);
```

### चरण 6: `NullableBool` ऑब्जेक्ट का स्ट्रिंग प्रतिनिधित्व दिखाएं।

```csharp
Console.WriteLine("'HonorConstraints' ToString: " + honorConstraints.ToString());
```

### चरण 7: प्रोजेक्ट में सेट करके `NullableBool` इंस्टेंस का उपयोग करें।

```csharp
project.Set(Prj.HonorConstraints, honorConstraints);
```

## `NullableBool` इंस्टेंस की तुलना

### चरण 1: दो `NullableBool` ऑब्जेक्ट बनाएं।

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### चरण 2: प्रत्येक `NullableBool` ऑब्जेक्ट का स्ट्रिंग प्रतिनिधित्व जांचें।

```csharp
Console.WriteLine("Nullable Bool 1: " + bool1.ToString());
Console.WriteLine("Nullable Bool 2: " + bool2.ToString());
```

### चरण 3: `bool` में implicit conversion करें और परिणाम प्रिंट करें।

```csharp
if (bool1)
{
    Console.WriteLine("Nullable Bool 1 is True");
}
else
{
    Console.WriteLine("Nullable Bool 1 is False");
}
```

### चरण 4: दो `NullableBool` ऑब्जेक्ट की समानता की तुलना करें।

```csharp
Console.WriteLine("Are bools equal: " + bool1.Equals(bool2));
```

## `NullableBool` का हैश कोड प्राप्त करना

### चरण 1: दो `NullableBool` ऑब्जेक्ट बनाएं।

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### चरण 2: प्रत्येक `NullableBool` ऑब्जेक्ट का हैश कोड प्रिंट करें।

```csharp
Console.WriteLine("Bool 1: {0} Hash Code 1: {1}", bool1.ToString(), bool1.GetHashCode());
Console.WriteLine("Bool 2: {0} Hash Code 1: {1}", bool2.ToString(), bool2.GetHashCode());
```

## सामान्य ग़लतियाँ और टिप्स

- **कभी भी यह न मानें कि nullable boolean परिभाषित है।** `Value` उपयोग करने से पहले हमेशा `IsDefined` जांचें।  
- **बिना जांच के नियमित bool में बदलने से यदि मान अपरिभाषित है तो अपवाद फेंका जा सकता है।** केवल तब ही implicit conversion उपयोग करें जब आपको यकीन हो कि यह परिभाषित है।  
- **प्रोजेक्ट प्रॉपर्टीज़ सेट करते समय, यदि आवश्यक हो तो अपरिभाषित स्थिति को संरक्षित रखने के लिए `NullableBool` के साथ `Set` मेथड का उपयोग करें।**

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: Nullable Boolean क्या है?**  
उत्तर: एक nullable boolean `true`, `false`, या एक अपरिभाषित स्थिति का प्रतिनिधित्व कर सकता है, जिससे तीन अलग-अलग परिणाम मिलते हैं।

**प्रश्न: मैं nullable boolean को सुरक्षित रूप से नियमित bool में कैसे बदल सकता हूँ?**  
उत्तर: पहले `IsDefined` जांचें, फिर `Value` प्रॉपर्टी का उपयोग करें या जब आप सुनिश्चित हों तो implicit conversion पर भरोसा करें।

**प्रश्न: Aspose.Tasks में साधारण bools के बजाय nullable booleans का उपयोग क्यों करना चाहिए?**  
उत्तर: वे आपको वैकल्पिक प्रोजेक्ट सेटिंग्स को अपरिवर्तित रखने देते हैं, जिससे आकस्मिक ओवरराइड से बचा जा सकता है।

**प्रश्न: क्या मैं nullable boolean को अपरिभाषित सेट कर सकता हूँ?**  
उत्तर: हाँ—ऐसे कंस्ट्रक्टर का उपयोग करें जो केवल defined फ़्लैग लेता है, उदाहरण के लिए `new NullableBool(false, false)`।

**प्रश्न: Aspose.Tasks for .NET पर आगे की दस्तावेज़ीकरण कहाँ मिल सकती है?**  
उत्तर: आप विस्तृत दस्तावेज़ीकरण [यहाँ](https://reference.aspose.com/tasks/net/) पा सकते हैं।

---

**अंतिम अपडेट:** 2026-03-14  
**परीक्षित संस्करण:** Aspose.Tasks for .NET (latest release)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}