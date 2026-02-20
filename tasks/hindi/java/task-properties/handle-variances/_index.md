---
date: 2026-02-20
description: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट की शुरूआती तिथि कैसे सेट
  करें और प्रोजेक्ट वैरिएंस को कैसे प्रबंधित करें, सीखें। यह गाइड यह भी दिखाता है
  कि टास्क की अवधि को प्रभावी ढंग से कैसे सेट किया जाए।
linktitle: Handle Task Variances in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: प्रोजेक्ट की शुरूआती तिथि निर्धारित करें और कार्य वैरिएंस को संभालें Aspose.Tasks
url: /hi/java/task-properties/handle-variances/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# प्रोजेक्ट की प्रारंभ तिथि सेट करें और टास्क वैरिएंस को संभालें Aspose.Tasks

## Introduction
प्रोजेक्ट मैनेजमेंट की दुनिया में, **set project start date** वह पहला कदम है जो आप अपने शेड्यूल को ठोस आधार देने के लिए उठाते हैं। Aspose.Tasks for Java इस चरण को—और उसके बाद टास्क वैरिएंस को संभालने को—सरल और भरोसेमंद बनाता है। इस ट्यूटोरियल में आप सीखेंगे कि प्रोजेक्ट की प्रारंभ तिथि कैसे सेट करें, टास्क की अवधि कैसे सेट करें, और प्रोजेक्ट वैरिएंस को प्रभावी ढंग से कैसे मैनेज करें।

## Quick Answers
- **प्रोजेक्ट की प्रारंभ तिथि सेट करने का मुख्य मेथड क्या है?** `project.set(Prj.START_DATE, …)` को `java.util.Calendar` इंस्टेंस के साथ उपयोग करें।  
- **वैरिएंस ट्रैकिंग के लिए कौन सा क्लास बेसलाइन दर्शाता है?** `BaselineType.Baseline`।  
- **क्या बेसलाइन सेट करने के बाद टास्क की प्रारंभ और समाप्ति तिथियों को समायोजित कर सकता हूँ?** हाँ, बस `Tsk.START` और `Tsk.STOP` को अपडेट करें।  
- **डेवलपमेंट उपयोग के लिए लाइसेंस चाहिए?** मूल्यांकन के लिए एक टेम्पररी लाइसेंस उपलब्ध है।  
- **इस कोड के साथ कौन सा Aspose.Tasks संस्करण काम करता है?** नवीनतम Aspose.Tasks for Java रिलीज़।

## What is **set project start date**?
प्रोजेक्ट की प्रारंभ तिथि सेट करना वह कैलेंडर दिन निर्धारित करता है जिससे सभी टास्क तिथियां गणना की जाती हैं। यह शेड्यूल गणना, क्रिटिकल पाथ विश्लेषण, और बेसलाइन निर्माण को प्रभावित करता है, जिससे सटीक वैरिएंस मैनेजमेंट संभव होता है।

## Why set project start date and manage variances?
- **पूर्वानुमानिता:** वास्तविक प्रगति की तुलना के लिए एक ज्ञात बेसलाइन स्थापित करता है।  
- **लचीलापन:** मूल योजना खोए बिना व्यक्तिगत टास्क तिथियों को समायोजित करने की अनुमति देता है।  
- **रिपोर्टिंग:** स्पष्ट वैरिएंस रिपोर्ट प्रदान करता है जो शेड्यूल स्लिपेज या शीघ्र समाप्तियों को उजागर करता है।  

## Prerequisites
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हों:

