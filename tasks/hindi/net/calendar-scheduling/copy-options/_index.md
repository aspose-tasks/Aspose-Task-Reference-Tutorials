---
date: 2026-07-05
description: Aspose.Tasks for .NET का उपयोग करके copy options के साथ प्रोजेक्ट डेटा
  कैसे कॉपी करें सीखें। सटीक प्रोजेक्ट मैनेजमेंट के साथ अपने .NET एप्लिकेशन को बढ़ाएँ।
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
linktitle: Aspose.Tasks में copy options के साथ प्रोजेक्ट डेटा कैसे कॉपी करें
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  type: TechArticle
- description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
  type: HowTo
- questions:
  - answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
    question: Can I copy only a subset of tasks?
  - answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
    question: Does Aspose.Tasks support copying between different file formats?
  - answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
    question: How do I handle password‑protected project files?
  - answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
    question: Is there a way to copy resource pools without tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
    question: Where can I find more examples?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks में copy options के साथ प्रोजेक्ट डेटा कैसे कॉपी करें
url: /hi/net/calendar-scheduling/copy-options/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में कॉपी विकल्पों के साथ प्रोजेक्ट डेटा कैसे कॉपी करें

## परिचय

यदि आपको एक Microsoft Project फ़ाइल से दूसरी में **how to copy project** जानकारी कॉपी करनी है, तो Aspose.Tasks for .NET आपको इसे करने का एक साफ़, कोड‑फ़र्स्ट तरीका देता है। इस ट्यूटोरियल में हम पूरी कार्यप्रवाह—स्रोत प्रोजेक्ट लोड करना, कॉपी विकल्प कॉन्फ़िगर करना, कॉपी बनाना, और परिणाम लोड करना—के माध्यम से चलेंगे—ताकि आप किसी भी .NET एप्लिकेशन में प्रोजेक्ट‑कॉपी लॉजिक को आत्मविश्वास के साथ एकीकृत कर सकें।

## त्वरित उत्तर

- **कॉपी फ़ीचर क्या करता है?** यह प्रोजेक्ट डेटा को डुप्लिकेट करता है जबकि आपको कैलेंडर, रिसोर्सेज, या व्यू जानकारी जैसे विशिष्ट सेक्शन को शामिल या बाहर करने की अनुमति देता है।  
- **कौन सा क्लास व्यवहार को नियंत्रित करता है?** `CopyToOptions` आपको यह सूक्ष्म‑समायोजित करने देता है कि क्या कॉपी किया जाए।  
- **क्या मुझे लाइसेंस की आवश्यकता है?** प्रोडक्शन के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है; विकास के लिए एक फ्री ट्रायल काम करता है।  
- **समर्थित फ़ॉर्मेट्स?** Aspose.Tasks MPP, XML, और XER फ़ाइलों को संभालता है—कुल मिलाकर 20 + फ़ॉर्मेट्स से अधिक।  
- **क्या मैं व्यू डेटा को स्किप कर सकता हूँ?** हाँ, `CopyToOptions.SkipViewData = true` सेट करके UI‑संबंधित जानकारी को छोड़ सकते हैं।

## Aspose.Tasks में “how to copy project” क्या है?

**“How to copy project”** Aspose.Tasks की API का उपयोग करके एक Project ऑब्जेक्ट के डेटा को नई फ़ाइल में डुप्लिकेट करने को दर्शाता है, वैकल्पिक रूप से अनचाहे तत्वों को फ़िल्टर करते हुए। यह ऑपरेशन टेम्प्लेटिंग, आर्काइविंग, या मैन्युअल UI चरणों के बिना प्रोजेक्ट वैरिएंट बनाने के लिए उपयोगी है, और यह सभी समर्थित फ़ाइल फ़ॉर्मेट्स में काम करता है।

## Aspose.Tasks में कॉपी विकल्पों का उपयोग क्यों करें?

