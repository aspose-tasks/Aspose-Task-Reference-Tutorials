---
date: 2026-06-25
description: Aspose.Tasks for Java का उपयोग करके टास्क जोड़ने और MPP फ़ाइलों को अपडेट
  करने का तरीका जानें, जो एक जावा प्रोजेक्ट मैनेजमेंट लाइब्रेरी है जो आपको टास्क Microsoft
  Project फ़ाइलें बनाने और प्रोजेक्ट को MPP के रूप में सहेजने की अनुमति देती है।
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: Aspose.Tasks में टास्क जोड़ने और MPP फ़ाइल को अपडेट करने का तरीका
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में टास्क जोड़ने और MPP फ़ाइल को अपडेट करने का तरीका
url: /hi/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में टास्क जोड़ने और MPP फ़ाइल अपडेट करने का तरीका

## परिचय
इस ट्यूटोरियल में आप **टास्क कैसे जोड़ें** को एक मौजूदा Microsoft Project (MPP) फ़ाइल में जोड़ना और फिर Aspose.Tasks for Java, एक प्रमुख **जावा प्रोजेक्ट मैनेजमेंट लाइब्रेरी** का उपयोग करके अपडेटेड शेड्यूल को सहेजना सीखेंगे। चाहे आप एक कस्टम शेड्यूलर बना रहे हों, बड़े पैमाने पर अपडेट को स्वचालित कर रहे हों, या प्रोजेक्ट डेटा को बड़े सिस्टम में एकीकृत कर रहे हों, नीचे दिया गया चरण‑दर‑चरण गाइड दिखाता है कि प्रोजेक्ट को कैसे लोड करें, नया टास्क कैसे डालें, उसकी तिथियां सेट करें, और परिणाम को एक नई MPP दस्तावेज़ के रूप में कैसे सहेजें।

## त्वरित उत्तर
- **“how to add task” का अर्थ इस संदर्भ में क्या है?** यह मौजूदा MPP फ़ाइल के भीतर प्रोग्रामेटिक रूप से एक नया कार्य आइटम बनाना है।  
- **कौन सी लाइब्रेरी यह ऑपरेशन संभालती है?** Aspose.Tasks for Java, एक मजबूत जावा प्रोजेक्ट मैनेजमेंट लाइब्रेरी।  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए एक फ्री ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **क्या मैं परिणाम को MPP के रूप में सहेज सकता हूँ?** हाँ—`project.save(..., SaveFileFormat.Mpp)` का उपयोग करके **प्रोजेक्ट को mpp के रूप में सहेजें**।  
- **कौन सा जावा संस्करण आवश्यक है?** Java 8 या बाद का।

## MPP फ़ाइल में “how to add task” क्या है?
टास्क जोड़ना मतलब प्रोजेक्ट हायरार्की में एक नया कार्य आइटम डालना, उसकी प्रारंभ/समाप्ति तिथियां निर्धारित करना, और परिवर्तन को MPP फ़ाइल में वापस सहेजना। Aspose.Tasks फ़ाइल फ़ॉर्मेट के लो‑लेवल विवरणों को एब्स्ट्रैक्ट करता है, जिससे आप बिजनेस लॉजिक पर ध्यान केंद्रित कर सकते हैं जबकि यह स्वचालित रूप से रिसोर्स असाइनमेंट, कैलेंडर, और डिपेंडेंसी कैलकुलेशन को संभालता है। यह संबंधित असाइनमेंट को भी अपडेट करता है और प्रोजेक्ट शेड्यूल को पुनः‑गणना करता है ताकि डिपेंडेंट टास्क्स के बीच संगति बनी रहे।

## क्यों उपयोग करें Aspose.Tasks for Java?
- **पूर्ण संगतता**: Microsoft Project 2007‑2021 की 100% सुविधाओं का समर्थन करता है (150 से अधिक टास्क प्रकार और 200 रिसोर्स फ़ील्ड)।  
- **Zero‑dependency**: कोई COM, Office, या नेटिव लाइब्रेरी आवश्यक नहीं—शुद्ध जावा API जहाँ भी JRE चलता है, वहाँ चलता है।  
- **समृद्ध फीचर सेट**: टास्क लिंकिंग, रिसोर्स एलोकेशन, कस्टम फ़ील्ड, और बिल्ट‑इन रिपोर्टिंग शामिल हैं।  
- **उच्च प्रदर्शन**: 10,000 तक टास्क वाले प्रोजेक्ट को 200 MB से कम RAM में प्रोसेस करता है, जिससे यह सर्वर‑साइड ऑटोमेशन के लिए आदर्श है।

