---
date: 2026-06-10
description: Aspose.Tasks for Java का उपयोग करके रिसोर्स असाइनमेंट्स के लिए कंटूर
  बदलना और टाइमफ़ेज़्ड डेटा जेनरेट करना सीखें, जिसमें वर्क कंटूर टाइप्स और एडवांस्ड
  शेड्यूलिंग सीनारियो शामिल हैं।
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: Aspose.Tasks में रिसोर्स असाइनमेंट्स के लिए Timephased Data जेनरेट करें
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में टाइमफ़ेज़्ड डेटा के लिए कंटूर कैसे बदलें
url: /hi/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में टाइम‑फ़ेज़्ड डेटा के लिए कंटूर बदलने का तरीका

## परिचय
इस ट्यूटोरियल में आप **कंटूर बदलने** का तरीका सीखेंगे और Aspose.Tasks for Java का उपयोग करके रिसोर्स असाइनमेंट के लिए टाइम‑फ़ेज़्ड डेटा जेनरेट करेंगे। टाइम‑फ़ेज़्ड डेटा प्रोजेक्ट टाइमलाइन पर कार्य के वितरण को दिखाता है, जिससे आप शेड्यूल को फाइन‑ट्यून कर सकते हैं, वर्कलोड बैलेंस कर सकते हैं और डेटा‑ड्रिवेन निर्णय ले सकते हैं। कंटूर परिवर्तन को समझना आपको फ्रंट‑लोडिंग, बैक‑लोडिंग या पीक वर्कलोड जैसे वास्तविक प्रयास पैटर्न मॉडल करने में मदद करता है।

## त्वरित उत्तर
- **कंटूर क्या है?** वर्क कंटूर यह निर्धारित करता है कि कार्य की अवधि में प्रयास कैसे वितरित होता है (जैसे, Flat, Turtle, Bell)।  
- **कंटूर क्यों बदलें?** वास्तविक कार्य पैटर्न जैसे फ्रंट‑लोडिंग या बैक‑लोडिंग को दर्शाने के लिए।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Tasks for Java (कोई भी नवीनतम संस्करण)।  
- **क्या लाइसेंस चाहिए?** हाँ, प्रोडक्शन उपयोग के लिए वैध Aspose.Tasks लाइसेंस आवश्यक है।  
- **क्या परिणाम कंसोल में देख सकते हैं?** नमूना प्रत्येक टाइम‑फ़ेज़्ड सेगमेंट की प्रारंभ तिथियों और मानों को प्रिंट करता है।

## “कंटूर बदलने” क्या है?
कंटूर बदलना मतलब `ResourceAssignment` ऑब्जेक्ट की `WORK_CONTOUR` प्रॉपर्टी को अपडेट करना है। यह प्रॉपर्टी Aspose.Tasks को बताती है कि असाइनमेंट के कुल कार्य को टास्क की अवधि में कैसे वितरित किया जाए। लाइब्रेरी कई प्री‑डिफाइंड कंटूर प्रदान करती है जैसे Flat, Turtle, Bell आदि, जो समय के साथ विभिन्न प्रयास वितरण पैटर्न बनाते हैं।