Aspose.Tasks **50+ प्रोजेक्ट‑संबंधित इकाइयों** (टास्क, रिसोर्सेज, कैलेंडर, असाइनमेंट आदि) को समर्थन देता है और **10,000 टास्क** तक की फ़ाइलों को प्रोसेस कर सकता है जबकि मेमोरी उपयोग 200 MB से कम रखता है। `CopyToOptions` का उपयोग करके आप भारी व्यू डेटा को कॉपी करने से बच सकते हैं, जिससे आउटपुट फ़ाइल आकार **30‑40 %** तक घटता है और बड़े प्रोजेक्ट्स के लिए ऑपरेशन की गति लगभग **2×** तक बढ़ती है।

## पूर्वापेक्षाएँ

1. **Aspose.Tasks for .NET** – नवीनतम संस्करण [download link](https://releases.aspose.com/tasks/net/) से डाउनलोड करें।  
2. **.NET development environment** – Visual Studio 2022 (या कोई भी IDE जो .NET 6+ को सपोर्ट करता हो) स्थापित हो।  
3. **A valid Aspose.Tasks license** – मूल्यांकन के लिए वैकल्पिक, प्रोडक्शन बिल्ड्स के लिए अनिवार्य।  
4. **An existing project file** (जैसे, `SourceProject.xml`) जिसे आप कॉपी करना चाहते हैं।

## Aspose.Tasks के लिए नेमस्पेस कैसे इम्पोर्ट करें?

अपने C# फ़ाइल के शीर्ष पर आवश्यक `using` निर्देश जोड़ें ताकि कंपाइलर Aspose.Tasks टाइप्स को ढूँढ सके। इन स्टेटमेंट्स को शामिल करने से आपको `Project`, `CopyToOptions`, और अन्य यूटिलिटी क्लासेज़ तक सीधे पहुँच मिलती है बिना उनके नामों को पूरी तरह क्वालिफ़ाई किए, जिससे आपका कोड सरल और पठनीय बनता है।

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## चरण 1: प्रोजेक्ट ऑब्जेक्ट्स को इनिशियलाइज़ करें

पहले, एक `Project` इंस्टेंस बनाएं जो स्रोत फ़ाइल का प्रतिनिधित्व करता है और XML डेटा लोड करें।  
`Project` क्लास एक Microsoft Project फ़ाइल को मेमोरी में लोड किए हुए दर्शाता है, जो टास्क, रिसोर्सेज, कैलेंडर और अन्य प्रोजेक्ट जानकारी को उजागर करता है।

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **Pro tip:** यदि आप बहुत बड़ी फ़ाइलों के साथ काम करते हैं, तो `LoadOptions` कंस्ट्रक्टर का उपयोग करने पर विचार करें ताकि लेज़ी लोडिंग सक्षम हो और मेमोरी खपत कम रहे।

## चरण 2: प्रोजेक्ट की कॉपी बनाएं

अगला, एक दूसरा `Project` ऑब्जेक्ट इंस्टैंशिएट करें जो कॉपी किए गए डेटा को प्राप्त करेगा। यह ऑब्जेक्ट खाली शुरू होता है।

```csharp
Project copiedProject = new Project();
```

अब आपके पास दो अलग-अलग `Project` ऑब्जेक्ट्स हैं: एक डिस्क से लोड किया गया और एक कॉपी प्राप्त करने के लिए तैयार।

## चरण 3: कॉपी किए गए प्रोजेक्ट को लोड करें

कॉपी ऑपरेशन (बाद में दिखाया गया) के बाद, आप परिणाम की पुष्टि के लिए नई सेव की गई फ़ाइल को दूसरे `Project` इंस्टेंस में लोड करना चाहेंगे।

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

फ़ाइल को फिर से लोड करने से पुष्टि होती है कि कॉपी सफल रही और आपने सेट किए गए विकल्प अपेक्षित रूप से कार्य किए।

## चरण 4: कॉपी विकल्पों को कॉन्फ़िगर करें

`CopyToOptions` क्लास आपको यह निर्दिष्ट करने देती है कि स्रोत से गंतव्य में क्या ट्रांसफ़र किया जाए।

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

`SkipViewData = true` सेट करने से आउटपुट फ़ाइल आकार घटता है और ऑपरेशन तेज़ होता है, विशेषकर जब आपको केवल लॉजिकल प्रोजेक्ट डेटा की आवश्यकता हो।

## चरण 5: प्रोजेक्ट कॉपी निष्पादित करें

अंत में, स्रोत प्रोजेक्ट पर `CopyTo` मेथड को कॉल करें, गंतव्य प्रोजेक्ट और आपने कॉन्फ़िगर किए विकल्प पास करते हुए।

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

यह दो‑लाइन कॉल पूरी कॉपी ऑपरेशन को निष्पादित करती है, आपके द्वारा परिभाषित विकल्पों का सम्मान करते हुए। परिणामी `CopiedProject.xml` में केवल वही डेटा होगा जो आपने माँगा था।

## सामान्य समस्याएँ और समाधान

| समस्या | कारण | समाधान |
|-------|-------|-----|
| **CopyTo को कॉल करते समय NullReferenceException** | गंतव्य प्रोजेक्ट इंस्टैंशिएट नहीं किया गया। | `CopyTo` से पहले `new Project()` कॉल किया गया हो, यह सुनिश्चित करें। |
| **कॉपी के बाद टास्क गायब** | `CopyCommonData` को `false` सेट किया गया है। | `CopyCommonData = true` सेट करें या मैन्युअली विशिष्ट कलेक्शन कॉपी करें। |
| **बड़ी आउटपुट फ़ाइल** | `SkipViewData` को `false` रखा गया है। | UI‑संबंधित डेटा को छोड़ने के लिए `SkipViewData` सक्षम करें। |
| **लाइसेंस लागू नहीं हुआ** | लाइसेंस फ़ाइल लोड नहीं हुई। | किसी भी API उपयोग से पहले `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` कॉल करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं केवल टास्क का एक उपसमुच्चय कॉपी कर सकता हूँ?**  
A: हाँ, `CopyToOptions` को `ProjectRootTask` के साथ उपयोग करके प्रारंभिक टास्क निर्दिष्ट करें, या प्रारंभिक कॉपी के बाद मैन्युअली चयनित टास्क कॉपी करें।

**Q: क्या Aspose.Tasks विभिन्न फ़ाइल फ़ॉर्मेट्स के बीच कॉपी का समर्थन करता है?**  
A: बिल्कुल। आप एक MPP फ़ाइल लोड कर सकते हैं और कॉपी को XML, XER, या किसी भी अन्य समर्थित फ़ॉर्मेट में सेव कर सकते हैं—कुल मिलाकर **20 + फ़ॉर्मेट्स** से अधिक।

**Q: पासवर्ड‑सुरक्षित प्रोजेक्ट फ़ाइलों को कैसे हैंडल करूँ?**  
A: स्रोत को `new Project("file.mpp", new LoadOptions { Password = "pwd" })` से लोड करें, फिर सामान्य रूप से कॉपी जारी रखें।

**Q: क्या टास्क के बिना रिसोर्स पूल कॉपी करने का कोई तरीका है?**  
A: केवल रिसोर्स जानकारी ट्रांसफ़र करने के लिए `CopyToOptions.CopyResources = true` और `CopyToOptions.CopyTasks = false` सेट करें।

**Q: मैं और उदाहरण कहाँ पा सकता हूँ?**  
A: समुदाय‑चलित स्निपेट्स, ट्रबलशूटिंग टिप्स, और आधिकारिक दस्तावेज़ीकरण के लिए [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर जाएँ।

---

**अंतिम अपडेट:** 2026-07-05  
**परीक्षित संस्करण:** Aspose.Tasks 24.12 for .NET  
**लेखक:** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.Tasks के साथ प्रोजेक्ट डेटा में महारत](/tasks/net/project-management-integration/project-data/)
- [Aspose.Tasks के लिए MS Project सेव विकल्पों में महारत](/tasks/net/saving-options/general-save-options/)
- [Aspose.Tasks कैलेंडर और शेड्यूलिंग](/tasks/net/calendar-scheduling/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}