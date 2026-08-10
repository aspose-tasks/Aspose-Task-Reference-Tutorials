---
date: 2026-06-15
description: जाने कैसे mpp को pdf में परिवर्तित करें और Aspose.Tasks for Java का उपयोग
  करके Resource Usage और Sheet व्यूज़ को रेंडर करें। हमारे step‑by‑step गाइड का पालन
  करें ताकि timescale सेट कर सकें और आसानी से विस्तृत PDF reports जेनरेट कर सकें।
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: MPP को PDF में परिवर्तित करें और Resource Usage View रेंडर करें – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: MPP को PDF में परिवर्तित करें और Resource Usage View रेंडर करें – Aspose.Tasks
url: /hi/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MPP को PDF में बदलें और रिसोर्स उपयोग व्यू रेंडर करें – Aspose.Tasks

इस ट्यूटोरियल में आप सीखेंगे **MPP को PDF में कैसे बदलें** जबकि Microsoft Project फ़ाइल के रिसोर्स उपयोग और शीट व्यू को रेंडर करेंगे। Aspose.Tasks for Java का उपयोग करने से सर्वर पर Microsoft Project की आवश्यकता समाप्त हो जाती है, जिससे आप MPP फ़ाइलों से PDF रिपोर्ट तेज़ और विश्वसनीय तरीके से बना सकते हैं। हम आपको **टाइमस्केल कैसे सेट करें** भी दिखाएंगे ताकि आउटपुट आपकी रिपोर्टिंग आवश्यकताओं से मेल खाए।

## त्वरित उत्तर
- **Aspose.Tasks क्या करता है?** यह Microsoft Project (MPP) फ़ाइलों को पढ़ता, संशोधित करता और बदलता है बिना MS Project स्थापित किए।  
- **क्या मैं एक लाइन कोड में MPP को PDF में बदल सकता हूँ?** हाँ – प्रोजेक्ट लोड करें, SaveOptions सेट करें, और `save` कॉल करें।  
- **कौन से टाइमस्केल समर्थित हैं?** Days, ThirdsOfMonths, और Months।  
- **क्या उत्पादन के लिए लाइसेंस चाहिए?** गैर‑ट्रायल डिप्लॉयमेंट के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **क्या लाइब्रेरी Java 8+ के साथ संगत है?** बिल्कुल – यह Java 8 और बाद के संस्करणों को सपोर्ट करती है।

## Convert mpp to pdf क्या है?
*Convert mpp to pdf* वह प्रक्रिया है जिसमें Microsoft Project (.mpp) फ़ाइल लेकर एक पोर्टेबल डॉक्यूमेंट फॉर्मेट (PDF) संस्करण बनाया जाता है जो प्रोजेक्ट की तालिकाएँ, शेड्यूल, चार्ट और रिसोर्स आवंटन को सटीक रूप से पुनः उत्पन्न करता है। परिणामी PDF को आसानी से साझा, प्रिंट और आर्काइव किया जा सकता है बिना प्राप्तकर्ता की मशीन पर Microsoft Project स्थापित किए।

## Aspose.Tasks के साथ प्रोजेक्ट को PDF में क्यों बदलें?
Aspose.Tasks **50+ इनपुट और आउटपुट फॉर्मेट** को सपोर्ट करता है और पूरी फ़ाइल को मेमोरी में लोड किए बिना सैकड़ों पृष्ठों वाले प्रोजेक्ट को रेंडर कर सकता है, जिससे RAM उपयोग 70 % तक घट जाता है। PDF आउटपुट तालिकाएँ, चार्ट और रिसोर्स आवंटन को बरकरार रखता है, जिससे यह स्टेकहोल्डर वितरण और आर्काइविंग के लिए आदर्श है।

