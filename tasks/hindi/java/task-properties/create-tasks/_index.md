---
date: 2026-09-25
description: Aspose.Tasks का उपयोग करके Java में प्रोजेक्ट शेड्यूल बनाना सीखें। यह
  गाइड आपको सारांश कार्य जोड़ना, प्रोजेक्ट पदानुक्रम प्रबंधित करना, और दस्तावेज़ डायरेक्टरी
  को कुशलतापूर्वक सेट करने का तरीका दिखाता है।
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: Aspose.Tasks में टास्क बनाएं
og_description: Aspose.Tasks का उपयोग करके Java में प्रोजेक्ट शेड्यूल बनाना सीखें।
  सारांश कार्य जोड़ने, पदानुक्रम प्रबंधित करने, और दस्तावेज़ डायरेक्टरी सेट करने के
  लिए चरण‑दर‑चरण निर्देशों का पालन करें।
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: Aspose.Tasks for Java के साथ प्रोजेक्ट शेड्यूल कैसे बनाएं
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: Aspose.Tasks for Java के साथ प्रोजेक्ट शेड्यूल कैसे बनाएं
url: /hi/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java के साथ प्रोजेक्ट शेड्यूल कैसे बनाएं

## परिचय
इस ट्यूटोरियल में आप सीखेंगे कि Aspose.Tasks का उपयोग करके जावा एप्लिकेशन में **प्रोजेक्ट शेड्यूल बनाएं**। चाहे आप एक साधारण टू‑डू लिस्ट बना रहे हों या एक जटिल एंटरप्राइज़‑लेवल प्लानर, नीचे दिए गए चरण सारांश कार्य जोड़ने, प्रोजेक्ट पदानुक्रम प्रबंधित करने, और दस्तावेज़ डायरेक्टरी सेट करने के बारे में मार्गदर्शन करेंगे—सभी स्पष्ट, चलाने योग्य कोड स्निपेट्स के साथ। अंत तक, आपके पास आगे की हेरफेर या निर्यात के लिए तैयार एक पूरी तरह से संरचित शेड्यूल होगा।

## त्वरित उत्तर
- **Aspose.Tasks क्या प्रबंधित करता है?** यह टास्क पदानुक्रम, संसाधन, कैलेंडर, और प्रोजेक्ट फ़ाइल फ़ॉर्मेट (MS‑Project, Primavera, आदि) को संभालता है।  
- **क्या विकास के लिए लाइसेंस चाहिए?** मूल्यांकन के लिए एक मुफ्त अस्थायी लाइसेंस काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **कौन सा जावा संस्करण समर्थित है?** जावा 8 और उसके बाद के संस्करण पूरी तरह समर्थित हैं।  
- **क्या मैं टास्क में कस्टम फ़ील्ड जोड़ सकता हूँ?** हाँ, आप API के माध्यम से उपयोगकर्ता‑परिभाषित फ़ील्ड के साथ टास्क को विस्तारित कर सकते हैं।  
- **क्या गैंट चार्ट के लिए बिल्ट‑इन समर्थन है?** Aspose.Tasks PDF/HTML में निर्यात कर सकता है जिसमें गैंट विज़ुअलाइज़ेशन शामिल होते हैं।

## Aspose.Tasks में प्रोजेक्ट शेड्यूल क्या है?
प्रोजेक्ट शेड्यूल कार्यों, निर्भरताओं और समयसीमाओं का पूर्ण सेट है जो यह निर्धारित करता है कि काम कैसे किया जाएगा। Aspose.Tasks इस जानकारी को एक `Project` ऑब्जेक्ट में संग्रहीत करता है जिसे आप विभिन्न फ़ॉर्मेट में पढ़, संशोधित और सहेज सकते हैं। इसमें प्रारंभ और समाप्ति तिथियां, प्रतिबंध, और संसाधन असाइनमेंट शामिल होते हैं, जिससे व्यापक योजना और रिपोर्टिंग संभव होती है।

