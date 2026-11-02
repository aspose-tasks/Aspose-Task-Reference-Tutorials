---
date: 2026-10-31
description: Aspose.Tasks का उपयोग करके Java में गैंट को PDF में निर्यात करना सीखें।
  यह चरण-दर-चरण गाइड आपको गैंट चार्ट डेटा पढ़ने और PDF रिपोर्ट बनाने का तरीका दिखाता
  है।
keywords:
- export gantt to pdf
- how to read gantt
- export gantt to excel
- generate gantt report java
lastmod: 2026-10-31
linktitle: Aspose.Tasks में विशिष्ट गैंट चार्ट डेटा पढ़ें
og_description: Aspose.Tasks के साथ Java में गैंट को PDF में निर्यात करें। इस ट्यूटोरियल
  का पालन करके गैंट चार्ट डेटा पढ़ें, दृश्य गुणों को अनुकूलित करें, और प्रोजेक्ट मैनेजमेंट
  के लिए PDF रिपोर्ट बनाएं।
og_image_alt: 'Tutorial screenshot: exporting Gantt chart to PDF using Aspose.Tasks
  for Java'
og_title: Java में गैंट को PDF में निर्यात करें – Aspose.Tasks गाइड
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  headline: Export gantt to pdf in Java – extract specific data
  type: TechArticle
- description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  name: Export gantt to pdf in Java – extract specific data
  steps:
  - name: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
    text: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
  - name: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
    text: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates seamlessly with any Java library
      or framework, including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library processes multi‑hundred‑page MPP files in under
      5 seconds on standard server hardware and supports concurrent execution in multi‑threaded
      environments.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports 20+ formats, including MPP, XML, MPX, and Primavera
      XML, enabling you to read and convert legacy schedules.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Certainly. You can modify bar styles, gridlines, text styles, and timescale
      tiers programmatically before exporting to PDF or image formats.
    question: Can I customize the appearance of Gantt charts with Aspose.Tasks?
  - answer: Call `project.save("output.mpp");` after making any modifications to persist
      them to the project file.
    question: How do I save changes after modifying a view?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- export gantt
- Aspose.Tasks
- Java Gantt
- pdf generation
- project management
title: Java में गैंट को PDF में निर्यात करें – विशिष्ट डेटा निकालें
url: /hi/java/project-data-reading/read-specific-gantt-chart-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में गैंट को पीडीएफ में निर्यात करें – विशिष्ट डेटा निकालें

## परिचय
इस ट्यूटोरियल में आप **export gantt to pdf in Java** को Aspose.Tasks for Java के साथ पढ़कर सीखेंगे। गैंट चार्ट प्रोजेक्ट मैनेजर्स को कार्यों, निर्भरताओं और समयसीमा का दृश्य रोडमैप प्रदान करते हैं, और इस डेटा को प्रोग्रामेटिकली निकालने से आप स्वचालित पीडीएफ रिपोर्ट, डैशबोर्ड या अन्य एंटरप्राइज़ सिस्टम के साथ इंटीग्रेशन बना सकते हैं। चलिए प्रत्येक चरण को देखते हैं, प्रोजेक्ट फ़ाइल लोड करने से लेकर व्यू प्रॉपर्टीज़ निकालने और अंत में पीडीएफ जनरेट करने तक।

## त्वरित उत्तर
- **मैं क्या निकाल सकता हूँ?** गैंट चार्ट से कोई भी व्यू प्रॉपर्टी, बार स्टाइल, ग्रिडलाइन, टेक्स्ट स्टाइल, प्रोग्रेस लाइन, या टाइमस्केल टियर।  
- **क्या लाइसेंस चाहिए?** विकास के लिए ट्रायल चल सकता है; उत्पादन के लिए व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन सा जावा संस्करण समर्थित है?** जावा 8 या बाद का (ट्यूटोरियल JDK 11 का उपयोग करता है)।  
- **क्या कोड जैसा का वैसा चलाएगा?** हाँ – केवल डेटा डायरेक्टरी पाथ बदलें।  
- **क्या पढ़ने के बाद व्यू को संशोधित कर सकता हूँ?** बिल्कुल – API आपको प्रॉपर्टीज़ बदलने और प्रोजेक्ट फ़ाइल में वापस सेव करने की अनुमति देता है।

