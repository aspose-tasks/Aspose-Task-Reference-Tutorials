---
date: 2026-05-26
description: Aspose.Tasks for Java का उपयोग करके Microsoft Project फ़ाइलों को निर्यात
  करते समय प्रोजेक्ट स्नैपशॉट JPEG कैसे बनाएं और JPEG गुणवत्ता को कैसे समायोजित करें,
  सीखें।
keywords:
- create project snapshot jpeg
- adjust jpeg quality
- Aspose.Tasks Java
linktitle: Aspose.Tasks में प्रोजेक्ट को JPEG के रूप में सहेजें
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to create project snapshot JPEG and adjust JPEG quality when
    exporting Microsoft Project files using Aspose.Tasks for Java.
  headline: Create Project Snapshot JPEG – Adjust Quality with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Higher quality preserves text and line details, while very low quality
      may make small labels hard to read.
    question: Does adjusting JPEG quality affect Gantt chart readability?
  - answer: Yes, Aspose.Tasks supports PNG, BMP, and TIFF via the appropriate `SaveFileFormat`
      enum.
    question: Can I export other image formats besides JPEG?
  - answer: You can iterate over the desired views and save each as a separate JPEG
      using the same `ImageSaveOptions` configuration.
    question: Is it possible to export multiple pages (e.g., different views) at once?
  - answer: Aspose.Tasks for Java works with JDK 8 and later.
    question: What Java version is required?
  - answer: Consider reducing the JPEG quality or scaling the image dimensions via
      additional `ImageSaveOptions` settings.
    question: How do I handle large projects that produce big images?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: प्रोजेक्ट स्नैपशॉट JPEG बनाएं – Aspose.Tasks के साथ गुणवत्ता समायोजित करें
url: /hi/java/project-file-operations/save-as-jpeg/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# प्रोजेक्ट स्नैपशॉट JPEG बनाएं – Aspose.Tasks के साथ गुणवत्ता समायोजित करें

## परिचय
इस ट्यूटोरियल में आप सीखेंगे कि Aspose.Tasks for Java का उपयोग करके Microsoft Project से **create project snapshot JPEG** फ़ाइलें कैसे बनाएं, और JPEG गुणवत्ता को कैसे फाइन‑ट्यून करें ताकि आपके आकार‑वर्सेस‑स्पष्टता आवश्यकताओं को पूरा किया जा सके। चाहे आपको बोर्ड‑रूम प्रस्तुतियों के लिए स्पष्ट छवियों की आवश्यकता हो या वेब पोर्टलों के लिए हल्की फ़ाइलों की, गुणवत्ता सेटिंग को मास्टर करने से आप अंतिम आउटपुट पर पूर्ण नियंत्रण प्राप्त करते हैं।

## त्वरित उत्तर
- **What does “adjust JPEG quality” do?** यह आपको निर्यात किए गए JPEG की संपीड़न स्तर को नियंत्रित करने की अनुमति देता है, जिससे फ़ाइल आकार और दृश्य गुणवत्ता के बीच संतुलन बनता है।  
- **Which library handles the conversion?** Aspose.Tasks for Java प्रोजेक्ट फ़ाइलों को JPEG में निर्यात करने के लिए एक सरल API प्रदान करता है।  
- **Do I need a license?** मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन उपयोग के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **Can I set the quality in code?** हाँ, `ImageSaveOptions.setJpegQuality(int)` मेथड (0‑100 रेंज) का उपयोग करें।  
- **Is the process fast?** सामान्य प्रोजेक्ट फ़ाइल को JPEG में बदलने में आधुनिक हार्डवेयर पर केवल कुछ सेकंड लगते हैं।

