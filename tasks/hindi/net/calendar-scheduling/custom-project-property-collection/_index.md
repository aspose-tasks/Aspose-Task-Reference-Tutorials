---
date: 2026-10-15
description: Aspose.Tasks for .NET में custom property जोड़ना और custom project properties
  को प्रबंधित करना सीखें, जिससे आपके project metadata नियंत्रण में सुधार हो।
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Aspose.Tasks में Custom Project Property Collection का प्रबंधन
og_description: Aspose.Tasks for .NET के साथ अपने प्रोजेक्ट फ़ाइलों में custom property
  जोड़ें। यह गाइड दिखाता है कि कैसे custom properties को प्रबंधित करें, पढ़ें, और
  boolean या string मानों को प्रभावी ढंग से जोड़ें।
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: Aspose.Tasks .NET API का उपयोग करके custom property जोड़ें
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: Aspose.Tasks for .NET में custom property कैसे जोड़ें
url: /hi/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for .NET में कस्टम प्रॉपर्टी कैसे जोड़ें

## परिचय

कस्टम प्रॉपर्टी समर्थन आपको प्रोजेक्ट‑विशिष्ट मेटाडेटा संग्रहीत करने की सुविधा देता है जो बिल्ट‑इन फ़ील्ड्स द्वारा कवर नहीं किया जाता। इस ट्यूटोरियल में आप सीखेंगे कि **कस्टम प्रॉपर्टी कैसे जोड़ें**, उसे पढ़ें, और Aspose.Tasks for .NET का उपयोग करके पूरी कस्टम प्रॉपर्टी कलेक्शन को प्रबंधित करें। अंत में आप बूलियन, डेटटाइम, डबल और स्ट्रिंग मानों के साथ प्रोजेक्ट फ़ाइलों को अपने व्यावसायिक नियमों के अनुसार अनुकूलित कर पाएँगे।

## त्वरित उत्तर
- **क्या मैं बूलियन कस्टम प्रॉपर्टी जोड़ सकता हूँ?** हाँ – `CustomPropertyType.Boolean` का उपयोग करें।
- **कस्टम प्रॉपर्टी के कितने प्रकार समर्थित हैं?** चार: Boolean, DateTime, Double, String.
- **क्या कस्टम प्रॉपर्टी कलेक्शन रीड‑ओनली है?** यदि प्रोजेक्ट रीड‑ओनली स्रोत से लोड किया गया हो तो यह रीड‑ओनली हो सकता है।
- **क्या इस फीचर को उपयोग करने के लिए लाइसेंस चाहिए?** मूल्यांकन के लिए एक टेम्पररी लाइसेंस काम करता है; प्रोडक्शन के लिए पूर्ण लाइसेंस आवश्यक है।
- **कौन से .NET संस्करण संगत हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## कस्टम प्रॉपर्टी क्या है?

कस्टम प्रॉपर्टी एक उपयोगकर्ता‑परिभाषित मेटाडेटा फ़ील्ड है जिसे आप एक Project ऑब्जेक्ट से जोड़ते हैं। यह आपको अतिरिक्त जानकारी जैसे “Risk Level”, “Customer ID”, या कोई भी बूलियन फ़्लैग जो मानक MS‑Project फ़ील्ड्स में नहीं है, संग्रहीत करने की अनुमति देता है।

## Aspose.Tasks में कस्टम प्रॉपर्टी क्यों जोड़ें?

Aspose.Tasks **50+ इनपुट और आउटपुट फॉर्मेट** का समर्थन करता है और **10,000 तक टास्क** वाले प्रोजेक्ट्स को पूरी फ़ाइल को मेमोरी में लोड किए बिना संभाल सकता है। कस्टम प्रॉपर्टी जोड़ने से आप व्यापार‑महत्वपूर्ण डेटा को सीधे प्रोजेक्ट फ़ाइल में एम्बेड कर सकते हैं, जिससे बाहरी डेटाबेस की आवश्यकता समाप्त हो जाती है और डेटा प्रोजेक्ट के साथ ही रहता है।

## आवश्यकताएँ

