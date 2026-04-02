---
date: 2026-01-31
description: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट कैलेंडर बनाना, छुट्टी कैलेंडर
  जोड़ना, और प्रोजेक्ट XML निर्यात करना सीखें।
linktitle: Add Calendar to Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java के साथ प्रोजेक्ट कैलेंडर कैसे बनाएं
url: /hi/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java के साथ प्रोजेक्ट कैलेंडर कैसे बनाएं

## Introduction
आधुनिक प्रोजेक्ट‑मैनेजमेंट वर्कफ़्लो में, प्रप्रोजेक्ट कैलेंडर** बनाने की। Aspose.Tasks for Java डेवलपर्स को एक साफ़, टाइप‑सेफ़ API प्रदान करता है जिससे आप Microsoft Project फ़ाइलों को डेस्कटॉप क्लाइंट खोले बिना ही मैनीपुलेट कर सकते हैं। इस ट्यूटोरियल में आप सीखेंगे **कैसे कैलेंडर जोड़ें**, **MS Project कैलेंडर कैसे बनाएं**, और **प्रोजेक्ट XML एक्सपोर्ट करें**—सिर्फ कुछ ही लाइनों के Java कोड से।

## Quick Answers
- **“create project calendar” का क्या मतलब है?**  
  इसका अर्थ है कोड के माध्यम से Microsoft Project फ़ाइल के भीतर एक नया कार्य‑समय परिभाषा (कैलेंडर) बनाना।  
- **यह कौन सी लाइब्रेरी संभालती है?**  
  Aspose.Tasks for Java `Calendar` क्लास और `Project` कंटेनर प्रदान करता है जिससे कैलेंडर मैनेज किए जा सकते हैं।  
- **क्या मुझे लाइसेंस चाहिए?**  
  परीक्षण के लिए एक अस्थायी इवैल्यूएशन लाइसेंस काम करता है; प्रोडक्शन उपयोग के लिए पूर्ण लाइसेंस आवश्यक है  
  हाँ—`SaveFileFormat.Xml` का उपयोगाइल के रूप में एक्सपोर्ट करें।  
- **पूर्वापेक्षाएँ क्या हैं?**  
  Java JDK 8+ और आपके What is “create project calendar”?
प्रोजेक्ट कैलेंडर बनाना प्रोजेक्ट के लिए कार्य दिवस, छुट्टियों और दैनिक कार्य घंटे निर्धारित करता है। एक बार कैलेंडर को टास्क, रिसोर्स या पूरे प्रोजेक्ट से जोड़ दिया जाता है, सभी शेड्यूलिंग गणनाएँ परिभाषित कार्य समय का सम्मान करती हैं।

## Why use create project calendar?
- **Full control** – UI के बिना कई प्रोजेक्ट्स में बड़े पैमाने पर कैलेंडर निर्माण को ऑटोमेट करें।  
- **Cross‑version, 2013, 2016 और बाद की फ़ाइलों के साथ काम करता है।  
- **No Microsoft Project installation** – किसी भी सर्वर या CI पाइपलाइन पर चलाएँ।  
- **Export flexibility** – XML, MPP या अन्य समर्थित फ़ॉर्मैट में सेव करें।