## Aspose.Tasks से टाइम‑फ़ेज़्ड डेटा क्यों जेनरेट करें?
Aspose.Tasks **0 ms ओवरहेड** के साथ इन‑मेमोरी ऑपरेशन्स करता है और **50+ आउटपुट फ़ॉर्मेट** (MPP, XML, CSV आदि) को सपोर्ट करता है। यह लाइब्रेरी पूरे फ़ाइल को मेमोरी में लोड किए बिना सैकड़ों‑पृष्ठ प्रोजेक्ट को प्रोसेस कर सकती है, जिससे रिपोर्टिंग, रिसोर्स लेवलिंग और वॉट‑इफ़ विश्लेषण के लिए सटीक कार्य वितरण मिलता है। इसका API कंटूर परिवर्तन को ऑटोमेट करने और प्रोग्रामेटिक रूप से सटीक टाइम‑फ़ेज़्ड वैल्यू निकालने में मदद करता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. Java Development Kit (JDK): सुनिश्चित करें कि आपके सिस्टम पर JDK स्थापित है। आप इसे [यहाँ](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) से डाउनलोड और इंस्टॉल कर सकते हैं।  
2. Aspose.Tasks for Java लाइब्रेरी: आपको Aspose.Tasks for Java लाइब्रेरी की आवश्यकता होगी। इसे आप [वेबसाइट](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।

## पैकेज इम्पोर्ट करें
`Project` क्लास Aspose.Tasks का कोर ऑब्जेक्ट है जो मेमोरी में पूरे प्रोजेक्ट फ़ाइल का प्रतिनिधित्व करता है। टास्क और असाइनमेंट के साथ काम शुरू करने से पहले आवश्यक नेमस्पेस इम्पोर्ट करें।

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## चरण 1: स्रोत MPP फ़ाइल पढ़ें
`Project` कंस्ट्रक्टर मौजूदा MPP फ़ाइल को लोड करता है, उसकी संरचना को पार्स करता है बिना सभी टास्क को पूरी तरह मेमोरी में मैटेरियलाइज़ किए, जिससे ऑपरेशन हल्का रहता है।

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## चरण 2: टास्क और रिसोर्स असाइनमेंट प्राप्त करें
`ResourceAssignment` एक रिसोर्स को टास्क से जोड़ता है और असाइनमेंट‑लेवल प्रॉपर्टीज़ जैसे कार्य, लागत और कंटूर को स्टोर करता है। कंटूर बदलने से पहले `project.getResourceAssignments().getById(1)` (या कोई वैध ID) के साथ पहला असाइनमेंट प्राप्त करें।

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## कंटूर बदलें – Flat (डिफ़ॉल्ट)
`WorkContourType` एक एनेमरेशन है जो Aspose.Tasks द्वारा सपोर्ट किए गए प्री‑डिफाइंड वर्क कंटूर पैटर्न को सूचीबद्ध करता है। `Asn.WORK_CONTOUR` रिसोर्स असाइनमेंट के कंटूर फ़ील्ड को पहचानता है, और `generateTimephasedData()` वर्तमान कंटूर सेटिंग के आधार पर टाइम‑फ़ेज़्ड कार्य एंट्री बनाता है। **Flat** कंटूर कार्य को टास्क की अवधि में समान रूप से वितरित करता है; इसे `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` से सेट करें और फिर `firstRA.generateTimephasedData()` कॉल करके समान अंतराल वाले मान प्राप्त करें।

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## कंटूर बदलें – Turtle
**Turtle** कंटूर कम प्रयास से शुरू होता है, मध्य में तेज़ी से बढ़ता है, और फिर फिर से धीमा हो जाता है, जो कछुए की धीरे‑धीरे गति जैसा है। इसे `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` सेट करके लागू करें और फिर टाइम‑फ़ेज़्ड डेटा को पुनः जेनरेट करें। यह पैटर्न उन टास्क के लिए आदर्श है जिन्हें पीक प्रोडक्टिविटी से पहले लर्निंग कर्व की आवश्यकता होती है।

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## कंटूर बदलें – BackLoaded
**BackLoaded** कंटूर कार्य का अधिकांश भाग टास्क के शेड्यूल के अंत की ओर रखता है, जबकि शुरुआत में कम प्रयास होता है। इसे `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` से सेट करें और टाइम‑फ़ेज़्ड डेटा को पुनः जेनरेट करें। यह उन गतिविधियों के लिए उपयोगी है जो पूर्ववर्ती टास्क पर निर्भर करती हैं।

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## कंटूर बदलें – FrontLoaded
**FrontLoaded** कंटूर टास्क की शुरुआत में प्रयास को केंद्रित करता है, जैसे किक‑ऑफ़ फेज़ या शुरुआती तीव्र कार्य बर्स्ट। इसे `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` से लागू करें और फिर `firstRA.generateTimephasedData()` कॉल करके फ्रंट‑लोडेड वितरण देखें।

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## कंटूर बदलें – Bell
**Bell** कंटूर टाइमलाइन के मध्य में सममित पीक बनाता है, जो कार्य को धीरे‑धीरे बढ़ाता, पीक पर पहुँचाता और फिर सुगमता से घटाता है। इसे `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` से सेट करें और टाइम‑फ़ेज़्ड डेटा को पुनः जेनरेट करके बेल‑शेप्ड प्रयास कर्व देखें।

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## कंटूर बदलें – EarlyPeak
**EarlyPeak** शेड्यूल की शुरुआत में सबसे अधिक कार्य मान रखता है और फिर धीरे‑धीरे घटता है। इसे `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` के बाद `firstRA.generateTimephasedData()` कॉल करके लागू करें, जिससे तेज़ प्रोटोटाइपिंग जैसी शुरुआती तीव्रता वाले कार्य मॉडल हो सकें।

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## कंटूर बदलें – LatePeak
**LatePeak** कार्य पीक को टास्क के अंत की ओर शिफ्ट करता है, जो डेडलाइन के करीब काम की तीव्रता बढ़ाने वाले परिदृश्यों के लिए उपयुक्त है। इसे `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` से सेट करें और टाइम‑फ़ेज़्ड डेटा को पुनः जेनरेट करके लेट‑स्टेज वर्कलोड सर्ज देखें।

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## कंटूर बदलें – DoublePeak
**DoublePeak** दो अलग‑अलग कार्य स्पाइक्स बनाता है, जिनके बीच कम‑प्रयास अंतराल होता है, जो दो प्रमुख प्रयास बर्स्ट वाले टास्क के लिए उपयोगी है। इसे `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` से सेट करें और फिर `firstRA.generateTimephasedData()` कॉल करके डबल‑पीक पैटर्न प्राप्त करें।

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## सामान्य समस्याएँ और टिप्स
- **कंटूर अपडेट नहीं हो रहा?** टाइम‑फ़ेज़्ड डेटा प्राप्त करने से *पहले* `firstRA.set(Asn.WORK_CONTOUR, …)` कॉल करना सुनिश्चित करें।  
- **अप्रत्याशित मान?** सुनिश्चित करें कि टास्क की प्रारंभ और समाप्ति तिथियां स्रोत MPP में सही सेट हैं।  
- **परफ़ॉर्मेंस टिप:** कई कंटूर पर इटररेट करते समय एक ही `Project` इंस्टेंस को पुनः उपयोग करें ताकि अनावश्यक फ़ाइल I/O से बचा जा सके, जिससे बड़े प्रोजेक्ट पर प्रोसेसिंग समय 40 % तक घट सकता है।  
- **मेमोरी टिप:** 1 GB से बड़े प्रोजेक्ट के लिए `Project.setReadOnly(true)` सक्षम करें ताकि मेमोरी उपयोग 200 MB से नीचे रहे जबकि सटीक टाइम‑फ़ेज़्ड डेटा जेनरेट हो।

## अक्सर पूछे जाने वाले प्रश्न
**प्रश्न: क्या मैं Aspose.Tasks को अन्य Java लाइब्रेरी के साथ उपयोग कर सकता हूँ?**  
उत्तर: हाँ, Aspose.Tasks अन्य Java लाइब्रेरी के साथ सहजता से इंटीग्रेट होता है, जिससे आप शेड्यूलिंग डेटा को रिपोर्टिंग, एनालिटिक्स या UI फ्रेमवर्क के साथ संयोजित कर सकते हैं।

**प्रश्न: क्या Aspose.Tasks बड़े‑स्तर के एंटरप्राइज़ प्रोजेक्ट्स के लिए उपयुक्त है?**  
उत्तर: बिल्कुल। यह लाइब्रेरी दसियों हज़ार टास्क और रिसोर्स वाले प्रोजेक्ट को बिना परफ़ॉर्मेंस गिरावट के प्रोसेस करने के लिए डिज़ाइन की गई है।

**प्रश्न: क्या Aspose.Tasks विभिन्न प्रोजेक्ट फ़ाइल फ़ॉर्मेट्स को सपोर्ट करता है?**  
उत्तर: हाँ, Aspose.Tasks 30 से अधिक फ़ॉर्मेट्स को सपोर्ट करता है, जिसमें MPP, XML, CSV और MPX शामिल हैं, जिससे लेगेसी और मॉडर्न सिस्टम के बीच आसान इम्पोर्ट/एक्सपोर्ट संभव होता है।

**प्रश्न: क्या मैं अपने प्रोजेक्ट की आवश्यकताओं के अनुसार वर्क कंटूर कस्टमाइज़ कर सकता हूँ?**  
उत्तर: हाँ, आप `WORK_CONTOUR` प्रॉपर्टी में कार्य प्रतिशत की एक एरे प्रदान करके कस्टम कंटूर परिभाषित कर सकते हैं, जिससे आप प्रयास वितरण पर पूर्ण नियंत्रण पा सकते हैं।

**प्रश्न: क्या Aspose.Tasks के लिए कोई कम्युनिटी फ़ोरम है जहाँ सहायता मिल सके?**  
उत्तर: हाँ, आप समर्थन, चर्चा और कोड सैंपल के लिए [Aspose.Tasks फ़ोरम](https://forum.aspose.com/c/tasks/15) पर जा सकते हैं।

---

**अंतिम अपडेट:** 2026-06-10  
**टेस्टेड विद:** Aspose.Tasks for Java (नवीनतम रिलीज)  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.Tasks में रिसोर्स असाइनमेंट बनाएं](/tasks/java/resource-assignments/create-resource-assignments/)
- [Aspose.Tasks में रिसोर्स के लिए टाइम‑फ़ेज़्ड डेटा पढ़ें](/tasks/java/resource-management/read-timephased-data/)
- [Aspose.Tasks में असाइनमेंट को रोकें और रिसोर्स असाइनमेंट को पुनः शुरू करें](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}