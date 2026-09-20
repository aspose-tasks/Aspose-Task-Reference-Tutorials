---
date: 2026-09-20
description: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट टास्क डिपेंडेंसीज़ को कैसे
  प्रबंधित करें, जानें। यह गाइड आपको दिखाता है कि कैसे predecessor links जोड़ें, task
  names प्रिंट करें, और task dependencies को प्रभावी ढंग से सेट करें।
keywords:
- project task dependencies
- how to add predecessor
- java project management
- manage task dependencies
- print task names
lastmod: 2026-09-20
linktitle: Aspose.Tasks for Java के माध्यम से प्रोजेक्ट टास्क डिपेंडेंसीज़ को प्रबंधित
  करें
og_description: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट टास्क डिपेंडेंसीज़ को
  कैसे प्रबंधित करें, जानें। यह गाइड आपको दिखाता है कि कैसे predecessor links जोड़ें,
  task names प्रिंट करें, और task dependencies को प्रभावी ढंग से सेट करें।
og_image_alt: Guide showing how to manage project task dependencies with Aspose.Tasks
  Java API
og_title: Aspose.Tasks for Java के माध्यम से प्रोजेक्ट टास्क डिपेंडेंसीज़ को प्रबंधित
  करें
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  headline: Manage project task dependencies via Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  name: Manage project task dependencies via Aspose.Tasks for Java
  steps:
  - name: initialize the project object
    text: Create a new instance of the `Project` class and provide the path to your
      project file (e.g., `"project.mpp"`).
  - name: access task links
    text: Retrieve all task links from the project using the `getTaskLinks()` method.
  - name: iterate through task links
    text: Use a loop to iterate through each task link in the collection and print
      information about the predecessor and successor tasks.
  - name: add a new predecessor link (optional)
    text: If you need to create a new dependency, instantiate a `TaskLink`, set its
      `PredecessorTaskUid`, `SuccessorTaskUid`, and `LinkType`, then add it to the
      project's link collection. Repeat these steps as needed for your specific project
      requirements.
  type: HowTo
