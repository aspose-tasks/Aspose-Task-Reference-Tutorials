---
date: 2026-08-29
description: Java में प्रोजेक्ट में task जोड़ना, task सूची बनाना, और Aspose.Tasks
  का उपयोग करके Microsoft Project के बिना baseline सेट करना सीखें।
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: Aspose.Tasks में Task Baseline बनाना
og_description: Aspose.Tasks का उपयोग करके Java में प्रोजेक्ट में task जोड़ना और baseline
  सेट करना सीखें। यह गाइड स्टेप‑बाय‑स्टेप कोड दिखाता है, बिना Microsoft Project की
  आवश्यकता के।
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: Java में प्रोजेक्ट में task जोड़ने और baseline सेट करने का तरीका
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: Java में प्रोजेक्ट में task जोड़ने और baseline सेट करने का तरीका
url: /hi/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java में प्रोजेक्ट में टास्क जोड़ने और बेसलाइन सेट करने का तरीका

## परिचय
इस ट्यूटोरियल में आप प्रोग्रामेटिक रूप से **add task to project** करेंगे, Microsoft Project टास्क बेसलाइन जेनरेट करेंगे, और फ़ाइल सहेजेंगे—बिना कभी Microsoft Project खोले। Aspose.Tasks for Java आपको एक शुद्ध‑Java API प्रदान करता है जो किसी भी प्लेटफ़ॉर्म पर काम करता है, जिससे यह स्वचालित बिल्ड पाइपलाइन, रिपोर्टिंग सेवाओं, या किसी भी सर्वर‑साइड समाधान के लिए उपयुक्त बनता है जिसे .mpp फ़ाइलों को हेरफेर करने की आवश्यकता है।

## त्वरित उत्तर
- **What does Aspose.Tasks do?** यह Microsoft Project की आवश्यकता के बिना Microsoft Project फ़ाइलों को बनाने, पढ़ने और संपादित करने के लिए एक Java API प्रदान करता है।  
- **Do I need Microsoft Project installed?** नहीं, यह लाइब्रेरी पूरी तरह से स्वतंत्र रूप से काम करती है।  
- **Which Java version is required?** JDK 8 या उससे ऊपर।  
- **Can I set a baseline for a single task?** हाँ – `setBaseline` को उस सूची पर कॉल करें जिसमें केवल वही टास्क हों जिन्हें आप चाहते हैं।  
- **Is a license needed for production?** हाँ, एक कमर्शियल लाइसेंस मूल्यांकन सीमाओं को हटाता है और सभी फीचर अनलॉक करता है।

## टास्क बेसलाइन क्या है?
एक टास्क बेसलाइन वह मूल रूप से नियोजित प्रारंभ तिथि, समाप्ति तिथि, और कार्य प्रयास को कैप्चर करती है जो शेड्यूल पहली बार सहेजे जाने पर टास्क के लिए निर्धारित होती है। यह स्नैपशॉट एक संदर्भ बिंदु के रूप में कार्य करता है, जिससे प्रोजेक्ट मैनेजर्स वास्तविक प्रगति और लागत को प्रारंभिक योजना से तुलना कर सकते हैं, और प्रदर्शन विश्लेषण के लिए विचलन की गणना कर सकते हैं।

## Java में प्रोजेक्ट में टास्क जोड़ने के लिए Aspose.Tasks क्यों उपयोग करें?
आप डेस्कटॉप इंस्टॉलेशन के बिना टास्क बना, संशोधित और बेसलाइन कर सकते हैं, जिससे पूरी तरह स्वचालित वर्कफ़्लो संभव होते हैं। Aspose.Tasks **50+ इनपुट और आउटपुट फॉर्मैट** का समर्थन करता है और **सैकड़ों टास्क** वाले प्रोजेक्ट को संभाल सकता है जबकि मेमोरी उपयोग 200 MB से कम रखता है, जिससे यह क्लाउड सेवाओं और CI/CD पाइपलाइनों के लिए आदर्श बनता है।