- Java Development Environment – एक स्थापित JDK और तैयार IDE या बिल्ड टूल।  
- Aspose.Tasks Library – लाइब्रेरी **[here](https://releases.aspose.com/tasks/java/)** से डाउनलोड करें।  

## Import Packages
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Step 1: Setting Up the Project
एक नया `Project` इंस्टेंस बनाएं जो सभी टास्क और शेड्यूल जानकारी रखेगा।

```java
Project project = new Project();
```

## Step 2: Adding a Task
रूट टास्क के तहत एक टास्क जोड़ें। यह वह कार्य आइटम होगा जिसे हम बाद में समायोजित करेंगे।

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Step 3: Setting Start Date and Duration
प्रोजेक्ट की प्रारंभ तिथि निर्धारित करें और टास्क को एक अवधि दें। यह व्यावहारिक रूप से **set task duration** को दर्शाता है।

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task.set(Tsk.DURATION, project.getDuration(2));
```

## Step 4: Setting Baseline
एक बेसलाइन बनाएं ताकि आप बाद में नियोजित बनाम वास्तविक तिथियों की तुलना कर सकें—जो **manage project variances** के लिए आवश्यक है।

```java
project.setBaseline(BaselineType.Baseline);
```

## Step 5: Adjusting Task Start and Stop Dates
वैरिएंस परिदृश्य का सिमुलेशन करने के लिए टास्क की प्रारंभ और समाप्ति तिथियों को संशोधित करें।

```java
cal.set(2013, Calendar.NOVEMBER, 29, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2013, Calendar.NOVEMBER, 27, 8, 0, 0);
task.set(Tsk.STOP, cal.getTime());
```

*अपने प्रोजेक्ट की विशिष्ट आवश्यकताओं के अनुसार तिथियों और अवधियों को बदलने के लिए स्वतंत्र महसूस करें।*

## Common Issues & Tips
- **बेसलाइन को तिथियों को समायोजित करने से पहले सेट करना आवश्यक है।** यदि आप पहले तिथियों को बदलते हैं, तो बेसलाइन बदली हुई शेड्यूल को कैप्चर करेगी, न कि मूल योजना को।  
- **कैलेंडर महीने शून्य‑आधारित होते हैं।** याद रखें कि `Calendar.FEBRUARY` महीने 1 के बराबर है, न कि 2।  
- **अवधि इकाइयाँ:** `project.getDuration(2)` डिफ़ॉल्ट रूप से दो दिनों की अवधि बनाता है; यदि आपको घंटे या हफ्ते चाहिए तो इकाई को समायोजित करें।

## Conclusion
**set project start date**, **set task duration**, और **manage project variances** को महारत हासिल करके आप Aspose.Tasks for Java का उपयोग करके अपने प्रोजेक्ट शेड्यूल पर पूर्ण नियंत्रण प्राप्त करते हैं। ऊपर दिए गए चरण एक ठोस आधार प्रदान करते हैं जिसे आप मल्टी‑फेज प्रोजेक्ट्स, रिसोर्स एलोकेशन, और ऑटोमेटेड रिपोर्टिंग जैसे अधिक जटिल परिदृश्यों में विस्तारित कर सकते हैं।

## Frequently Asked Questions
### क्या Aspose.Tasks सभी प्रोजेक्ट मैनेजमेंट आवश्यकताओं के लिए उपयुक्त है?
Aspose.Tasks एक बहुमुखी टूल है जो विभिन्न प्रोजेक्ट मैनेजमेंट आवश्यकताओं को पूरा करता है, लचीलापन और मजबूत फीचर सेट प्रदान करता है।

### क्या मैं Aspose.Tasks को अपने मौजूदा Java प्रोजेक्ट में इंटीग्रेट कर सकता हूँ?
हाँ, आप प्रदान की गई डॉक्यूमेंटेशन **[here](https://reference.aspose.com/tasks/java/)** का पालन करके Aspose.Tasks को अपने Java प्रोजेक्ट में आसानी से इंटीग्रेट कर सकते हैं।

### क्या Aspose.Tasks के लिए एक टेम्पररी लाइसेंस उपलब्ध है?
हाँ, आप Aspose.Tasks के लिए टेम्पररी लाइसेंस **[here](https://purchase.aspose.com/temporary-license/)** से प्राप्त कर सकते हैं।

### Aspose.Tasks के लिए सपोर्ट कहाँ प्राप्त कर सकता हूँ?
सपोर्ट और चर्चा के लिए Aspose.Tasks फ़ोरम **[here](https://forum.aspose.com/c/tasks/15)** पर जाएँ।

### क्या मैं Aspose.Tasks for Java डाउनलोड कर सकता हूँ?
हाँ, Aspose.Tasks for Java का नवीनतम संस्करण **[here](https://releases.aspose.com/tasks/java/)** से डाउनलोड करें।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2026-02-20  
**परीक्षण किया गया:** Aspose.Tasks नवीनतम Java रिलीज़  
**लेखक:** Aspose