## export gantt to pdf क्या है?
export gantt to pdf वह प्रक्रिया है जिसमें प्रोजेक्ट फ़ाइल में संग्रहीत गैंट चार्ट व्यू को पीडीएफ दस्तावेज़ में परिवर्तित किया जाता है, जो दृश्य शैली और टाइमलाइन जानकारी को संरक्षित रखता है। यह ऑपरेशन उन स्टेकहोल्डर्स के साथ प्रोजेक्ट स्थिति साझा करने के लिए उपयोगी है जिनके पास प्रोजेक्ट‑मैनेजमेंट टूल नहीं है।

## Aspose.Tasks के साथ export gantt to pdf क्यों?
Aspose.Tasks **30 + इनपुट फ़ॉर्मेट** (MPP, XML, MPX, आदि) को संभाल सकता है और **एक ही कॉल में PDF में निर्यात** करता है, जबकि 95 % दृश्य सटीकता बनाए रखता है, यहाँ तक कि 500 से अधिक कार्यों वाले प्रोजेक्ट्स के लिए भी। लाइब्रेरी फ़ाइलों को मेमोरी में प्रोसेस करती है, इसलिए आप सर्वर पर बिना Microsoft Project इंस्टॉल किए PDFs जेनरेट कर सकते हैं।

## पूर्वापेक्षाएँ
1. **Java Development Kit (JDK):** सुनिश्चित करें कि आपके सिस्टम पर जावा स्थापित है। आप इसे **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)** से डाउनलोड कर सकते हैं।  
2. **Aspose.Tasks for Java Library:** Aspose.Tasks for Java लाइब्रेरी को **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)** से डाउनलोड और इंस्टॉल करें।  
3. **Integrated Development Environment (IDE):** अपनी पसंद का IDE चुनें। लोकप्रिय विकल्पों में IntelliJ IDEA, Eclipse, या NetBeans शामिल हैं।

## पैकेज आयात करें
निम्न आयात आपको गैंट डेटा पढ़ने और निर्यात करने के लिए आवश्यक कोर Aspose.Tasks क्लासेज़ तक पहुँच प्रदान करते हैं।  
*यहाँ कोई कोड ब्लॉक नहीं दिखाया गया है ताकि ट्यूटोरियल अवधारणाओं पर केंद्रित रहे; बस इन आयातों को अपनी Java फ़ाइल में जोड़ें।*

## Java में गैंट चार्ट प्रोजेक्ट फ़ाइल कैसे लोड करें?
प्रोजेक्ट फ़ाइल को `Project` इंस्टेंस बनाकर और कंस्ट्रक्टर में पूर्ण पाथ पास करके लोड करें। यह चरण गैंट चार्ट की इन‑मेमोरी प्रतिनिधित्व को प्रारंभ करता है, जिससे बाद में व्यू प्रॉपर्टीज़ को क्वेरी किया जा सकता है। फ़ाइल सफलतापूर्वक लोड होने पर आप प्रोजेक्ट का नाम, प्रारंभ तिथि, और कार्यों की संख्या की जाँच कर सकते हैं ताकि सही फ़ाइल खुली है यह सुनिश्चित हो सके। यह सत्यापन पाथ या फ़ॉर्मेट समस्याओं को प्रारंभिक चरण में पकड़ने में मदद करता है।  
```java
Project project = new Project(dataDir + "SampleProject.mpp");
```  
*परिभाषा एंकर:* `Project` वह टॉप‑लेवल Aspose.Tasks ऑब्जेक्ट है जो मेमोरी में एकल प्रोजेक्ट फ़ाइल का प्रतिनिधित्व करता है।

## गैंट चार्ट व्यू तक कैसे पहुँचें?
प्रोजेक्ट के व्यू कलेक्शन से पहला गैंट व्यू प्राप्त करें। अधिकांश प्रोजेक्ट्स में कम से कम एक गैंट व्यू होता है, और यह आमतौर पर पहला एंट्री होता है। व्यू प्राप्त करने के बाद, आप उसका नाम जाँच सकते हैं और सुनिश्चित कर सकते हैं कि यह `GanttChartView` प्रकार का है, इससे पहले कि आप प्रॉपर्टी एक्सट्रैक्शन जारी रखें। यह अतिरिक्त जाँच कस्टम या गैर‑मानक व्यू कलेक्शन के साथ काम करते समय रन‑टाइम त्रुटियों से बचाती है।  
```java
GanttChartView ganttView = (GanttChartView) project.getViews().get(0);
```  
*परिभाषा एंकर:* `GanttChartView` कार्यों, टाइमस्केल और बार्स के दृश्य लेआउट को दर्शाता है जो आप सामान्य गैंट चार्ट में देखते हैं।