## पूर्वापेक्षाएँ
1. **Java Development Kit (JDK)** – JDK 8 या नए संस्करण को इंस्टॉल करें।  
2. **Aspose.Tasks for Java** – लाइब्रेरी को [download link](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  

## पैकेज आयात करें
अपने Java प्रोजेक्ट में Aspose.Tasks के साथ काम शुरू करने के लिए, आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## चरण 1: प्रोजेक्ट ऑब्जेक्ट बनाएं
`Project` क्लास Aspose.Tasks का टॉप‑लेवल ऑब्जेक्ट है जो मेमोरी में Microsoft Project फ़ाइल का प्रतिनिधित्व करता है। इसे इंस्टैंशिएट करने से आपको एक खाली प्रोजेक्ट मिलता है जिसे आप टास्क, रिसोर्सेज और कैलेंडर से भर सकते हैं।

```java
Project project = new Project();
```
यहाँ हम एक नया `Project` ऑब्जेक्ट इंस्टैंशिएट करते हैं – यह वह MS Project फ़ाइल दर्शाता है जो हमारी टास्क सूची को रखेगी।

## चरण 2: प्रोजेक्ट में टास्क जोड़ें
`Task` क्लास प्रोजेक्ट शेड्यूल में एक व्यक्तिगत कार्य आइटम का प्रतिनिधित्व करता है। प्रत्येक `Task` की अपनी अवधि, प्रारंभ तिथि, और रिसोर्स असाइनमेंट हो सकते हैं।

```java
Task task = project.getRootTask().getChildren().add("Task");
```
`getRootTask()` का उपयोग करके हम प्रोजेक्ट हायरेरकी की रूट तक पहुँचते हैं और **add task to Microsoft Project** करते हैं। स्ट्रिंग `"Task"` टास्क का नाम है; आप इसे अपनी आवश्यकतानुसार किसी भी विवरण से बदल सकते हैं।

## चरण 3: निर्दिष्ट टास्क के लिए बेसलाइन सेट करें
`BaselineType` एक एन्यूमरेशन है जो यह निर्धारित करता है कि आप कौन सा बेसलाइन स्लॉट (Baseline, Baseline1 … Baseline10) लिखना चाहते हैं। टास्क की सूची पास करके आप केवल चयनित आइटम्स की बेसलाइन सेट कर सकते हैं।

```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
**MS Project के बिना बेसलाइन सेट करने** के लिए, उन टास्कों की एक सूची बनाएं जिन्हें आप बेसलाइन करना चाहते हैं (यहाँ `myList`) और इसे `setBaseline` को पास करें। यदि आपको केवल चयनात्मक बेसलाइन चाहिए तो `myList` को आपने जो टास्क जोड़े हैं, उनसे भरें।

## चरण 4: पूरे प्रोजेक्ट के लिए बेसलाइन सेट करें
`setBaseline` चयनित बेसलाइन मानों को प्रोजेक्ट के प्रत्येक टास्क में लिखता है।  
यदि आप एक ही कॉल में पूरे प्रोजेक्ट की बेसलाइन सेट करना चाहते हैं, तो बस इच्छित `BaselineType` के साथ `setBaseline` को कॉल करें।

```java
project.setBaseline(BaselineType.Baseline);
```
यह कॉल प्रोजेक्ट में **हर टास्क** के लिए चुने गए बेसलाइन मान लिखता है, जिससे मूल शेड्यूल का पूर्ण स्नैपशॉट सुनिश्चित होता है।

## Aspose.Tasks का उपयोग करके Microsoft Project में टास्क कैसे जोड़ें
`add()` निर्दिष्ट पैरेंट टास्क के तहत एक नया चाइल्ड टास्क बनाता है और नई बनाई गई `Task` ऑब्जेक्ट लौटाता है।  
आप पैरेंट `Task` ऑब्जेक्ट (आमतौर पर रूट टास्क) पर `add()` को कॉल करके टास्क जोड़ते हैं। यह मेथड एक नया `Task` इंस्टेंस लौटाता है जिसे आप आगे कॉन्फ़िगर कर सकते हैं—अवधि, प्रारंभ तिथि, रिसोर्सेज, या कस्टम फ़ील्ड्स—प्रोजेक्ट फ़ाइल सहेजने से पहले।

## MS Project के बिना बेसलाइन कैसे सेट करें
Aspose.Tasks पूरी तरह कोड के माध्यम से बेसलाइन निर्माण को सक्षम करता है। एक `BaselineType` चुनें (जैसे, `BaselineType.Baseline`) और `setBaseline` को कॉल करें। आप इसे `Baseline1`‑`Baseline10` के साथ दोहरा सकते हैं ताकि कई रिवीजन बेसलाइन रखी जा सकें, सभी बिना Microsoft Project खोले।

## सामान्य समस्याएँ और समाधान
- **Baseline not appearing:** बेसलाइन सेट करने के बाद सुनिश्चित करें कि आप `project.save("output.mpp")` कॉल करें (संक्षिप्तता के लिए सहेजने का चरण यहाँ छोड़ा गया है)।  
- **Task list appears empty:** यह जाँचें कि आप टास्क सही पैरेंट (`getRootTask()` या किसी सब‑टास्क) में जोड़ रहे हैं।  
- **Version mismatch errors:** नवीनतम Aspose.Tasks JAR का उपयोग करें ताकि नए .mpp फ़ॉर्मैट्स के साथ संगतता सुनिश्चित हो सके।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Microsoft Project स्थापित किए बिना Aspose.Tasks for Java का उपयोग कर सकता हूँ?**  
A: हाँ, Aspose.Tasks स्वतंत्र रूप से काम करता है और होस्ट मशीन पर Microsoft Project की आवश्यकता नहीं होती।

**Q: क्या Aspose.Tasks for Java विभिन्न संस्करणों के Microsoft Project के साथ संगत है?**  
A: बिल्कुल। यह लाइब्रेरी 2007 से लेकर नवीनतम 2024 रिलीज़ तक के प्रोजेक्ट फ़ाइलों का समर्थन करती है।

**Q: क्या मैं Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट रिसोर्सेज को हेरफेर कर सकता हूँ?**  
A: हाँ, आप प्रोग्रामेटिक रूप से रिसोर्सेज को जोड़, अपडेट और डिलीट कर सकते हैं, बिलकुल टास्क की तरह।

**Q: क्या Aspose.Tasks for Java टास्क डिपेंडेंसी सेट करने का समर्थन करता है?**  
A: हाँ, आप `TaskLink` क्लास का उपयोग करके प्रीडेससर‑सक्सेसर संबंध परिभाषित कर सकते हैं।

**Q: क्या Aspose.Tasks for Java के लिए तकनीकी समर्थन उपलब्ध है?**  
A: हाँ, आप [support forum](https://forum.aspose.com/c/tasks/15) के माध्यम से मदद प्राप्त कर सकते हैं, जहाँ Aspose स्टाफ और समुदाय प्रश्नों का उत्तर देते हैं।

## निष्कर्ष
इन चरणों का पालन करके आपने Java में **add task to project** करना, टास्क सूची बनाना, और Aspose.Tasks का उपयोग करके **MS Project के बिना बेसलाइन सेट करना** सीख लिया है। यह तरीका प्रोजेक्ट ऑटोमेशन को सरल बनाता है, डेस्कटॉप प्रोजेक्ट इंस्टॉलेशन की आवश्यकता को हटाता है, और आपके शेड्यूल के हर पहलू पर पूर्ण प्रोग्रामेटिक नियंत्रण प्रदान करता है।

---

**अंतिम अपडेट:** 2026-08-29  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [प्रोजेक्ट aspose.tasks कैसे बनाएं – नई टास्क विशेषताएँ सेट करें](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Aspose.Tasks for Java में बेसलाइन अवधि कैसे सेट करें](/tasks/java/task-baselines/task-baseline-duration/)
- [Aspose Java में टास्क बनाएं – टास्क प्रॉपर्टीज़](/tasks/java/task-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}