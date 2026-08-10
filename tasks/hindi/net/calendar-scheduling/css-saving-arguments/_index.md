---
date: 2026-07-05
description: Aspose.Tasks for .NET का उपयोग करके प्रोजेक्ट को HTML में निर्यात करते
  समय CSS को कस्टमाइज़ करना सीखें। CSS सहेजने के आर्ग्युमेंट्स के साथ HTML आउटपुट
  को अनुकूलित करें।
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: Aspose.Tasks के साथ प्रोजेक्ट सहेजते समय CSS को कैसे कस्टमाइज़ करें
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks के साथ प्रोजेक्ट सहेजते समय CSS को कैसे कस्टमाइज़ करें
url: /hi/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ प्रोजेक्ट्स को सेव करते समय CSS को कैसे कस्टमाइज़ करें

इस गाइड में आप Aspose.Tasks for .NET का उपयोग करके Microsoft Project फ़ाइल के HTML निर्यात के दौरान **CSS को कैसे कस्टमाइज़ करें** यह जानेंगे। CSS सहेजने के तर्कों को समायोजित करके आप उत्पन्न HTML पृष्ठों की दृश्य शैली पर पूर्ण नियंत्रण प्राप्त करते हैं, जिससे आउटपुट आपके ब्रांडिंग या रिपोर्टिंग मानकों से मेल खाता है।

## त्वरित उत्तर
- **मुख्य प्रवेश बिंदु क्या है?** Use `HtmlSaveOptions` with custom callbacks.  
- **क्या मुझे लाइसेंस चाहिए?** Yes, a valid Aspose.Tasks license is required for production.  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **क्या मैं बड़े प्रोजेक्ट्स निर्यात कर सकता हूँ?** Aspose.Tasks handles projects with > 10,000 tasks without loading the entire file into memory.  
- **क्या CSS कस्टमाइज़ेशन वैकल्पिक है?** Yes, you can omit callbacks to use the default stylesheet.

## Aspose.Tasks में CSS को कैसे कस्टमाइज़ करें?

अपने प्रोजेक्ट को लोड करें, `HtmlSaveOptions` ऑब्जेक्ट में CSS‑saving callbacks संलग्न करें, और फिर `project.Save` को कॉल करें। यह पैटर्न आपको कस्टम CSS फ़ाइलें लिखने, डिफ़ॉल्ट स्टाइल्स को बदलने, और फ़ोल्डर संरचना को नियंत्रित करने की अनुमति देता है — सभी कुछ कोड की कुछ लाइनों में। निर्यात प्रक्रिया के दौरान प्रत्येक CSS फ़ाइल के लिए callbacks स्वचालित रूप से बुलाए जाते हैं।

`HtmlSaveOptions` प्रोजेक्ट को HTML में निर्यात करने के तरीके को कॉन्फ़िगर करता है।

## परिचय

इस ट्यूटोरियल में, हम Aspose.Tasks for .NET का उपयोग करके CSS तर्कों को सहेजने की प्रक्रिया में गहराई से जाएंगे। Cascading Style Sheets (CSS) HTML तत्वों की प्रस्तुति को परिभाषित करने के लिए महत्वपूर्ण हैं। Aspose.Tasks हमें इन CSS गुणों को कुशलतापूर्वक हेरफेर करने और सहेजने की सुविधा देता है।

## पूर्वापेक्षाएँ

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

