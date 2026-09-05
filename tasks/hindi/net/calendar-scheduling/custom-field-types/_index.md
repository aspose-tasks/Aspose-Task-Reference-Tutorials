---
date: 2026-07-19
description: Aspose.Tasks for .NET में custom field types जोड़ने के बारे में चरण‑दर‑चरण
  कोड, पूर्वापेक्षाएँ और FAQs के साथ सीखें।
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Aspose.Tasks में Custom Field Types
og_description: Aspose.Tasks for .NET में custom field types जोड़ना सीखें। इस चरण‑दर‑चरण
  गाइड का पालन करके extended attributes को प्रभावी ढंग से बनाएं, परिभाषित करें और
  उपयोग करें।
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: Aspose.Tasks for .NET में Custom Field Types कैसे जोड़ें
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: Aspose.Tasks for .NET में Custom Field Types कैसे जोड़ें
url: /hi/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में कस्टम फ़ील्ड प्रकार कैसे जोड़ें

## परिचय

इस ट्यूटोरियल में आप **कस्टम फ़ील्ड कैसे जोड़ें** प्रकारों को Microsoft Project फ़ाइल में Aspose.Tasks for .NET का उपयोग करके जोड़ना सीखेंगे। कस्टम फ़ील्ड आपको अतिरिक्त जानकारी—जैसे जोखिम स्कोर, विभाग कोड, या कस्टम नोट्स—सीधे टास्क, रिसोर्स या प्रोजेक्ट पर संग्रहीत करने की अनुमति देते हैं। हम पूरी प्रक्रिया को कवर करेंगे, पर्यावरण सेटअप से लेकर परिभाषा, जोड़ना और कस्टम टेक्स्ट फ़ील्ड की पुष्टि तक।

## त्वरित उत्तर
- **कस्टम फ़ील्ड क्या है?** उपयोगकर्ता‑परिभाषित कॉलम जो कार्यों/संसाधनों पर टेक्स्ट, संख्या, तिथियां, या फ़्लैग रख सकता है।  
- **कस्टम फ़ील्ड को परिभाषित करने वाली क्लास कौन सी है?** `ExtendedAttributeDefinition`।  
- **क्या मैं मौजूदा प्रोजेक्ट में कस्टम फ़ील्ड जोड़ सकता हूँ?** हाँ—प्रोजेक्ट लोड करें, परिभाषा बनाएं, फिर इसे कलेक्शन में जोड़ें।  
- **क्या मुझे Aspose.Tasks के लिए लाइसेंस चाहिए?** उत्पादन के लिए लाइसेंस आवश्यक है; मूल्यांकन के लिए फ्री ट्रायल काम करता है।  
- **समर्थित .NET संस्करण?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7।

## Aspose.Tasks में “कस्टम फ़ील्ड कैसे जोड़ें” क्या है?
**कस्टम फ़ील्ड कैसे जोड़ें** प्रक्रिया को दर्शाता है जिसमें `ExtendedAttributeDefinition` बनाकर उसे प्रोजेक्ट के `ExtendedAttributes` कलेक्शन में संलग्न किया जाता है। यह आपको अतिरिक्त मेटाडेटा संग्रहीत करने की अनुमति देता है जो मानक प्रोजेक्ट स्कीमा का हिस्सा नहीं है। इसे कार्यों, संसाधनों, या स्वयं प्रोजेक्ट के लिए उपयोग किया जा सकता है, जिससे आप जोखिम स्तर, विभाग कोड, या कस्टम नोट्स जैसी जानकारी कैप्चर कर सकते हैं जो डिफ़ॉल्ट फ़ील्ड में उपलब्ध नहीं हैं।

## प्रोजेक्ट मैनेजमेंट में कस्टम फ़ील्ड क्यों उपयोग करें?
Aspose.Tasks **50+ बिल्ट‑इन विस्तारित एट्रिब्यूट प्रकार** का समर्थन करता है और आपको **किसी भी संख्या में कस्टम फ़ील्ड** परिभाषित करने देता है बिना फ़ाइल आकार पर बड़ा असर डाले। कस्टम फ़ील्ड का उपयोग करके आप:  
ये फ़ील्ड Microsoft Project में अतिरिक्त कॉलम के रूप में दिखते हैं और फ़ॉर्मूले, रिपोर्ट, और फ़िल्टर में संदर्भित किए जा सकते हैं। वे प्रोजेक्ट फ़ाइल के भीतर संग्रहीत होते हैं और फ़ाइल के साथ चलते हैं, जिससे कोई भी डाउनस्ट्रीम टूल कस्टम डेटा को बनाए रखता है।

## पूर्वापेक्षाएँ

### 1. Visual Studio स्थापित
सुनिश्चित करें कि आपके मशीन पर Visual Studio (2019 या बाद का) स्थापित है। आप इसे Microsoft वेबसाइट से डाउनलोड कर सकते हैं।