## जावा प्रोजेक्ट मैनेजमेंट के लिए Aspose.Tasks क्यों उपयोग करें?
Aspose.Tasks **30+ इनपुट और आउटपुट फ़ॉर्मेट** का समर्थन करता है और **10,000 से अधिक टास्क** वाले प्रोजेक्ट को पूरी फ़ाइल को मेमोरी में लोड किए बिना प्रोसेस कर सकता है, जिससे बड़े‑पैमाने के जावा प्रोजेक्ट मैनेजमेंट परिदृश्यों के लिए उच्च प्रदर्शन मिलता है।

## आवश्यकताएँ
ट्यूटोरियल शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ मौजूद हैं:
- **Java Development Kit (JDK)** – आपके मशीन पर JDK 8 या उससे नया स्थापित हो।  
- **Aspose.Tasks for Java लाइब्रेरी** – लाइब्रेरी को [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/) से डाउनलोड और इंस्टॉल करें।  
- **Integrated Development Environment (IDE)** – Eclipse, IntelliJ IDEA, या कोई भी जावा‑अनुकूल IDE उपयोग करें।

## पैकेज इम्पोर्ट करें
`Project`, `Task`, और संबंधित क्लासेस `com.aspose.tasks` नेमस्पेस में स्थित हैं। इन्हें अपने जावा फ़ाइल के शीर्ष पर इम्पोर्ट करें:

`Project` क्लास एक पूर्ण प्रोजेक्ट शेड्यूल का प्रतिनिधित्व करती है और टास्क व संसाधनों को संशोधित करने के लिए मेथड्स प्रदान करती है।

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

`Project` क्लास प्रोजेक्ट फ़ाइल पर सभी ऑपरेशन्स के लिए एंट्री पॉइंट है।

## Aspose.Tasks के साथ प्रोजेक्ट शेड्यूल कैसे बनाएं?

एक नया `Project` इंस्टेंस लोड करें, दस्तावेज़ डायरेक्टरी सेट करें, और टास्क जोड़ना शुरू करें। यह सीधा‑उत्तर पैराग्राफ मुख्य प्रवाह को समझाता है: आप एक `Project` बनाते हैं, उसके `RootFolder` (दस्तावेज़ डायरेक्टरी) को कॉन्फ़िगर करते हैं, फिर एक सारांश टास्क जोड़ते हैं और उसके बाद सब‑टास्क। सभी परिवर्तन मेमोरी में रखे जाते हैं जब तक आप `save` को कॉल नहीं करते ताकि शेड्यूल को फ़ाइल में सहेजा जा सके।

### चरण 1: दस्तावेज़ डायरेक्टरी सेट करें
परिभाषित करें कि परिणामी प्रोजेक्ट फ़ाइल कहाँ लिखी जाएगी। डायरेक्टरी को पहले सेट करने से सभी बाद के सहेजने के ऑपरेशन एकसमान पथ का उपयोग करेंगे।

`RootFolder` प्रॉपर्टी उस बेस फ़ोल्डर को निर्दिष्ट करती है जहाँ प्रोजेक्ट फ़ाइलें पढ़ी या लिखी जाती हैं।

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### चरण 2: नया प्रोजेक्ट बनाएं
एक नया `Project` ऑब्जेक्ट बनाएं जो आपका शेड्यूल रखेगा। आप वैकल्पिक रूप से एक मौजूदा फ़ाइल पाथ पास करके मौजूदा शेड्यूल को लोड कर संशोधित भी कर सकते हैं।

`Project` कंस्ट्रक्टर एक खाली शेड्यूल बनाता है जो टास्क जोड़ने के लिए तैयार है।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### चरण 3: एक सारांश टास्क जोड़ें
एक सारांश टास्क संबंधित सब‑टास्क को समूहित करता है और गैंट चार्ट में एक कोलेप्सिबल नोड के रूप में दिखता है। `Task` क्लास का उपयोग करें और `IsSummary` को `true` सेट करें।

`addTask` मेथड निर्दिष्ट पैरेंट के तहत एक नया टास्क बनाता है और उसका ID लौटाता है।

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### चरण 4: एक सबटास्क जोड़ें
सबटास्क अपने पैरेंट सारांश टास्क से प्रारंभ/समाप्ति तिथियां विरासत में लेते हैं जब तक आप उन्हें ओवरराइड नहीं करते। सबटास्क जोड़ना इतना ही सरल है कि आप फिर से `addTask` कॉल करें और पैरेंट ID निर्दिष्ट करें।

