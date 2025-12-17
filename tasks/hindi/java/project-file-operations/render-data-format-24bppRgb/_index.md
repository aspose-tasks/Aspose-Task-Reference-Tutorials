---
date: 2025-12-17
description: जाने कैसे Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट को इमेज के रूप
  में सहेँ और इमेज रेज़ोल्यूशन बदलें। यह चरण‑दर‑चरण गाइड MS Project डेटा को 24bppRgb
  फ़ॉर्मेट में रेंडर करने को दिखाता है।
linktitle: Save Project as Image – 24bppRgb Format
second_title: Aspose.Tasks Java API
title: Aspose.Tasks के साथ प्रोजेक्ट को इमेज के रूप में सहेजें – 24bppRgb फ़ॉर्मेट
url: /hi/java/project-file-operations/render-data-format-24bppRgb/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# प्रोजेक्ट को इमेज के रूप में सहेजें – 24bppRgb फ़ॉर्मेट के साथ Aspose.Tasks

## Introduction
इस ट्यूटोरियल में आप सीखेंगे कि कैसे **save project as image** को Aspose.Tasks for Java के साथ 24bppRgb पिक्सेल फ़ॉर्मेट का उपयोग करके सहेजा जाए। MS Project डेटा को इमेज में रेंडर करना उपयोगी होता है जब आपको शेड्यूल का विज़ुअल स्नैपशॉट साझा करना हो, रिपोर्ट में टाइमलाइन एम्बेड करनी हो, या प्रोजेक्ट‑पोर्टल के लिए थंबनेल बनाना हो। हम यह भी दिखाएंगे कि कैसे **change image resolution java** को अपनी गुणवत्ता आवश्यकताओं के अनुसार बदला जाए।

## Quick Answers
- **Can I render a project to an image?** हाँ, Aspose.Tasks आपको प्रोजेक्ट को TIFF, PNG, JPEG आदि के रूप में सहेजने की अनुमति देता है।  
- **Which pixel format gives the best color depth?** `Format24bppRgb` true‑color (24‑bit) इमेज प्रदान करता है।  
- **How do I adjust the image resolution?** `ImageSaveOptions` पर `setHorizontalResolution` और `setVerticalResolution` का उपयोग करें।  
- **Do I need a license for production?** गैर‑मूल्यांकन उपयोग के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **Is this compatible with all Java versions?** Java 8 और उसके बाद के संस्करणों के साथ काम करता है।

## What is “save project as image”?
प्रोजेक्ट को इमेज के रूप में सहेजना Microsoft Project फ़ाइल (`.mpp`) के विज़ुअल प्रतिनिधित्व को रास्टर फ़ॉर्मेट (जैसे TIFF) में बदल देता है। परिणामी फ़ाइल को ब्राउज़र में दिखाया जा सकता है, दस्तावेज़ों में सम्मिलित किया जा सकता है, या मूल Project एप्लिकेशन की आवश्यकता के बिना प्रिंट किया जा सकता है।

## Why use the 24bppRgb format?
24bppRgb पिक्सेल फ़ॉर्मेट प्रत्येक पिक्सेल को लाल, हरा और नीला के लिए 8 बिट्स के साथ संग्रहीत करता है, जिससे अल्फा चैनल के बिना true‑color गुणवत्ता मिलती है। यह उन हाई‑क्लैरिटी रिपोर्टों के लिए आदर्श है जहाँ रंग की सटीकता महत्वपूर्ण होती है, जबकि 32‑बिट फ़ॉर्मेट की तुलना में फ़ाइल आकार को उचित रखता है।