- आपके कार्यस्थल पर Visual Studio (कोई भी नवीनतम संस्करण) स्थापित हो।  
- Aspose.Tasks for .NET – इसे [download link](https://releases.aspose.com/tasks/net/) से डाउनलोड करें।  
- C# सिंटैक्स और .NET प्रोजेक्ट संरचना की बुनियादी परिचितता।

## नेमस्पेस इम्पोर्ट करें

निम्नलिखित नेमस्पेस आपको कोर प्रोजेक्ट मॉडल और कस्टम प्रॉपर्टी API तक पहुँच प्रदान करते हैं।

```csharp
using Aspose.Tasks;
using System;


```

## Aspose.Tasks में कस्टम प्रॉपर्टी कैसे जोड़ें?

कस्टम प्रॉपर्टी जोड़ने के लिए, पहले प्रोजेक्ट लोड करें, फिर एक `CustomProperty` ऑब्जेक्ट बनाएँ, उसका नाम, प्रकार और मान सेट करें, और अंत में इसे प्रोजेक्ट की `CustomProperties` कलेक्शन में जोड़ें। यह ऑपरेशन मेटाडेटा को सीधे प्रोजेक्ट फ़ाइल में एम्बेड करता है, और परिवर्तन `project.Save(...)` कॉल करने पर सहेजे जाते हैं।  

`CustomProperty` एक प्रोजेक्ट से जुड़ी एकल उपयोगकर्ता‑परिभाषित फ़ील्ड को दर्शाता है।

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### चरण 1: प्रोजेक्ट इनिशियलाइज़ करें

`Project` Aspose.Tasks में प्रोजेक्ट फ़ाइल का प्रतिनिधित्व करने वाली मुख्य क्लास है।

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### चरण 2: कस्टम प्रॉपर्टी संग्रह की तैयारी जांचें

`CustomProperties` वह कलेक्शन है जो प्रोजेक्ट के सभी कस्टम प्रॉपर्टी ऑब्जेक्ट्स को रखता है।

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### चरण 3: कस्टम प्रॉपर्टी जोड़ें

`Add` मेथड प्रोजेक्ट की कलेक्शन में एक नई कस्टम प्रॉपर्टी डालता है।

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### चरण 4: कस्टम प्रॉपर्टी तक पहुँचें

`CustomProperties` कलेक्शन IEnumerable को इम्प्लीमेंट करता है, जिससे प्रत्येक `CustomProperty` पर इटरेशन संभव होता है।

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### चरण 5: कस्टम प्रॉपर्टी का मान प्राप्त करें

`Get` मेथड कस्टम प्रॉपर्टी का मान उसके नाम से लौटाता है।

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### चरण 6: कस्टम प्रॉपर्टी नामों पर इटरेट करें

`Names` प्रॉपर्टी कलेक्शन में सभी कस्टम प्रॉपर्टी नामों की सूची प्रदान करती है।

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### चरण 7: कस्टम प्रॉपर्टी हटाएँ या साफ़ करें

`Remove` मेथड एक विशिष्ट प्रॉपर्टी को हटाता है, जबकि `Clear` पूरी कलेक्शन को खाली कर देता है।

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## सामान्य समस्याएँ और ट्रबलशूटिंग

- **रीड‑ओनली कलेक्शन** – यदि `project.CustomProperties.IsReadOnly` `true` लौटाता है, तो सुनिश्चित करें कि स्रोत फ़ाइल एक्सक्लूसिव रीड एक्सेस के साथ नहीं खुली है या संपादन से पहले इसे लिखने योग्य स्थान पर कॉपी करें।  
- **टाइप मिसमैच** – यदि आप ऐसे मान को असाइन करते हैं जो घोषित `CustomPropertyType` से मेल नहीं खाता, तो `ArgumentException` उत्पन्न होता है। हमेशा सही `Type` निर्धारित करने के बाद `Value` सेट करें।  
- **परिवर्तनों को सहेजना** – प्रॉपर्टी जोड़ने या हटाने के बाद, संशोधनों को स्थायी बनाने के लिए `project.Save("output.mpp")` कॉल करें; अन्यथा परिवर्तन केवल मेमोरी में रहेंगे।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Tasks for .NET का उपयोग करके अपने प्रोजेक्ट में किसी भी डेटा टाइप की कस्टम प्रॉपर्टी जोड़ सकता हूँ?**  
उत्तर: हाँ, आप बूलियन, डेटटाइम, डबल और स्ट्रिंग टाइप्स को सपोर्ट करने वाली कस्टम प्रॉपर्टी जोड़ सकते हैं।

**प्रश्न: क्या Aspose.Tasks for .NET में कस्टम प्रॉपर्टी नामों पर इटरेट करना संभव है?**  
उत्तर: बिल्कुल, आप `Names` प्रॉपर्टी का उपयोग करके कस्टम प्रॉपर्टी नामों पर इटरेट कर सकते हैं।

**प्रश्न: मैं अपने प्रोजेक्ट से एक विशिष्ट कस्टम प्रॉपर्टी कैसे हटाऊँ?**  
उत्तर: आप `Remove` मेथड का उपयोग करके उसके नाम से कस्टम प्रॉपर्टी हटा सकते हैं।

**प्रश्न: क्या Aspose.Tasks for .NET टेम्पररी लाइसेंस का समर्थन करता है?**  
उत्तर: हाँ, आप मूल्यांकन के लिए Aspose वेबसाइट से टेम्पररी लाइसेंस प्राप्त कर सकते हैं।

**प्रश्न: Aspose.Tasks for .NET के संबंध में समर्थन या अतिरिक्त सहायता कहाँ प्राप्त कर सकता हूँ?**  
उत्तर: आप किसी भी प्रश्न या सहायता के लिए Aspose.Tasks फ़ोरम [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर जा सकते हैं।

**अंतिम अपडेट:** 2026-10-15  
**परीक्षित संस्करण:** Aspose.Tasks 24.11 for .NET  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Tasks for .NET का उपयोग करके बिल्ट‑इन प्रोजेक्ट प्रॉपर्टीज़ कैसे पढ़ें](/tasks/net/advanced-features/built-in-project-property-collection/)
- [Aspose.Tasks में MS Project एट्रिब्यूट्स कलेक्शन प्रबंधित करें](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Aspose.Tasks कस्टम फ़ील्ड टाइप्स – कैलेंडर और शेड्यूलिंग](/tasks/net/calendar-scheduling/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}