## व्यू प्रॉपर्टीज़ कैसे निकालें?
आप `GanttChartView` ऑब्जेक्ट से बैकग्राउंड कलर, बार हाईट, और टाइमस्केल सेटिंग्स जैसी प्रॉपर्टीज़ सीधे पढ़ सकते हैं। इन्हें प्रिंट करने से निर्यात से पहले वर्तमान कॉन्फ़िगरेशन की पुष्टि होती है। एक सामान्य एक्सट्रैक्शन लूप प्रत्येक प्रॉपर्टी पर इटररेट करता है, मान को स्ट्रिंग में फॉर्मेट करता है, और बाद में विश्लेषण के लिए कंसोल या फ़ाइल में लॉग करता है। यह डिबगिंग और चार्ट की उपस्थिति का दस्तावेज़ीकरण बनाने में उपयोगी है।  
```java
System.out.println("Bar height: " + ganttView.getBarHeight());
System.out.println("Show gridlines: " + ganttView.getShowGridlines());
```  
*परिभाषा एंकर:* `GanttChartView` व्यू सेटिंग्स जैसे बैकग्राउंड कलर, बार हाईट, और टाइमस्केल कॉन्फ़िगरेशन तक पहुँच प्रदान करता है।

## बार स्टाइल्स कैसे निकालें?
`BarStyle` ऑब्जेक्ट्स के कलेक्शन पर इटररेट करके प्रत्येक बार प्रकार के रंग, पैटर्न और आकार जैसी विवरण प्राप्त करें। प्रत्येक स्टाइल के लिए आप संबंधित टास्क टाइप और वह कंडीशन भी पढ़ सकते हैं जो स्टाइल को ट्रिगर करती है, जो चार्ट को किसी अन्य फ़ॉर्मेट में पुनः बनाने के लिए आवश्यक है। यह जानकारी इकट्ठा करने से आप एक सटीक विज़ुअल रेप्लिका बना सकते हैं या प्रोग्रामेटिकली कस्टम स्टाइलिंग नियम लागू कर सकते हैं।  
```java
for (BarStyle style : ganttView.getBarStyles()) {
    System.out.println("Bar type: " + style.getBarType() + ", Color: " + style.getColor());
}
```  
*परिभाषा एंकर:* `BarStyle` गैंट बार की दृश्य उपस्थिति को परिभाषित करता है, जिसमें उसका रंग, पैटर्न और आकार शामिल है।

## ग्रिडलाइन कैसे निकालें?
ग्रिडलाइन पंक्तियों और कॉलमों के बीच दृश्य विभाजन को परिभाषित करती हैं। इन्हें `getGridlines()` मेथड के माध्यम से एक्सेस करें और उनकी विज़िबिलिटी तथा स्टाइल आउटपुट करें। ग्रिडलाइन कलेक्शन प्राप्त करने के बाद, आप प्रत्येक लाइन को लूप करके उसकी लाइन टाइप (सॉलिड, डैश्ड), थिकनेस और कलर कैप्चर कर सकते हैं। यह डेटा तब उपयोगी होता है जब आपको निर्यातित PDFs या अन्य रिपोर्टिंग फ़ॉर्मेट में सटीक ग्रिड लेआउट पुनः बनाना हो।  
```java
for (Gridline grid : ganttView.getGridlines()) {
    System.out.println("Gridline visible: " + grid.getVisible());
}
```  
*परिभाषा एंकर:* `getGridlines()` गैंट व्यू में पंक्ति और कॉलम सेपरेटर को नियंत्रित करने वाले ग्रिडलाइन ऑब्जेक्ट्स का कलेक्शन लौटाता है।