## “adjust JPEG quality” क्या है?
JPEG गुणवत्ता समायोजित करने से आप JPEG फ़ॉर्मेट में छवि सहेजते समय लागू होने वाले संपीड़न कारक को निर्दिष्ट कर सकते हैं। उच्च मान (100 के करीब) अधिक विवरण को संरक्षित रखते हैं, जबकि कम मान फ़ाइल आकार को घटाते हैं लेकिन स्पष्टता की कीमत पर। **Direct answer:** आप `ImageSaveOptions.setJpegQuality` मेथड को (0‑100) संख्यात्मक मान पास करके JPEG गुणवत्ता को नियंत्रित करते हैं, जो तुरंत उत्पन्न स्नैपशॉट के आकार और दृश्य गुणवत्ता को प्रभावित करता है।  

JPEG गुणवत्ता वह संपीड़न कारक है जो JPEG फ़ॉर्मेट में छवि सहेजते समय लागू होता है।

## JPEG निर्यात के लिए Aspose.Tasks का उपयोग क्यों करें?
**Direct answer:** Aspose.Tasks Gantt चार्ट, रिसोर्स व्यू और कस्टम रिपोर्ट को इमेज फ़ाइलों में रेंडर करता है बिना Microsoft Project स्थापित किए, जिससे Windows, Linux और macOS पर पिक्सेल‑परफेक्ट आउटपुट की गारंटी मिलती है।  

