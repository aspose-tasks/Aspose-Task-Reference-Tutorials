---
date: 2026-08-29
description: Aspose.Tasks for Java का उपयोग करके baseline डेटा पढ़ने और टास्क शेड्यूल
  करने का तरीका सीखें, ताकि आप नियोजित और वास्तविक प्रगति की प्रभावी तुलना कर सकें।
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: Aspose.Tasks में Baseline टास्क शेड्यूलिंग
og_description: Aspose.Tasks for Java का उपयोग करके baseline डेटा पढ़ने और टास्क शेड्यूल
  करने के बारे में जानें, जिससे नियोजित और वास्तविक प्रगति की सटीक तुलना संभव हो सके।
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: Aspose.Tasks के साथ baseline पढ़ने और टास्क शेड्यूल करने का तरीका
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: Aspose.Tasks के साथ baseline पढ़ने और टास्क शेड्यूल करने का तरीका
url: /hi/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ बेसलाइन पढ़ने और कार्यों को शेड्यूल करने का तरीका

इस गाइड में आप **बेसलाइन पढ़ने का तरीका** जानकारी और Aspose.Tasks for Java का उपयोग करके प्रोग्रामेटिक रूप से कार्यों को शेड्यूल करने का तरीका जानेंगे। ट्यूटोरियल के अंत तक, आप मूल प्रोजेक्ट प्लान को कैप्चर कर पाएँगे, इसे वास्तविक प्रगति से तुलना कर पाएँगे, और वैरिएंस रिपोर्ट जेनरेट कर पाएँगे—बिना Microsoft Project इंस्टॉल किए।

## प्रोजेक्ट मैनेजमेंट बेसलाइन का परिचय

प्रभावी प्रोजेक्ट मैनेजमेंट में **project management baseline** को प्रबंधित करना एक मुख्य आधार है। यह आपको मूल योजना को कैप्चर करने और बाद में **planned vs actual progress** की तुलना करने की अनुमति देता है ताकि आप वैरिएंस को जल्दी पहचान सकें। इस ट्यूटोरियल में, हम Aspose.Tasks for Java का उपयोग करके टास्क बेसलाइन को शेड्यूल करने की प्रक्रिया देखेंगे, जिससे आप **manage project baselines** को आत्मविश्वास के साथ कर सकेंगे और अपने प्रोजेक्ट को ट्रैक पर रख सकेंगे।

## त्वरित उत्तर
- **What does a project management baseline represent?**  
  यह प्रोजेक्ट की शुरुआत में स्वीकृत शेड्यूल, लागत और स्कोप को रिकॉर्ड करता है, जो वैरिएंस विश्लेषण के लिए एक संदर्भ प्रदान करता है।  
- **Which library handles baseline scheduling in Java?**  
  Aspose.Tasks for Java एक शुद्ध‑Java API प्रदान करता है जो 45+ इनपुट और आउटपुट फ़ॉर्मेट्स को सपोर्ट करता है और 100 000 तक टास्क वाले प्रोजेक्ट्स को संभाल सकता है।  
- **Do I need a license to run the code?**  
  परीक्षण के लिए एक फ्री ट्रायल काम करता है; प्रोडक्शन उपयोग के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **What are the main prerequisites?**  
  Java Development Kit (JDK) 11+ और Aspose.Tasks for Java लाइब्रेरी।  
- **Can I view baseline dates after setting them?**  
  हाँ—`TaskBaseline` ऑब्जेक्ट का उपयोग करके आप स्टार्ट, फिनिश और ड्यूरेशन मान पढ़ सकते हैं।

## प्रोजेक्ट मैनेजमेंट बेसलाइन क्या है?

एक प्रोजेक्ट मैनेजमेंट बेसलाइन निष्पादन की शुरुआत में स्वीकृत शेड्यूल, बजट और स्कोप को रिकॉर्ड करती है। यह प्रोजेक्ट लाइफ़साइकल के दौरान प्रदर्शन मापने और विचलनों की पहचान करने के लिए एक संदर्भ बिंदु के रूप में कार्य करती है। इसमें नियोजित प्रारंभ और समाप्ति तिथियाँ, कुल लागत, और स्कोप विवरण शामिल होते हैं, जो भविष्य की तुलना के लिए एक व्यापक स्नैपशॉट प्रदान करती हैं।

## बेसलाइन शेड्यूलिंग के लिए Aspose.Tasks क्यों उपयोग करें?

Aspose.Tasks एक शुद्ध‑Java API प्रदान करता है जो Microsoft Project इंस्टॉल किए बिना काम करता है। यह **45+ इनपुट और आउटपुट फ़ॉर्मेट्स** को सपोर्ट करता है, मेमोरी‑इफ़िशिएंट मोड में **100 000 तक टास्क** वाले प्रोजेक्ट्स को प्रोसेस कर सकता है, और बेसलाइन डेटा को पढ़ने और लिखने के लिए बिल्ट‑इन मेथड्स प्रदान करता है—जिससे स्वचालित रिपोर्टिंग और इंटीग्रेशन सरल हो जाता है।