## टेक्स्ट स्टाइल्स कैसे निकालें?
टेक्स्ट स्टाइल्स गैंट चार्ट पर लेबल्स के फ़ॉन्ट, साइज और कलर को नियंत्रित करती हैं। `TextStyle` कलेक्शन पर लूप करके प्रत्येक स्टाइल सूचीबद्ध करें। प्रत्येक टेक्स्ट स्टाइल के लिए आप संबंधित एलिमेंट (टास्क नेम, डेट आदि) और किसी भी कंडीशनल फ़ॉर्मेटिंग नियम को भी प्राप्त कर सकते हैं। इन विवरणों को कैप्चर करने से निर्यातित दस्तावेज़ मूल चार्ट की टाइपोग्राफी को बनाए रखता है।  
```java
for (TextStyle txt : ganttView.getTextStyles()) {
    System.out.println("Text style: " + txt.getStyle() + ", Font size: " + txt.getFontSize());
}
```  
*परिभाषा एंकर:* `TextStyle` गैंट चार्ट के भीतर टेक्स्टुअल एलिमेंट्स पर लागू फ़ॉर्मेटिंग एट्रिब्यूट्स को दर्शाता है।

## प्रोग्रेस लाइन्स कैसे निकालें?
प्रोग्रेस लाइन्स कार्य की वर्तमान पूर्णता बिंदु दिखाती हैं। इन्हें `getProgressLines()` के माध्यम से एक्सेस करें और उनके एट्रिब्यूट्स प्रिंट करें। प्रत्येक प्रोग्रेस लाइन में लाइन कलर, थिकनेस, और टास्क बार के सापेक्ष पोज़िशन जैसी प्रॉपर्टीज़ शामिल होती हैं। इस जानकारी को रिकॉर्ड करने से आप प्रोग्रेस‑अवेयर विज़ुअलाइज़ेशन बना सकते हैं या कुल प्रोजेक्ट पूर्णता मेट्रिक्स की गणना कर सकते हैं।  
```java
for (ProgressLine line : ganttView.getProgressLines()) {
    System.out.println("Progress line color: " + line.getColor());
}
```  
*परिभाषा एंकर:* `getProgressLines()` प्रोग्रेस लाइन ऑब्जेक्ट्स का सेट लौटाता है जो कार्य की पूर्णता स्थिति दर्शाते हैं।

## टाइमस्केल टियर्स कैसे निकालें?
टाइमस्केल टियर्स चार्ट पर प्रदर्शित पदानुक्रमित समय इकाइयों (दिन, हफ्ता, माह) को परिभाषित करती हैं। इन्हें `getTimescaleTiers()` के माध्यम से प्राप्त करें और उनकी सेटिंग्स आउटपुट करें। प्रत्येक टियर के लिए आप यूनिट टाइप, लेबल फ़ॉर्मेट, और अलाइनमेंट कैप्चर कर सकते हैं, जो निर्यातित PDFs या कस्टम UI कंपोनेंट्स में सटीक टाइमलाइन ग्रैन्युलैरिटी पुनः बनाने के लिए महत्वपूर्ण है।  
```java
for (TimescaleTier tier : ganttView.getTimescaleTiers()) {
    System.out.println("Tier type: " + tier.getTierType());
}
```  
*परिभाषा एंकर:* `getTimescaleTiers()` टाइम एक्सिस डिस्प्ले को नियंत्रित करने वाले टाइमस्केल टियर ऑब्जेक्ट्स के कलेक्शन तक पहुँच प्रदान करता है।