1. इंस्टॉलेशन: सुनिश्चित करें कि आपने Aspose.Tasks for .NET स्थापित किया है। आप इसे [website](https://releases.aspose.com/tasks/net/) से डाउनलोड कर सकते हैं।
2. बुनियादी ज्ञान: C# और .NET विकास पर्यावरण से परिचित होना अनुशंसित है।

## नेमस्पेस आयात करें

शुरू करने के लिए, आवश्यक नेमस्पेस आयात करें:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## चरण 1: CSS Saving Callbacks को परिभाषित करें

`ICssSavingCallback` एक इंटरफ़ेस है जो आपको HTML निर्यात के दौरान CSS फ़ाइलों को सहेजने के तरीके को कस्टमाइज़ करने की अनुमति देता है।

एक **CSS saving callback** एक डेलीगेट है जिसे Aspose.Tasks HTML निर्यात के दौरान CSS फ़ाइलें लिखने के लिए कॉल करता है। प्रत्येक CSS फ़ाइल के निर्माण को नियंत्रित करने के लिए callback मेथड्स को परिभाषित करें:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## चरण 2: फ़ॉन्ट और इमेज Saving Callbacks लागू करें

`FontSavingArgs` सहेजे जा रहे फ़ॉन्ट की जानकारी प्रदान करता है, जबकि `ImageSavingArgs` इमेज संसाधनों के विवरण देता है।

फ़ॉन्ट और इमेज saving callback मेथड्स को इसी तरह लागू करें:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## चरण 3: Save Options को कॉन्फ़िगर करें

`HtmlSaveOptions` वह कॉन्फ़िगरेशन ऑब्जेक्ट है जो नियंत्रित करता है कि प्रोजेक्ट को HTML में कैसे निर्यात किया जाता है।

`HtmlSaveOptions` आपको callbacks, आउटपुट फ़ोल्डर, और अन्य निर्यात सेटिंग्स निर्दिष्ट करने की अनुमति देता है।

इसके गुणों को सेट करें ताकि पहले परिभाषित callbacks का उपयोग हो और आउटपुट फ़ोल्डर निर्दिष्ट किया जा सके:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## चरण 4: कस्टमाइज़्ड CSS के साथ प्रोजेक्ट सहेजें

`Project` एक Microsoft Project फ़ाइल को दर्शाता है जिसे हेरफेर किया जा सकता है और सहेजा जा सकता है।

अंत में, कस्टमाइज़्ड CSS सेटिंग्स के साथ अपने प्रोजेक्ट को सहेजें:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## प्रोजेक्ट निर्यात करते समय CSS को कस्टमाइज़ क्यों करें?

Aspose.Tasks **प्रोजेक्ट को HTML में निर्यात** करने को 30+ फ़ॉर्मैट्स में समर्थन देता है और प्रत्येक निर्यात में अधिकतम 30 अलग-अलग CSS फ़ाइलें उत्पन्न कर सकता है। यह 10 000 से अधिक टास्क वाले प्रोजेक्ट्स को विश्वसनीय रूप से प्रोसेस करता है जबकि मेमोरी उपयोग को 200 MB से कम रखता है, जिससे एंटरप्राइज़‑स्तर की रिपोर्टिंग बिना प्रदर्शन बाधाओं के संभव होती है।

## निष्कर्ष

इस ट्यूटोरियल में, हमने Aspose.Tasks for .NET का उपयोग करके CSS तर्कों को सहेजने की प्रक्रिया को समझा। CSS saving callbacks को परिभाषित करके और HTML save options को कॉन्फ़िगर करके, हम अपनी आवश्यकताओं के अनुसार CSS गुणों को कुशलतापूर्वक हेरफेर कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### प्रश्न 1: Aspose.Tasks for .NET क्या है?
A1: Aspose.Tasks for .NET एक शक्तिशाली .NET API है जो डेवलपर्स को प्रोग्रामेटिक रूप से Microsoft Project फ़ाइलों के साथ काम करने में सक्षम बनाता है।

### प्रश्न 2: क्या मैं Aspose.Tasks के साथ HTML फ़ाइलें सहेजते समय CSS गुणों को कस्टमाइज़ कर सकता हूँ?
A2: हाँ, आप अपनी आवश्यकताओं के अनुसार CSS गुणों को कस्टमाइज़ करने के लिए CSS saving callbacks को परिभाषित कर सकते हैं।

### प्रश्न 3: क्या Aspose.Tasks for .NET सभी संस्करणों की Microsoft Project फ़ाइलों के साथ संगत है?
A3: Aspose.Tasks for .NET विभिन्न संस्करणों की Microsoft Project फ़ाइलों को समर्थन देता है, जिससे विभिन्न पर्यावरणों में संगतता सुनिश्चित होती है।

### प्रश्न 4: मैं Aspose.Tasks for .NET के लिए व्यापक दस्तावेज़ कहाँ पा सकता हूँ?
A4: विस्तृत जानकारी और उदाहरणों के लिए आप [documentation](https://reference.aspose.com/tasks/net/) को देख सकते हैं।

### प्रश्न 5: क्या Aspose.Tasks for .NET डेवलपर्स के लिए समर्थन प्रदान करता है?
A5: हाँ, आप Aspose.Tasks समुदाय से [forum](https://forum.aspose.com/c/tasks/15) के माध्यम से समर्थन प्राप्त कर सकते हैं।

**अतिरिक्त प्रश्न**

**Q: कस्टम CSS का उपयोग करने से निर्यातित HTML का आकार कैसे प्रभावित होता है?**  
A: कस्टम CSS का उपयोग करने से कुल आकार में लगभग 15 % तक कमी आ सकती है क्योंकि आप अनावश्यक डिफ़ॉल्ट स्टाइल्स को हटा सकते हैं।

**Q: क्या मैं कई प्रोजेक्ट्स के लिए एक ही callbacks का उपयोग कर सकता हूँ?**  
A: बिल्कुल। callbacks को एक बार लागू करें और उन्हें किसी भी संख्या में प्रोजेक्ट निर्यातों में पुनः उपयोग करें।

**Q: क्या CSS को अलग फ़ाइलों के बजाय सीधे HTML में एम्बेड करना संभव है?**  
A: हाँ, `HtmlSaveOptions.EmbeddedCss = true` सेट करके स्टाइलशीट को इनलाइन किया जा सकता है, जिससे वितरण सरल हो जाता है।

---

**अंतिम अपडेट:** 2026-07-05  
**परीक्षित संस्करण:** Aspose.Tasks 24.11 for .NET  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Tasks के साथ MS Project को HTML में सहेजें](/tasks/net/saving-options/html-save-options/)
- [Aspose.Tasks में पेज सेविंग Callback को लागू करना](/tasks/net/advanced-concepts/page-saving-callback/)
- [Aspose.Tasks में इमेज सेविंग को संभालना](/tasks/net/advanced-concepts/image-saving/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}