## पूर्वापेक्षाएँ
1. **Java Development Environment** – JDK 8+ स्थापित और कॉन्फ़िगर किया हुआ।  
2. **Aspose.Tasks for Java** – [download page](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. **Basic Java knowledge** – क्लासेज़, ऑब्जेक्ट्स, और डेट हैंडलिंग की परिचितता।

## पैकेज आयात करें
पहले, उन क्लासेज़ को आयात करें जिनकी आपको आवश्यकता होगी। यह आपको प्रोजेक्ट मैनिपुलेशन, टास्क प्रॉपर्टीज़, और डेट हैंडलिंग तक पहुंच देता है।

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` मेमोरी में लोड किए गए Microsoft Project फ़ाइल का प्रतिनिधित्व करता है। `SaveFileFormat` उन फ़ॉर्मेट्स को एनेमरेट करता है जिनमें आप सहेज सकते हैं, जैसे MPP या PDF। `Task` प्रोजेक्ट हायरार्की के भीतर एक व्यक्तिगत कार्य आइटम को मॉडल करता है। `Tsk` टास्क फ़ील्ड्स के लिए कॉन्स्टेंट्स प्रदान करता है जो मान सेट या रिट्रीव करने में उपयोग होते हैं। `Calendar` शेड्यूल परिभाषित करने के लिए डेट‑टाइम यूटिलिटीज़ प्रदान करता है।

## चरण 1: डेटा डायरेक्टरी निर्धारित करें
```java
String dataDir = "Your Data Directory";
```  
`"Your Data Directory"` को उस पूर्ण पथ से बदलें जहाँ आपका स्रोत MPP फ़ाइल स्थित है।

## चरण 2: मौजूदा प्रोजेक्ट पढ़ें
`Project` क्लास Aspose.Tasks का कोर ऑब्जेक्ट है जो मेमोरी में Microsoft Project फ़ाइल का प्रतिनिधित्व करता है।  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
कंस्ट्रक्टर **SampleMSP2010.mpp** को लोड करता है, जिससे आपको एक पूरी तरह से मैनिपुलेटेबल ऑब्जेक्ट मॉडल मिलता है।

## चरण 3: नया टास्क बनाएं (how to add task)
`Task` क्लास प्रोजेक्ट हायरार्की के भीतर एक व्यक्तिगत कार्य आइटम को दर्शाता है।  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
यह पंक्ति **टास्क को mpp में बनाती है** रूट टास्क में *Task1* नामक एक चाइल्ड जोड़कर।

## चरण 4: प्रारंभ और समाप्ति तिथियां सेट करें
`Calendar` क्लास डेट‑टाइम यूटिलिटीज़ प्रदान करती है; महीने शून्य‑आधारित होते हैं (उदा., `Calendar.JULY`)।  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
यहाँ हम नए जोड़े गए टास्क के लिए शेड्यूल परिभाषित करते हैं। अपनी प्रोजेक्ट टाइमलाइन के अनुसार तिथियों को समायोजित करें।

## चरण 5: प्रोजेक्ट सहेजें (save project as mpp)
`SaveFileFormat.Mpp` Aspose.Tasks को फ़ाइल को मूल Microsoft Project फ़ॉर्मेट में वापस लिखने के लिए बताता है।  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
अपडेटेड प्रोजेक्ट, जिसमें नया टास्क अब शामिल है, **AfterLinking.mpp** के रूप में सहेजा जाता है।

## सामान्य समस्याएं और समाधान
| समस्या | समाधान |
|-------|----------|
| **फ़ाइल नहीं मिली** | Verify `dataDir` ends with a path separator (`/` or `\\`) and the file name is correct. |
| **गलत तिथियां** | Remember that `Calendar` months are zero‑based; `Calendar.JULY` is correct for July. |
| **लाइसेंस अपवाद** | Install a valid Aspose.Tasks license before calling any API to avoid evaluation watermarks. |

## अक्सर पूछे जाने वाले प्रश्न
**Q: मैं एक साथ कई टास्क कैसे जोड़ूँ?**  
A: टास्क नामों के संग्रह पर लूप चलाएँ और लूप के भीतर “create task” ब्लॉक को दोहराएँ।

**Q: क्या मैं नए टास्क के लिए कस्टम फ़ील्ड सेट कर सकता हूँ?**  
A: हाँ—`task.set(Tsk.CUSTOM_FIELD_x, value)` का उपयोग करें जहाँ *x* फ़ील्ड इंडेक्स है।

**Q: क्या मौजूदा टास्क को टेम्पलेट के रूप में कॉपी करना संभव है?**  
A: स्रोत टास्क को क्लोन करें (`Task cloned = sourceTask.clone();`) और फिर इसे इच्छित पैरेंट में जोड़ें।

**Q: यदि मुझे नया टास्क जोड़ने के बजाय मौजूदा टास्क को अपडेट करना हो तो क्या करें?**  
A: टास्क को ID द्वारा प्राप्त करें (`Task existing = project.getRootTask().getChildren().getById(id);`) और उसकी प्रॉपर्टीज़ को संशोधित करें।

**Q: क्या Aspose.Tasks PDF या PNG जैसे अन्य फ़ॉर्मेट में सहेजने का समर्थन करता है?**  
A: हाँ—`project.save("output.pdf", SaveFileFormat.Pdf);` या विज़ुअल रिप्रेजेंटेशन के लिए `SaveFileFormat.Png` का उपयोग करें।

---

**अंतिम अपडेट:** 2026-06-25  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [MPP फ़ाइल कैसे बनाएं – Aspose.Tasks के साथ MPP फ़ॉर्मेट में खाली प्रोजेक्ट बनाएं और सहेजें](/tasks/java/project-configuration/create-save-mpp/)
- [प्रोजेक्ट कैसे बनाएं – Aspose.Tasks के साथ नई टास्क एट्रिब्यूट सेट करें](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Create Task List Java – Aspose.Tasks का उपयोग करके MS Project बेसलाइन](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}