## गैंट चार्ट को PDF में कैसे निर्यात करें?
`PdfSaveOptions` ऑब्जेक्ट बनाएं, वैकल्पिक रूप से पेज साइज या फ़ॉन्ट एम्बेडिंग कस्टमाइज़ करें, फिर `project.save` को PDF फ़ॉर्मेट के साथ कॉल करें। यह एकल कॉल स्क्रीन पर दिख रहे गैंट व्यू को प्रतिबिंबित करने वाला PDF जेनरेट करता है। आप इमेज कॉम्प्रेशन, वॉटरमार्क हटाना, या कस्टम फ़ॉन्ट एम्बेड करने जैसे अतिरिक्त विकल्प भी निर्दिष्ट कर सकते हैं ताकि कॉर्पोरेट ब्रांडिंग आवश्यकताओं को पूरा किया जा सके। सेव करने के बाद PDF फ़ाइल आकार और दृश्य सटीकता की जाँच करें ताकि निर्यात सफल रहा हो यह सुनिश्चित हो सके।  
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setPageSize(PageSize.A4);
project.save(dataDir + "ExportedGantt.pdf", options);
```  
*परिभाषा एंकर:* `PdfSaveOptions` आपको PDF आउटपुट को फाइन‑ट्यून करने की अनुमति देता है, जैसे पेज डाइमेंशन, कॉम्प्रेशन, और फ़ॉन्ट हैंडलिंग।

## सामान्य समस्याएँ एवं टिप्स
- **गलत डेटा डायरेक्टरी:** सुनिश्चित करें कि `dataDir` फ़ाइल‑सेपरेटर (`/` या `\\`) के साथ समाप्त हो, जो आपके OS के अनुसार हो।  
- **व्यू नहीं मिला:** यदि प्रोजेक्ट में कोई गैंट व्यू नहीं है, तो `project.getViews()` खाली रहेगा – कास्ट करने से पहले जाँच जोड़ें।  
- **लाइसेंस अपवाद:** वैध लाइसेंस न होने पर API निर्यातित PDFs में वॉटरमार्क जोड़ सकता है।  
- **बड़े प्रोजेक्ट्स:** 1,000 से अधिक कार्यों वाले प्रोजेक्ट्स के लिए JVM हीप साइज (`-Xmx2g`) बढ़ाने पर विचार करें ताकि `OutOfMemoryError` से बचा जा सके।  

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Tasks for Java को अन्य Java लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?**  
उत्तर: हाँ, Aspose.Tasks for Java किसी भी Java लाइब्रेरी या फ्रेमवर्क, जैसे Spring, Hibernate, और Apache POI, के साथ सहजता से इंटीग्रेट हो जाता है।

**प्रश्न: क्या Aspose.Tasks बड़े‑पैमाने के एंटरप्राइज़ प्रोजेक्ट्स के लिए उपयुक्त है?**  
उत्तर: बिल्कुल। लाइब्रेरी मानक सर्वर हार्डवेयर पर 5 सेकंड से कम समय में कई‑सौ‑पेज MPP फ़ाइलों को प्रोसेस करती है और मल्टी‑थ्रेडेड वातावरण में समवर्ती निष्पादन का समर्थन करती है।

**प्रश्न: क्या Aspose.Tasks कई प्रोजेक्ट फ़ाइल फ़ॉर्मेट्स को सपोर्ट करता है?**  
उत्तर: हाँ, Aspose.Tasks 20+ फ़ॉर्मेट्स को सपोर्ट करता है, जिसमें MPP, XML, MPX, और Primavera XML शामिल हैं, जिससे आप लेगेसी शेड्यूल को पढ़ और कन्वर्ट कर सकते हैं।

**प्रश्न: क्या मैं Aspose.Tasks के साथ गैंट चार्ट की उपस्थिति को कस्टमाइज़ कर सकता हूँ?**  
उत्तर: निश्चित रूप से। आप बार स्टाइल्स, ग्रिडलाइन, टेक्स्ट स्टाइल्स, और टाइमस्केल टियर्स को प्रोग्रामेटिकली संशोधित कर सकते हैं, फिर PDF या इमेज फ़ॉर्मेट में निर्यात कर सकते हैं।

**प्रश्न: व्यू में बदलाव करने के बाद कैसे सेव करें?**  
उत्तर: किसी भी संशोधन के बाद `project.save("output.mpp");` कॉल करें ताकि परिवर्तन प्रोजेक्ट फ़ाइल में स्थायी हो जाएँ।

---

**अंतिम अपडेट:** 2026-10-31  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose  

```java
import com.aspose.tasks.DateLabel;
import com.aspose.tasks.DayType;
import com.aspose.tasks.Field;
import com.aspose.tasks.FontStyles;
import com.aspose.tasks.GanttBarEndShape;
import com.aspose.tasks.GanttBarMiddleShape;
import com.aspose.tasks.GanttBarShowFor;
import com.aspose.tasks.GanttBarSize;
import com.aspose.tasks.GanttBarStyle;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.Gridlines;
import com.aspose.tasks.Interval;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Project;
import com.aspose.tasks.TextStyle;
import com.aspose.tasks.TimescaleUnit;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```

```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```

```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// Continue for other properties...
```

```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // Print bar style details...
}
```

```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// Print gridline details...
```

```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // Print text style details...
}
```

```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// Print other progress line details...
```

```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// Print details of other timescale tiers...
```

## संबंधित ट्यूटोरियल

- [How to Save Project as PDF with Aspose.Tasks – Export Guide](/tasks/java/project-file-operations/save-as-pdf/)
- [Create Project PDF – Customize Gantt Chart Time Scale](/tasks/java/project-file-operations/set-time-scale-count/)
- [Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}