- questions:
  - answer: Yes, simply add the Aspose.Tasks JAR to your classpath or Maven/Gradle
      dependencies.
    question: Can I use Aspose.Tasks for Java in my existing Java project?
  - answer: Yes, it supports MPP, XML, CSV, and more than 30 additional formats.
    question: Is Aspose.Tasks compatible with different project file formats?
  - answer: Obtain a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community support and discussions.
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, download a free trial from the [Aspose free trial page](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project task dependencies
- Aspose.Tasks
- Java project management
title: Aspose.Tasks for Java के माध्यम से प्रोजेक्ट टास्क डिपेंडेंसीज़ को प्रबंधित
  करें
url: /hi/java/task-links/predecessor-successor-tasks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java के माध्यम से प्रोजेक्ट टास्क डिपेंडेंसीज़ प्रबंधित करें

## परिचय
प्रोजेक्ट टास्क डिपेंडेंसीज़ किसी भी वास्तविक शेड्यूल की रीढ़ हैं, जिससे आप यह मॉडल कर सकते हैं कि कौन सा काम दूसरे के शुरू होने से पहले समाप्त होना चाहिए। इस ट्यूटोरियल में आप Aspose.Tasks for Java के साथ **project task dependencies** को कैसे प्रबंधित करें, जिसमें प्रीडेसेसर लिंक जोड़ना, टास्क नाम प्रिंट करना, और प्रोग्रामेटिकली टास्क डिपेंडेंसीज़ सेट करना शामिल है।

## त्वरित उत्तर
- **पहला कदम क्या है?** अपने MPP फ़ाइल को एक `Project` ऑब्जेक्ट में लोड करें।  
- **प्रीडेसेसर कैसे जोड़ें?** एक `TaskLink` बनाएं और उसके `PredecessorTaskUid` और `SuccessorTaskUid` सेट करें।  
- **क्या आप सभी लिंक सूचीबद्ध कर सकते हैं?** `project.getTaskLinks()` का उपयोग करें और कलेक्शन पर इटररेट करें।  
- **क्या मुझे लाइसेंस चाहिए?** मूल्यांकन के लिए एक टेम्पररी लाइसेंस काम करता है; प्रोडक्शन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण समर्थित है?** Java 8 या उससे ऊपर।

## प्रोजेक्ट टास्क डिपेंडेंसीज़ क्या हैं?
प्रोजेक्ट टास्क डिपेंडेंसीज़ दो टास्क के बीच तार्किक संबंध को परिभाषित करती हैं, जैसे Finish‑to‑Start या Start‑to‑Start, और यह निर्धारित करती हैं कि काम किस क्रम में किया जाना चाहिए। इन लिंक को स्थापित करके, शेड्यूल स्वचालित रूप से वास्तविक‑विश्व प्रतिबंधों का सम्मान करता है, ओवरलैपिंग गतिविधियों को रोकता है, और सुनिश्चित करता है कि डाउनस्ट्रीम टास्क केवल तब शुरू हों जब उनकी पूर्वापेक्षाएँ पूरी हो गई हों।

## Aspose.Tasks for Java का उपयोग क्यों करें?
Aspose.Tasks for Java तीस से अधिक प्रोजेक्ट फ़ाइल फ़ॉर्मेट्स को सपोर्ट करता है, जिसमें नवीनतम Microsoft Project संस्करण शामिल हैं, और दो गीगाबाइट तक की फ़ाइलों को पूरी दस्तावेज़ को मेमोरी में लोड किए बिना प्रोसेस कर सकता है। यह हाई‑परफ़ॉर्मेंस क्षमता आपको बड़े शेड्यूल को मैनीपुलेट करने, रिपोर्ट जनरेट करने, और बल्क अपडेट्स को कुशलतापूर्वक करने देती है, जिससे यह एंटरप्राइज़‑स्केल प्रोजेक्ट मैनेजमेंट सॉल्यूशन्स के लिए आदर्श बनता है।

## पूर्वापेक्षाएँ
- Java Development Environment: Java 8 या उससे नई संस्करण आपके मशीन पर इंस्टॉल हो।  
- Aspose.Tasks for Java Library: Aspose.Tasks लाइब्रेरी को [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) से डाउनलोड और इंस्टॉल करें।  
- Integrated Development Environment (IDE): Eclipse, IntelliJ IDEA, या कोई भी Java‑compatible IDE जो आप पसंद करते हैं।

## पैकेज इम्पोर्ट करें
आपको कोर क्लासेज़ इम्पोर्ट करने की आवश्यकता है जो प्रोजेक्ट मैनिपुलेशन को सक्षम बनाती हैं।

`Project` क्लास Microsoft Project फ़ाइलों को लोड और सेव करने के लिए एंट्री पॉइंट है।  
`TaskLink` क्लास दो टास्क के बीच डिपेंडेंसी को दर्शाती है।

## दो टास्क के बीच प्रीडेसेसर लिंक कैसे जोड़ें?
एक `TaskLink` इंस्टेंस बनाएं, प्रीडेसेसर टास्क का UID और सक्सेसर टास्क का UID असाइन करें, उपयुक्त `TaskLinkType` जैसे Finish‑to‑Start चुनें, और फिर लिंक को प्रोजेक्ट की टास्क लिंक कलेक्शन में जोड़ें। एक बार जोड़ने के बाद, शेड्यूल तुरंत नई डिपेंडेंसी रिलेशनशिप को दर्शाता है।

### चरण 1: प्रोजेक्ट ऑब्जेक्ट को इनिशियलाइज़ करें
`Project` क्लास का नया इंस्टेंस बनाएं और अपने प्रोजेक्ट फ़ाइल का पाथ प्रदान करें (उदा., `"project.mpp"`).

```java
import com.aspose.tasks.*;
```

### चरण 2: टास्क लिंक एक्सेस करें
`getTaskLinks()` मेथड का उपयोग करके प्रोजेक्ट से सभी टास्क लिंक प्राप्त करें।

```java
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.mpp");
```

### चरण 3: टास्क लिंक के माध्यम से इटररेट करें
कलेक्शन में प्रत्येक टास्क लिंक के माध्यम से इटररेट करने के लिए लूप का उपयोग करें और प्रीडेसेसर तथा सक्सेसर टास्क की जानकारी प्रिंट करें।

```java
TaskLinkCollection allinks = project.getTaskLinks();
```

### चरण 4: नया प्रीडेसेसर लिंक जोड़ें (वैकल्पिक)
यदि आपको नई डिपेंडेंसी बनानी है, तो एक `TaskLink` इंस्टैंसिएट करें, उसके `PredecessorTaskUid`, `SuccessorTaskUid`, और `LinkType` सेट करें, फिर इसे प्रोजेक्ट की लिंक कलेक्शन में जोड़ें।

```java
for (TaskLink tsklnk : allinks) {
    System.out.println("Predecessor " + tsklnk.getPredTask().get(Tsk.NAME));
    System.out.println("Successor " + tsklnk.getSuccTask().get(Tsk.NAME));
}
```

अपने विशिष्ट प्रोजेक्ट आवश्यकताओं के अनुसार इन चरणों को दोहराएँ।

## सामान्य समस्याएँ और समाधान
- **लिंक जोड़ने के बाद प्रीडेसेसर गायब** – सुनिश्चित करें कि आप `project.updateTaskLinks()` कॉल करें (या सेव करके रीलोड करें) ताकि आंतरिक ग्राफ रिफ्रेश हो।  
- **बड़ी फ़ाइलों पर प्रदर्शन धीमा** – बल्क ऑपरेशन्स से पहले `project.setReadOnly(true)` का उपयोग करें ताकि मेमोरी ओवरहेड कम हो।  
- **गलत लिंक प्रकार** – सत्यापित करें कि आप सही `TaskLinkType` एन्‍म वैल्यू (जैसे `FinishToStart`) का उपयोग कर रहे हैं ताकि आपका शेड्यूल लॉजिक मेल खाए।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Tasks for Java को अपने मौजूदा Java प्रोजेक्ट में उपयोग कर सकता हूँ?**  
उत्तर: हाँ, बस Aspose.Tasks JAR को अपने क्लासपाथ या Maven/Gradle डिपेंडेंसीज़ में जोड़ें।

**प्रश्न: क्या Aspose.Tasks विभिन्न प्रोजेक्ट फ़ाइल फ़ॉर्मेट्स के साथ संगत है?**  
उत्तर: हाँ, यह MPP, XML, CSV, और 30 से अधिक अतिरिक्त फ़ॉर्मेट्स को सपोर्ट करता है।

**प्रश्न: मैं Aspose.Tasks के लिए टेम्पररी लाइसेंस कैसे प्राप्त कर सकता हूँ?**  
उत्तर: टेम्पररी लाइसेंस [temporary license page](https://purchase.aspose.com/temporary-license/) से प्राप्त करें।

**प्रश्न: मैं Aspose.Tasks के लिए अतिरिक्त समर्थन कहाँ पा सकता हूँ?**  
उत्तर: समुदाय समर्थन और चर्चा के लिए [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर जाएँ।

**प्रश्न: क्या मैं Aspose.Tasks for Java का फ्री ट्रायल डाउनलोड कर सकता हूँ?**  
उत्तर: हाँ, [Aspose free trial page](https://releases.aspose.com/) से फ्री ट्रायल डाउनलोड करें।

---

**अंतिम अपडेट:** 2026-09-20  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Tasks में प्रोजेक्ट मैनेजमेंट टास्क डिपेंडेंसीज़ बनाएं](/tasks/java/task-links/create-task-link/)
- [Aspose.Tasks में प्रोजेक्ट स्टार्ट डेट सेट करें और पैरेंट व चाइल्ड टास्क मैनेज करें](/tasks/java/task-properties/parent-child-tasks/)
- [Aspose.Tasks for Java के साथ टास्क प्रायोरिटी पढ़ें और सेट करें](/tasks/java/task-properties/handle-priorities/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}