## पूर्वापेक्षाएँ
- **Java Development Kit (JDK)** – JDK 11 या बाद का संस्करण इंस्टॉल करें। आप इसे [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) से डाउनलोड कर सकते हैं।  
- **Aspose.Tasks for Java library** – नवीनतम रिलीज़ को [download page](https://releases.aspose.com/tasks/java/) से डाउनलोड करें और JAR को अपने प्रोजेक्ट की क्लासपाथ में जोड़ें।

## पैकेज इम्पोर्ट करें
`Project`, `Task`, और `TaskBaseline` क्लासेस `com.aspose.tasks` नेमस्पेस में स्थित हैं। इन्हें अपने सोर्स फ़ाइल के शीर्ष पर इम्पोर्ट करें:

`Project` क्लास Aspose.Tasks का टॉप‑लेवल ऑब्जेक्ट है जो मेमोरी में एक सिंगल प्रोजेक्ट फ़ाइल को दर्शाता है। यह टास्क, रिसोर्सेज, और बेसलाइन कलेक्शन तक पहुँच प्रदान करता है।

## बेसलाइन कैसे पढ़ें?

प्रोजेक्ट को लोड करें, फिर प्रत्येक टास्क के लिए `TaskBaseline` कलेक्शन को क्वेरी करें। `TaskBaseline` ऑब्जेक्ट वह बेसलाइन स्टार्ट, फिनिश, और ड्यूरेशन रिटर्न करता है जो आपने `setBaseline` कॉल करने पर कैप्चर किए थे। यह सीधा तरीका आपको XML या बाइनरी फ़ाइलों को पार्स किए बिना बेसलाइन मान पढ़ने की अनुमति देता है।

## चरण 1: नया प्रोजेक्ट इंस्टेंस बनाएं
`Project` क्लास मेमोरी में पूरे प्रोजेक्ट फ़ाइल को दर्शाता है।
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## चरण 2: टास्क परिभाषित करें और बेसलाइन सेट करें
`Task` एक व्यक्तिगत कार्य आइटम को दर्शाता है, और `setBaseline` उसकी वर्तमान शेड्यूल को बेसलाइन के रूप में कैप्चर करता है।
```java
Project project = new Project();
```

## चरण 3: बेसलाइन जानकारी तक पहुँचें
`TaskBaseline` एक बेसलाइन के लिए सेव किए गए स्टार्ट, फिनिश, और ड्यूरेशन मान रखता है।
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## चरण 4: बेसलाइन ड्यूरेशन दिखाएँ
`Duration` एक टास्क या बेसलाइन की अवधि को दर्शाता है।
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## चरण 5: बेसलाइन स्टार्ट डेट दिखाएँ
`Start` बेसलाइन की निर्धारित प्रारंभ तिथि है।
```java
System.out.println(baseline.getDuration().toString());
```

## चरण 6: बेसलाइन फिनिश डेट दिखाएँ
`Finish` बेसलाइन की निर्धारित समाप्ति तिथि है।
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## सामान्य समस्याएँ और समाधान
- **Baseline not set:** सुनिश्चित करें कि आप टास्क जोड़ने के **बाद** `project.setBaseline(BaselineType.Baseline)` कॉल करें; अन्यथा बेसलाइन कलेक्शन खाली रहेगा।  
- **Null values:** यदि `task.getBaselines()` एक खाली लिस्ट रिटर्न करता है, तो यह जांचें कि बेसलाइन सेट करने से पहले टास्क को प्रोजेक्ट हायरार्की में जोड़ा गया था।  
- **Date format:** `getStart()` और `getFinish()` मेथड्स `java.util.Date` ऑब्जेक्ट्स रिटर्न करते हैं। यदि आपको कस्टम डिस्प्ले फ़ॉर्मेट चाहिए तो `SimpleDateFormat` का उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: Aspose.Tasks में नया प्रोजेक्ट इंस्टेंस कैसे बनाएं?**  
A: `Project` क्लास को इंस्टैंशिएट करें (`Project project = new Project();`)। यह टास्क और बेसलाइन के लिए तैयार एक नया प्रोजेक्ट फ़ाइल बनाता है।

**Q: `BaselineType.Baseline` और अन्य बेसलाइन टाइप्स में क्या अंतर है?**  
A: `BaselineType.Baseline` प्राथमिक बेसलाइन (Baseline 1) को दर्शाता है। Aspose.Tasks अतिरिक्त स्नैपशॉट्स के लिए Baseline 2‑10 को भी सपोर्ट करता है।

**Q: क्या मैं बेसलाइन डेटा को Excel या CSV में एक्सपोर्ट कर सकता हूँ?**  
A: हाँ, आप `TaskBaseline` ऑब्जेक्ट्स पर इटरेट करके मानों को मानक Java I/O का उपयोग करके CSV फ़ाइल में लिख सकते हैं।

**Q: क्या बेसलाइन सेट करने से मौजूदा टास्क डेट्स प्रभावित होते हैं?**  
A: बेसलाइन सेट करने से वर्तमान डेट्स कैप्चर होते हैं लेकिन टास्क के सक्रिय शेड्यूल को बदलते नहीं हैं। आप बेसलाइन सेट होने के बाद भी स्टार्ट/फिनिश डेट्स को एडजस्ट कर सकते हैं।

**Q: क्या प्रोग्रामेटिक रूप से कई बेसलाइन की तुलना करना संभव है?**  
A: बिल्कुल। प्रत्येक बेसलाइन को `task.getBaselines().get(index)` के माध्यम से प्राप्त करें और उनके `Start`, `Finish`, और `Duration` प्रॉपर्टीज़ की तुलना करें।

---

**अंतिम अपडेट:** 2026-08-29  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose  








```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## संबंधित ट्यूटोरियल

- [Create Task List Java – Aspose.Tasks के साथ MS Project बेसलाइन](/tasks/java/task-baselines/create-task-baseline/)
- [Aspose.Tasks for Java में बेसलाइन ड्यूरेशन कैसे सेट करें](/tasks/java/task-baselines/task-baseline-duration/)
- [Create MPP Project Java – Aspose.Tasks के साथ टास्क प्रोग्रेस बदलें](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}