## Prerequisites
- **Java Development Kit (JDK) 8 या नया** for Java** लाइब्रेरी – [official website](https://releases.aspose.com/tasks/java/) से डाउनलोड करें और JAR को अपने प्रोजेक्ट के क्लासपाथ में जोड़ें।  
- आपका पसंदीदा IDE या बिल्ड टूल (Maven/Gradle)।

## Step‑by‑step guide

### Step 1: Import the required Aspose.Tasks package
पहले Aspose.Tasks क्लासेस को स्कोप में लाएँ ताकि आप प्रोजेक्ट्स और कैलेंडरों के साथ काम कर सकें।

```java
import com.aspose.tasks.*;
```

### Step 2: Set the data directory path
निर्धारित करें कि जेनरेटेड प्रोजेक्ट फ़ाइल कहाँ लिखी जाएगी। प्लेसहोल्डर को अपने मशीन पर एक एब्सॉल्यूट या रिलेटिव पाथ से बदलें।

```java
String dataDir = "Your Data Directory";
```

### Step 3: Create a new Project instance
एक `Project` ऑब्जेक्ट इंस्टैंशिएट करें – यह एक खाली Microsoft Project फ़ाइल का प्रतिनिधित्व करता है जिसे आप भर सकते हैं।

```java
Project prj = new Project();
```

### Step 4: Define the calendars you want to add
`Calendars.add(String name)` मेथड का उपयोग करके नए कैलेंडर एंट्री बनाएँ। इस उदाहरण में हम तीन कैलेंडर जोड़ते हैं, लेकिन आप जितने चाहें जोड़ सकते हैं और बाद में उनके कार्य समय को कॉन्फ़िगर कर सकते हैं।

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Pro tip:** कैलेंडर जोड़ने के बाद, आप `cal1.getWeekDays().add(...)` से उसके कार्य दिवस कस्टमाइज़ कर सकते हैं और `cal1.getBaseCalendar().setWorkingTime(...)` से दैनिक कार्य घंटे सेट कर सकते हैं।

### Step 5: Save the project (export project XML)
प्रोजेक्ट को, जिसमें नए जोड़े गए कैलेंडर शामिल हैं, एक टूल्स के साथ संगत है।

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Step 6: Display a completion message
उपयोगकर्ता को बताएं कि ऑपरेशन सफलतापूर्वक समाप्त हो गया है।

```java
System.out.println("Process completed Successfully");
```

इन छह संक्षिप्त चरणों का पालन करके, आपने सफलतापूर्वक **प्राइल में जोड़ा, और **प्रोजेक्ट को XML के रूप में एक्सपोर्ट किया**।

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **`NullPointerException` on `prj.getCalendars()`** | प्रोजेक्ट ऑब्जेक्ट सही तरीके से इनिशियलाइज़ नहीं हुआ। | कैलेंडर एक्सेस करने से पहले `new Project()` को कॉल करें। |
| **File not found when saving** | `dataDir` एक गैर‑मौजूद फ़ोल्डर की ओर इशारा कर रहारी बनाएं या एब्सॉल्यूट पाथ का उपयोग करें। |
| **Calendar name appears as “no info”** | सैंपल में प्लेसहोल्डर नाम उपयोग किए गए थे। | ऐसे अर्थपूर्ण नाम रखें जो शेड्यूल को दर्शाते हों (जैसे, “US Holiday Calendar”)। |
| **Saved XML cannot be opened in MS Project.Tasks for Java रिलीज़ में अपडेट करें। |

## Frequently Asked Questions

**Q: क्या Aspose.Tasks जटिल कैलेंडर को कई एक्सेप्शन के साथ संभाल सकता है?**  
A: हाँ – कैलेंडर जोड़ने के बाद आप `WeekDay` और `Exception` क्लासेस का उपयोग करके एक्सेप्शन, कार्य घंटे और गैर‑कार्य दिवस परिभाषित कर सकते हैं।

**Q: क्या नया कैलेंडर विशेष टास्क्स को। `prj.getRootTask().getChildren().add("Task Name")` से टास्क प्राप्त करें और `task.set(Tsk.CALENDAR, cal3);` सेट करें।

**Q: क्या लाइब्रेरी MPP जैसे अन्य फ़ॉर्मैट में सेव करने का समर्थन करती है?**  
A: हाँ। `SaveFileFormat.Xml` को `SaveFileFormat.Mpp` या `SaveFileFormat.P6` से बदलें।

**Q: क्या विकास बिल्ड्स के लिए लाइसेंस चाहिए?**  
A: परीक्षण के लिए अस्थायी इवैल्यूएशन लाइसेंस पर्याप्त है; प्रोडक्शन डिप्लॉयमेंट के लिए पूर्ण लाइसेंस आवश्यक है।

**्युनिटी फ़ोरम एक उत्कृष्ट संसाधन है: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)।

## Conclusion
Aspose.Tasks for Java का उपयोग करके आप प्रोग्रामेटिक रूप से **प्रोजेक्ट कैलेंडर बना** सकते हैं, शेड्यूलिंग नियमों को कस्टमाइज़ कर सकते हैं, सकते हैं, वह भी कुछ ही लाइनों के कोड से। यह ऑटोमेशन मैन्युअल प्रयास को कम करता है, मानव त्रुटियों को समाप्त करता है, और बड़े प्रोजेक्ट पोर्टफ़ोलियो की बैच प्रोसेसिंग को सक्षम बनाता है।

---

01-31  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}