## आवश्यकताएँ
1. **Java Development Kit (JDK)** – आपके मशीन पर Java 8 या नया स्थापित हो।  
2. **Aspose.Tasks for Java** – नवीनतम JAR को [download page](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  

## Aspose.Tasks for Java का उपयोग करके mpp को pdf कैसे बदलें?
अपने स्रोत MPP फ़ाइल को लोड करें, इच्छित टाइमस्केल कॉन्फ़िगर करें, प्रस्तुति फॉर्मेट को **ResourceUsage** सेट करें, और परिणाम को PDF के रूप में सहेजें। यह एंड‑टू‑एंड फ्लो केवल कुछ API कॉल्स की आवश्यकता रखता है और सामान्य प्रोजेक्ट आकारों के लिए एक सेकंड से कम समय में चलता है।

### चरण 1: स्रोत प्रोजेक्ट पढ़ें
`Project` क्लास एक Microsoft Project फ़ाइल को मेमोरी में लोड किए जाने का प्रतिनिधित्व करती है, जो उसके डेटा और संरचना तक पहुंच प्रदान करती है।  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### चरण 2: आवश्यक TimeScale सेटिंग्स के साथ SaveOptions परिभाषित करें
`SaveOptions` यह कॉन्फ़िगर करता है कि प्रोजेक्ट कैसे सहेजा जाता है, जिससे आप टाइमस्केल जैसे फॉर्मेट‑विशिष्ट सेटिंग्स निर्दिष्ट कर सकते हैं।  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### चरण 3: प्रस्तुति फॉर्मेट को ResourceUsage सेट करें
`PresentationFormat` निर्धारित करता है कि आउटपुट दस्तावेज़ में कौन सा प्रोजेक्ट व्यू (जैसे ResourceUsage) रेंडर किया जाएगा।  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### चरण 4: प्रोजेक्ट को PDF के रूप में सहेजें
`project.save` प्रदान किए गए `SaveOptions` का उपयोग करके प्रोजेक्ट को फ़ाइल में लिखता है, जिससे अंतिम PDF बनता है।  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### चरण 5: अन्य TimeScale सेटिंग्स के लिए व्यू रेंडर करें
पिछले चरणों को दोहराएँ, `TimeScale` मान को बदलकर अतिरिक्त टाइमस्केल व्यू रेंडर करें।  
```java
// Save the Project
project.save(dataDir + days, options);
```

### चरण 6: वैकल्पिक – बैच में कई प्रोजेक्ट्स को बदलें
यदि आपको कई फ़ाइलों के लिए **प्रोजेक्ट को pdf में बदलना** है, तो ऊपर की लॉजिक को एक लूप में रखें जो *.mpp* फ़ाइलों की डायरेक्टरी पर इटररेट करता है। यह तरीका **ms project pdf** फ़ाइलों को बड़े पैमाने पर न्यूनतम कोड बदलाव के साथ **सहेजता** है।  
निम्नलिखित कोड वांछित सेटिंग्स के साथ MPP फ़ाइल को PDF में बदलने का पूर्ण उदाहरण दर्शाता है।  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## सामान्य समस्याएँ और समाधान
- **PDF में फ़ॉन्ट गायब** – सुनिश्चित करें कि आवश्यक फ़ॉन्ट सर्वर पर स्थापित हों या उन्हें `PdfSaveOptions` के माध्यम से एम्बेड करें।  
- **बड़ी प्रोजेक्ट फ़ाइलें OutOfMemoryError देती हैं** – संसाधनों को आवश्यकता अनुसार लोड करने के लिए `LoadOptions.setLoadAllResources(false)` उपयोग करें।  
- **टाइमस्केल रेंडरिंग गलत** – सुनिश्चित करें कि `options.setTimeScale(TimeScale.Days)` (या अन्य enum) वांछित ग्रैन्युलैरिटी से मेल खाता है।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.Tasks रिसोर्स उपयोग और शीट के अलावा अन्य व्यू रेंडर कर सकता है?**  
A: हाँ, यह Gantt Chart, Task Usage, Calendar, और कई अतिरिक्त व्यू को भी सपोर्ट करता है।

**Q: क्या Aspose.Tasks विभिन्न संस्करणों की Microsoft Project फ़ाइलों के साथ संगत है?**  
A: बिल्कुल – यह Project 2000 से लेकर Project 2021 तक के MPP, MPT, और XML फॉर्मेट को संभालता है।

**Q: क्या मैं रेंडर किए गए व्यू की उपस्थिति को कस्टमाइज़ कर सकता हूँ?**  
A: हाँ, आप `PdfSaveOptions` और `PresentationOptions` के माध्यम से रंग, फ़ॉन्ट, और कॉलम लेआउट बदल सकते हैं।

**Q: क्या Aspose.Tasks को Microsoft Project स्थापित करने की आवश्यकता है?**  
A: नहीं, यह एक स्टैंडअलोन लाइब्रेरी है और किसी भी Java‑संगत वातावरण में काम करती है।

**Q: तकनीकी समर्थन कहाँ प्राप्त कर सकता हूँ?**  
A: समर्थन [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/) के माध्यम से उपलब्ध है।

---

**अंतिम अपडेट:** 2026-06-15  
**परीक्षित संस्करण:** Aspose.Tasks 24.12 for Java  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Tasks में रिसोर्स उपयोग और शीट व्यू रेंडर करें](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [Aspose.Tasks में PDF निर्यात कैसे करें – Save As PDF](/tasks/java/project-file-operations/save-as-pdf/)
- [Aspose.Tasks for Java के साथ MPP फ़ाइलें कैसे बनाएं](/tasks/java/project-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}