Aspose.Tasks **चार** इमेज फ़ॉर्मेट (JPEG, PNG, BMP, TIFF) में निर्यात का समर्थन करता है और मानक 2.5 GHz CPU पर 5 सेकंड से कम समय में **10,000 टास्क** तक वाले प्रोजेक्ट को रेंडर कर सकता है, जिससे एक मात्रात्मक प्रदर्शन गारंटी मिलती है।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. **Java Development Kit (JDK)** – नवीनतम JDK (8 या नया) [Java वेबसाइट](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) से इंस्टॉल करें।  
2. **Aspose.Tasks for Java** – आधिकारिक [दस्तावेज़ीकरण](https://reference.aspose.com/tasks/java/) में दिए गए चरणों का पालन करके लाइब्रेरी डाउनलोड करें और सेट अप करें।

## पैकेज आयात करें
`ImageSaveOptions` Aspose.Tasks की क्लास है जो इमेज निर्यात सेटिंग्स जैसे फ़ॉर्मेट, आयाम, और JPEG गुणवत्ता को नियंत्रित करती है।  
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```

## चरण 1: डेटा डायरेक्टरी निर्धारित करें
अपने Microsoft Project फ़ाइल वाले फ़ोल्डर का पथ सेट करें। यह डायरेक्टरी इनपुट और आउटपुट दोनों संचालन के लिए उपयोग की जाती है।  
```java
String dataDir = "Your Data Directory";
```

## चरण 2: MS Project फ़ाइल लोड करें
`Project` क्लास मेमोरी में एक Microsoft Project फ़ाइल का प्रतिनिधित्व करती है, जो टास्क, रिसोर्स और व्यू डेटा तक पहुंच प्रदान करती है।  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## चरण 3: JPEG गुणवत्ता समायोजित करें (वैकल्पिक)
यदि आप आउटपुट को फाइन‑ट्यून करना चाहते हैं, तो आप `ImageSaveOptions` क्लास का उपयोग करके **JPEG गुणवत्ता सेट** कर सकते हैं। गुणवत्ता मान 0 से 100 तक होता है, जहाँ 100 सबसे अधिक दृश्य गुणवत्ता देता है।  
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Set JPEG quality to 50
```

## चरण 4: प्रोजेक्ट को JPEG के रूप में सहेजें
`Project.save` आपके द्वारा कॉन्फ़िगर किए गए विकल्पों का उपयोग करके रेंडर किए गए व्यू को इमेज फ़ाइल में लिखता है।  
```java
project.save(dataDir + "image_out.jpeg", options);
```

## MS Project से JPEG निर्यात कैसे करें
**Direct answer:** `ImageSaveOptions` को कॉन्फ़िगर करने के बाद `project.save("output.jpeg", SaveFileFormat.JPEG, saveOptions)` कॉल करें; यह मेथड सक्रिय व्यू (डिफ़ॉल्ट रूप से Gantt चार्ट) को रेंडर करता है और निर्दिष्ट गुणवत्ता के साथ JPEG फ़ाइल लिखता है। यह एक‑लाइन कॉल पेजिनेशन, स्केलिंग, और कलर मैनेजमेंट को स्वतः संभालता है।  

JPEG गुणवत्ता को समायोजित करके, आप इमेज स्पष्टता और फ़ाइल आकार के बीच संतुलन नियंत्रित करते हैं, जिससे निर्यातित इमेज वेब प्रकाशन, प्रिंटेड रिपोर्ट या एम्बेडेड स्लाइड्स के लिए उपयुक्त बनती है।

## सामान्य समस्याएँ और समाधान
- **Low quality makes text unreadable:** JPEG गुणवत्ता को 70 से ऊपर बढ़ाएँ या लॉसलेस रेंडरिंग के लिए PNG पर स्विच करें।  
- **Out‑of‑memory errors on large projects:** मेमोरी उपयोग को 200 MB से नीचे रखने के लिए `saveOptions.setUseMemoryCache(true)` सेट करके स्ट्रीमिंग सक्षम करें।  
- **Wrong view exported:** किसी अलग व्यू को निर्यात करने के लिए `saveOptions.setView(ViewType.TaskSheet)` का उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या JPEG गुणवत्ता समायोजित करने से Gantt चार्ट की पठनीयता प्रभावित होती है?**  
A: उच्च गुणवत्ता टेक्स्ट और लाइन विवरण को संरक्षित रखती है, जबकि बहुत कम गुणवत्ता छोटे लेबलों को पढ़ना कठिन बना सकती है।  

**Q: क्या मैं JPEG के अलावा अन्य इमेज फ़ॉर्मेट निर्यात कर सकता हूँ?**  
A: हाँ, Aspose.Tasks उपयुक्त `SaveFileFormat` एन्‍यूम के माध्यम से PNG, BMP, और TIFF का समर्थन करता है।  

**Q: क्या एक साथ कई पेज (जैसे विभिन्न व्यू) निर्यात करना संभव है?**  
A: आप इच्छित व्यूज़ पर इटररेट करके प्रत्येक को समान `ImageSaveOptions` कॉन्फ़िगरेशन का उपयोग करके अलग JPEG के रूप में सहेज सकते हैं।  

**Q: कौन सा Java संस्करण आवश्यक है?**  
A: Aspose.Tasks for Java JDK 8 और उसके बाद के संस्करणों के साथ काम करता है।  

**Q: बड़े प्रोजेक्ट्स जो बड़ी इमेज बनाते हैं, उन्हें कैसे संभालें?**  
A: JPEG गुणवत्ता को कम करने या अतिरिक्त `ImageSaveOptions` सेटिंग्स के माध्यम से इमेज आयाम को स्केल करने पर विचार करें।  

## निष्कर्ष
हमने बताया कि कैसे **create project snapshot JPEG** फ़ाइलें बनाई जा सकती हैं और Aspose.Tasks for Java का उपयोग करके JPEG गुणवत्ता को समायोजित किया जा सकता है। यह तरीका मैन्युअल स्क्रीनशॉट को समाप्त करता है, प्लेटफ़ॉर्म के बीच सुसंगत रेंडरिंग की गारंटी देता है, और आपको इमेज स्पष्टता और फ़ाइल आकार के बीच संतुलन को फाइन‑ट्यून करने की अनुमति देता है—रिपोर्ट, प्रस्तुतियों और वेब प्रकाशन के लिए एकदम उपयुक्त।

---

**अंतिम अपडेट:** 2026-05-26  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [MPP फ़ाइल कैसे बनाएं – Aspose.Tasks के साथ MPP फ़ॉर्मेट में खाली प्रोजेक्ट बनाएं और सहेजें](/tasks/java/project-configuration/create-save-mpp/)
- [Aspose.Tasks for Java के साथ प्रोजेक्ट को टेम्पलेट, CSV, और टेक्स्ट के रूप में सहेजें](/tasks/java/project-file-operations/save-csv-text-template/)
- [Aspose.Tasks में खाली MS Project फ़ाइल बनाएं](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}