## Prerequisites
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. **Java Development Kit (JDK)** – आपके मशीन पर JDK 8 या नया स्थापित हो।  
2. **Aspose.Tasks for Java** – इसे [here](https://releases.aspose.com/tasks/java/) से डाउनलोड और इंस्टॉल करें।  
3. **Basic Java knowledge** – Java सिंटैक्स और प्रोजेक्ट सेटअप की परिचितता कोड स्निपेट्स को समझने में मदद करेगी।

## Import Packages
सबसे पहले, आवश्यक Aspose.Tasks क्लासेज़ को अपने Java प्रोजेक्ट में इम्पोर्ट करें:

```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step‑by‑Step Guide

### Step 1: Define Data Directory
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` को उस पूर्ण पथ से बदलें जहाँ आपका `.mpp` फ़ाइल स्थित है।

### Step 2: Load Project File
```java
Project project = new Project(dataDir + "project.mpp");
```
यह पंक्ति Microsoft Project फ़ाइल (`project.mpp`) को पढ़ती है और एक `Project` ऑब्जेक्ट बनाती है जिसे Aspose.Tasks हेरफेर कर सकता है।

### Step 3: Configure Image Save Options
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
यहाँ हम आउटपुट फ़ॉर्मेट को TIFF सेट करते हैं,72 dpi** रेज़ोल्यूशन निर्दिष्ट करते हैं (आप अपनी आवश्यकता के अनुसार इन मानों को बदल सकते हैं – यही वह जगह है जहाँ आप **change image resolution java** करते हैं), और true‑color आउटपुट के लिए 24bppRgb पिक्सेल फ़ॉर्मेट चुनते हैं।

### Step 4: Save Project Data as Image
```java
project.save(dataDir + "resFile.tif", options);
```
`save` मेथड ऊपर परिभाषित विकल्पों का उपयोग करके रेंडर की गई इमेज को `resFile.tif` में लिखता है।

## Common Issues and Solutions
| समस्या | कारण | समाधान |
|-------|--------|-----|
| **Blank image output** | प्रोजेक्ट व्यू खाली हो सकता है। | सेव करने से पहले `project.setDefaultView(ViewType.Gantt);` कॉल करें। |
| **Low‑quality image** | रेज़ोल्यूशन बहुत कम सेट किया गया है। | `setHorizontalResolution` और `setVerticalResolution` को बढ़ाएँ (उदाहरण: 150 dpi)। |
| **Unsupported pixel format** | पुराने Aspose.Tasks संस्करण का उपयोग किया जा रहा है। | नवीनतम Aspose.Tasks for Java रिलीज़ में अपग्रेड करें। |

## Conclusion
अब आप जानते हैं कि कैसे **save project as image** को 24bppRgb फ़ॉर्मेट के साथ और Aspose.Tasks for Java का उपयोग करके रेज़ोल्यूशन को समायोजित किया जाए। यह तरीका आपको आपके प्रोजेक्ट शेड्यूल की स्पष्ट, रंग‑सटीक विज़ुअल प्रतिनिधित्व बनाने की अनुमति देता है, जिसे आप साझा करने, रिपोर्टिंग या अभिलेखीय उद्देश्यों के लिए उपयोग कर सकते हैं।

## FAQ's
### Q: क्या मैं प्रोजेक्ट डेटा को अन्य इमेज फ़ॉर्मेट में रेंडर कर सकता हूँ?
A: हाँ, Aspose.Tasks प्रोजेक्ट डेटा को PNG, JPEG, BMP आदि जैसे विभिन्न इमेज फ़ॉर्मेट में रेंडर करने का समर्थन करता है।

### Q: क्या Aspose.Tasks विभिन्न संस्करणों के MS Project के साथ संगत है?
A: हाँ, Aspose.Tasks MS Project के कई संस्करणों जैसे 2003, 2007, 2010, 2013, और 2016 को सपोर्ट करता है।

### Q: क्या मैं रेंडर की गई इमेज का रेज़ोल्यूशन और पिक्सेल फ़ॉर्मेट कस्टमाइज़ कर सकता हूँ?
A: हाँ, आप अपनी आवश्यकताओं के अनुसार Aspose.Tasks का उपयोग करके रेज़ोल्यूशन और पिक्सेल फ़ॉर्मेट को कस्टमाइज़ कर सकते हैं।

### Q: क्या Aspose.Tasks को व्यावसायिक उपयोग के लिए लाइसेंस की आवश्यकता है?
A: हाँ, Aspose.Tasks के व्यावसायिक उपयोग के लिए आपको लाइसेंस खरीदना होगा। आप परीक्षण उद्देश्यों के लिए एक अस्थायी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

### Q: मैं Aspose.Tasks के लिए समर्थन कहाँ प्राप्त कर सकता हूँ?
A: आप Aspose.Tasks के लिए समर्थन [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) से प्राप्त कर सकते हैं।

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}