### 2. Aspose.Tasks for .NET
अपने प्रोजेक्ट में Aspose.Tasks NuGet पैकेज जोड़ें। नवीनतम संस्करण [here](https://releases.aspose.com/tasks/net/) से डाउनलोड करें।

### 3. बुनियादी C# ज्ञान
आपको C# सिंटैक्स, क्लासेज़, और .NET प्रोजेक्ट संरचना में सहज होना चाहिए।

## नेमस्पेस इम्पोर्ट करें

`Project`, `ExtendedAttributeDefinition`, और संबंधित एनम्स `Aspose.Tasks` नेमस्पेस में स्थित हैं। इसे अपनी फ़ाइल के शीर्ष पर इम्पोर्ट करें:

`Aspose.Tasks` नेमस्पेस Microsoft Project फ़ाइलों को संभालने के लिए सभी कोर टाइप्स प्रदान करता है।

```csharp

```

## प्रोजेक्ट में कस्टम फ़ील्ड कैसे जोड़ें?

मौजूदा प्रोजेक्ट लोड करें, एक कस्टम फ़ील्ड परिभाषा बनाएं, और इसे प्रोजेक्ट के विस्तारित एट्रिब्यूट्स कलेक्शन में जोड़ें—तीन संक्षिप्त चरणों में। यह पैटर्न कार्यों, संसाधनों, और स्वयं प्रोजेक्ट के लिए काम करता है, और यह सुनिश्चित करता है कि फ़ाइल सहेजते समय कस्टम फ़ील्ड स्थायी रहे।

### चरण 1: प्रोजेक्ट ऑब्जेक्ट बनाएं
`Project` Aspose.Tasks का टॉप‑लेवल ऑब्जेक्ट है जो मेमोरी में एक सिंगल प्रोजेक्ट फ़ाइल का प्रतिनिधित्व करता है। इसे इंस्टैंशिएट करने से फ़ाइल लोड होती है और आपको कार्यों, संसाधनों, और विस्तारित एट्रिब्यूट्स तक पहुंच मिलती है।

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### चरण 2: कस्टम फ़ील्ड परिभाषित करें
`ExtendedAttributeDefinition` एक नया कॉलम वर्णित करता है। इस उदाहरण में हम कार्यों के लिए **Text** प्रकार का कस्टम फ़ील्ड बनाते हैं और इसे “MyText” उपनाम देते हैं। `ExtendedAttributeTask.Text1` एन्‍उम वैल्यू Aspose.Tasks को बताती है कि मान कहाँ संग्रहीत करना है।

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### चरण 3: कस्टम फ़ील्ड परिभाषा को प्रोजेक्ट में जोड़ें
प्रोजेक्ट का `ExtendedAttributes` कलेक्शन सभी कस्टम फ़ील्ड परिभाषाओं को रखता है। परिभाषा जोड़ने से यह प्रोजेक्ट के प्रत्येक कार्य के लिए उपलब्ध हो जाती है।

```csharp
project.ExtendedAttributes.Add(definition);
```

## सामान्य समस्याएँ और समाधान
- **फ़ील्ड MS Project UI में नहीं दिख रहा** – सुनिश्चित करें कि आपने `Alias` प्रॉपर्टी सेट की है; MS Project उपनाम को कॉलम हेडर के रूप में दिखाता है।  
- **सेव करने पर एक्सेप्शन आता है** – जांचें कि प्रोजेक्ट फ़ाइल रीड‑ओनली नहीं है और आपके पास वैध लाइसेंस है।  
- **कस्टम फ़ील्ड मान रीलोड के बाद खो जाते हैं** – कार्यों को मान असाइन करने के बाद `project.Save("output.mpp")` कॉल करना सुनिश्चित करें।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Tasks को अन्य .NET फ्रेमवर्क के साथ उपयोग कर सकता हूँ?**  
**उत्तर:** हाँ, Aspose.Tasks .NET Framework, .NET Core, और .NET 5/6/7 के साथ काम करता है।

**प्रश्न: क्या Aspose.Tasks एंटरप्राइज़‑लेवल एप्लिकेशन्स के लिए उपयुक्त है?**  
**उत्तर:** बिल्कुल। यह **10,000 कार्यों** तक के प्रोजेक्ट्स को प्रोसेस करने का समर्थन करता है और मल्टी‑थ्रेडेड सर्वर वातावरण में चल सकता है।

**प्रश्न: क्या Aspose.Tasks कई प्रोजेक्ट फ़ाइल फ़ॉर्मेट्स का समर्थन करता है?**  
**उत्तर:** हाँ—Aspose.Tasks MPP, XML, HTML, और CSV फ़ॉर्मेट पढ़ता और लिखता है, जो **सभी प्रमुख Microsoft Project संस्करणों** को कवर करता है।

**प्रश्न: क्या मैं Aspose.Tasks का उपयोग करके रिसोर्स डेटा को मैनीपुलेट कर सकता हूँ?**  
**उत्तर:** हाँ, आप रिसोर्सेज़ को जोड़, अपडेट, और डिलीट कर सकते हैं, साथ ही उन्हें कस्टम फ़ील्ड असाइन कर सकते हैं।

**प्रश्न: क्या Aspose.Tasks उपयोगकर्ताओं के लिए कोई कम्युनिटी फ़ोरम है?**  
**उत्तर:** हाँ, आप [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर जाकर अन्य उपयोगकर्ताओं से इंटरैक्ट कर सकते हैं और Aspose टीम से सपोर्ट प्राप्त कर सकते हैं।

---

**अंतिम अपडेट:** 2026-07-19  
**परीक्षण किया गया:** Aspose.Tasks 24.12 for .NET  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.Tasks में MS Project के विस्तारित एट्रिब्यूट परिभाषाओं में महारत हासिल करें](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [Aspose.Tasks के साथ MS Project विस्तारित एट्रिब्यूट्स को मैनीपुलेट करें](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Aspose.Tasks में फ़ील्ड हेल्पर MS Project इंटीग्रेशन](/tasks/net/tasks-project-management/field-helper/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}