---
date: 2026-03-05
description: Aspose.Tasks for .NET का उपयोग करके छवियों को सहेजना, छवियों के साथ HTML
  बनाना, और छवि निर्यात को अनुकूलित करना सीखें। प्रोजेक्ट को HTML के रूप में सहेजने
  के लिए चरण‑दर‑चरण गाइड।
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks for .NET के साथ छवियों को कैसे सहेजें
url: /hi/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for .NET के साथ इमेज कैसे सेव करें

## परिचय

इस ट्यूटोरियल में आप **इमेज कैसे सेव करें** यह सीखेंगे, Microsoft Project फ़ाइलों से Aspose.Tasks API for .NET का उपयोग करके। चाहे आपको रिपोर्ट में चार्ट एम्बेड करने हों, प्रोजेक्ट विज़ुअल्स वाले HTML पेज जनरेट करने हों, या सिर्फ डायग्रामेटिक रिसोर्सेज एक्सपोर्ट करने हों, नीचे दिए गए चरण आपको पूरे प्रोसेस में मार्गदर्शन करेंगे—प्रोजेक्ट ऑब्जेक्ट सेटअप से लेकर इमेज‑एक्सपोर्ट कॉलबैक को कस्टमाइज़ करने तक।

## त्वरित उत्तर
- **Aspose.Tasks में “इमेज कैसे सेव करें” का क्या अर्थ है?**  
  यह `IImageSavingCallback` इंटरफ़ेस का उपयोग करके यह नियंत्रित करने को दर्शाता है कि विज़ुअल रिसोर्सेज डिस्क पर कहाँ और कैसे लिखे जाएँ।
- **क्या मैं एम्बेडेड इमेज के साथ प्रोजेक्ट को HTML के रूप में सेव कर सकता हूँ?**  
  हाँ, `HtmlSaveOptions` को इमेज‑सेविंग कॉलबैक्स के साथ उपयोग करके आप **प्रोजेक्ट को HTML के रूप में सेव** कर सकते हैं, जिसमें सभी जनरेटेड इमेज शामिल होंगी।
- **इमेज एक्सपोर्ट के लिए लाइसेंस चाहिए?**  
  परीक्षण के लिए एक टेम्पररी इवैल्यूएशन लाइसेंस काम करता है; प्रोडक्शन उपयोग के लिए पूर्ण लाइसेंस आवश्यक है।
- **कौन से .NET संस्करण समर्थित हैं?**  
  Aspose.Tasks for .NET .NET Framework 4.5+, .NET Core 3.1+, और .NET 5/6+ को सपोर्ट करता है।
- **क्या इमेज एक्सपोर्ट (फ़ॉर्मेट, फ़ोल्डर, नामकरण) को कस्टमाइज़ करना संभव है?**  
  बिल्कुल—कॉलबैक आपको फ़ाइल नाम, फ़ॉर्मेट और डेस्टिनेशन पर पूर्ण नियंत्रण देता है।

## Aspose.Tasks के संदर्भ में “इमेज कैसे सेव करें” क्या है?
इमेज सेव करना का मतलब है प्रोजेक्ट फ़ाइल से विज़ुअल एलिमेंट्स (चार्ट, गैंट बार, रिसोर्स ग्राफ़िक्स) निकालना और उन्हें इमेज फ़ाइलों (PNG, JPEG आदि) में लिखना। Aspose.Tasks एक लचीला कॉलबैक मैकेनिज़्म प्रदान करता है, जिससे आप सटीक लोकेशन, नामकरण नियम और इमेज फ़ॉर्मेट तय कर सकते हैं।

## Aspose.Tasks से इमेज क्यों सेव करें?
- **पूर्ण प्रोग्रामेटिक कंट्रोल** – मैन्युअल UI इंटरैक्शन की आवश्यकता नहीं।  
- **क्रॉस‑प्लेटफ़ॉर्म** – .NET Core के माध्यम से Windows, Linux और macOS पर काम करता है।  
- **हाई‑फ़िडेलिटी रेंडरिंग** – इमेज मूल प्रोजेक्ट व्यू की समान गुणवत्ता रखती हैं।  
- **आसान HTML जनरेशन** – `HtmlSaveOptions` को इमेज कॉलबैक्स के साथ मिलाकर **ऑटोमैटिक इमेज के साथ HTML जनरेट** किया जा सकता है।

## आवश्यकताएँ

शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हों:

1. आपके विकास मशीन पर Visual Studio इंस्टॉल हो।  
2. Aspose.Tasks for .NET को [here](https://releases.aspose.com/tasks/net/) से डाउनलोड किया हो।  
3. C# और .NET प्रोजेक्ट स्ट्रक्चर की बेसिक समझ हो।

## नेमस्पेस इम्पोर्ट करें

सबसे पहले, आवश्यक नेमस्पेस को अपने सोर्स फ़ाइल में जोड़ें:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## चरण 1: प्रोजेक्ट ऑब्जेक्ट बनाएं

उस Microsoft Project फ़ाइल को लोड करें जिससे आप काम करना चाहते हैं:

```csharp
var project = new Project("Project1.mpp");
```

## चरण 2: सेव ऑप्शन परिभाषित करें

HTML सेव ऑप्शन बनाएं जो हमारे इमेज‑सेविंग कॉलबैक्स को भी रखेगा:

```csharp
var options = GetSaveOptions(1);
```

## चरण 3: प्रोजेक्ट को HTML के रूप में सेव करें (save project as html)

अब प्रोजेक्ट को एक HTML फ़ाइल में एक्सपोर्ट करें। HTML में रेफ़रेंस की गई इमेजेज़ को अगला कॉलबैक जनरेट करेगा:

```csharp
project.Save("document_out.html", options);
```

## चरण 4: इमेज सेविंग कॉलबैक लागू करें (customize image export)

`IImageSavingCallback` इंटरफ़ेस को इम्प्लीमेंट करें। यहाँ आप **इमेज एक्सपोर्ट** व्यवहार को कस्टमाइज़ करेंगे:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## चरण 5: निर्दिष्ट डायरेक्टरी में इमेज सेव करें

`ImageSaving` मेथड के अंदर तय करें कि प्रत्येक इमेज कहाँ स्टोर होनी चाहिए। नीचे दिया गया उदाहरण PNG रिसोर्सेज़ को अन्य फ़ॉर्मेट से अलग करता है:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Save nested resources
}
else
{
    // Save regular resources
}
```

## चरण 6: सेव ऑप्शन निर्दिष्ट करें (कॉलबैक्स सहित)

फ़ॉन्ट, CSS और इमेज के लिए कॉलबैक्स को वायर्ड करें। इससे हर विज़ुअल एलिमेंट सुसंगत रूप से हैंडल होगा:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Specify save options here
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## सामान्य समस्याएँ और समाधान

| समस्या | कारण | समाधान |
|-------|-------|-----|
| जनरेटेड HTML में इमेज नहीं दिख रही हैं | कॉलबैक वैध फ़ाइल पाथ असाइन नहीं कर रहा | सुनिश्चित करें `args.Path` लिखने योग्य फ़ोल्डर की ओर इशारा कर रहा है और `args.ImageStream` सही सेट किया गया है। |
| PNG फ़ाइलें गलत एक्सटेंशन के साथ सेव हो रही हैं | कंडीशनल लॉजिक केवल “png” सफ़िक्स चेक करता है | मजबूत डिटेक्शन के लिए `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)` उपयोग करें। |
| फ़ाइलें मूव करने के बाद HTML रेफ़रेंसेज़ टूट जाती हैं | आउटपुट फ़ोल्डर मूव करने से रिलेटिव पाथ बदल गए | HTML और इमेज फ़ोल्डर को साथ रखें या `options.ImageFolder` को तदनुसार अपडेट करें। |

## निष्कर्ष

इन चरणों का पालन करके आप अब **प्रोजेक्ट फ़ाइल से इमेज कैसे सेव करें**, **प्रोजेक्ट को HTML के रूप में सेव करें**, और **इमेज एक्सपोर्ट को अपनी एप्लिकेशन की फ़ोल्डर स्ट्रक्चर के अनुसार कस्टमाइज़ करें** यह सब जानते हैं। यह तरीका आपको **इमेज के साथ HTML जनरेट** करने की सुविधा देता है, जिसे आप रिपोर्ट, डॉक्यूमेंटेशन पोर्टल या वेब डैशबोर्ड में सहजता से एम्बेड कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

**Q1: क्या मैं Aspose.Tasks का उपयोग HTML के अलावा अन्य फ़ॉर्मेट में प्रोजेक्ट फ़ाइलों को मैनीपुलेट करने के लिए कर सकता हूँ?**  
A1: हाँ, Aspose.Tasks PDF, XLSX और MPP जैसे विभिन्न फ़ॉर्मेट को सपोर्ट करता है।

**Q2: क्या Aspose.Tasks क्लाउड स्टोरेज इंटीग्रेशन के लिए सपोर्ट प्रदान करता है?**  
A2: हाँ, Aspose.Tasks Amazon S3 और Google Drive जैसे लोकप्रिय क्लाउड स्टोरेज सेवाओं के साथ काम करने के लिए API प्रदान करता है।

**Q3: क्या Aspose.Tasks .NET Core के साथ संगत है?**  
A3: हाँ, Aspose.Tasks .NET Core के साथ संगत है, जिससे आप क्रॉस‑प्लेटफ़ॉर्म एप्लिकेशन विकसित कर सकते हैं।

**Q4: क्या मैं सेव की गई इमेज की अपीयरेंस को कस्टमाइज़ कर सकता हूँ?**  
A4: हाँ, आप कॉलबैक मेथड्स के भीतर इमेज सेविंग लॉजिक को मॉडिफाई करके इमेज की अपीयरेंस को कस्टमाइज़ कर सकते हैं।

**Q5: क्या Aspose.Tasks ट्रायल वर्ज़न प्रदान करता है?**  
A5: हाँ, आप Aspose.Tasks का फ्री ट्रायल [here](https://releases.aspose.com/) से प्राप्त कर सकते हैं।

---

**Last Updated:** 2026-03-05  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}