पैरेंट ID के साथ `addTask` कॉल करने से उस सारांश टास्क के तहत एक सबटास्क जुड़ता है।

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

अपने प्रोजेक्ट के लिए आवश्यकतानुसार जितने भी टास्क और सबटास्क जोड़ें। प्रत्येक चरण एक संरचित प्रोजेक्ट पदानुक्रम बनाने में योगदान देता है जिसे MS‑Project, PDF, या अन्य समर्थित फ़ॉर्मेट में निर्यात किया जा सकता है।

## सामान्य समस्याएँ और समाधान
- **समस्या:** “Document directory not found.”  
  **समाधान:** सुनिश्चित करें कि आप जो पाथ `RootFolder` को असाइन करते हैं वह फ़ाइल सिस्टम में मौजूद है और आपका जावा प्रोसेस लिखने की अनुमति रखता है।
- **समस्या:** सबटास्क सारांश टास्क के तहत नहीं दिख रहे हैं।  
  **समाधान:** `addTask` कॉल करते समय सही पैरेंट टास्क ID पास करें। API को पैरेंट ID दूसरे आर्ग्यूमेंट के रूप में चाहिए।
- **समस्या:** बड़े प्रोजेक्ट्स से OutOfMemoryError आता है।  
  **समाधान:** Aspose.Tasks टास्क को स्ट्रीमिंग मोड में प्रोसेस करता है; JVM हीप साइज (`-Xmx2g`) बढ़ाएँ या शेड्यूल को कई फ़ाइलों में विभाजित करें।

## अक्सर पूछे जाने वाले प्रश्न
**Q: क्या Aspose.Tasks छोटे‑पैमाने के प्रोजेक्ट्स के लिए उपयुक्त है?**  
A: बिल्कुल। लाइब्रेरी एक सिंगल‑टास्क लिस्ट से लेकर एंटरप्राइज़‑लेवल शेड्यूल तक, जिसमें हजारों टास्क होते हैं, स्केल करती है।

**Q: Aspose.Tasks for Java की विस्तृत दस्तावेज़ीकरण कहाँ मिल सकती है?**  
A: दस्तावेज़ीकरण देखें [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/)।

**Q: Aspose.Tasks के लिए अस्थायी लाइसेंस कैसे प्राप्त करें?**  
A: विकास और परीक्षण के लिए समय‑सीमित लाइसेंस के लिए [temporary license request page](https://purchase.aspose.com/temporary-license/) पर जाएँ।

**Q: क्या मैं Aspose.Tasks का उपयोग करके टास्क एट्रिब्यूट्स को कस्टमाइज़ कर सकता हूँ?**  
A: हाँ, आप टास्क को कस्टम फ़ील्ड्स के साथ विस्तारित कर सकते हैं, संसाधन असाइन कर सकते हैं, और प्रोग्रामेटिकली कैलेंडर संशोधित कर सकते हैं।

**Q: क्या Aspose.Tasks उपयोगकर्ताओं के लिए कोई सपोर्ट कम्युनिटी है?**  
A: बिल्कुल! [the support forum](https://forum.aspose.com/c/tasks/15) पर Aspose.Tasks कम्युनिटी से जुड़ें।

---

**अंतिम अपडेट:** 2026-09-25  
**परीक्षण किया गया:** Aspose.Tasks 24.12 for Java  
**लेखक:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## संबंधित ट्यूटोरियल

- [Aspose.Tasks for Java का उपयोग करके MS Project में प्रोजेक्ट स्टार्ट डेट सेट करें](/tasks/java/project-properties/write-project-info/)
- [Aspose.Tasks में प्रोजेक्ट मैनेजमेंट टास्क डिपेंडेंसी बनाएं](/tasks/java/task-links/create-task-link/)
- [Aspose.Tasks में प्रोजेक्ट में रिसोर्स जोड़ना और रिसोर्स असाइनमेंट बनाना](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}