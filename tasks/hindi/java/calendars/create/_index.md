---
date: 2026-08-03
description: Aspose.Tasks for Java का उपयोग करके MS Project कैलेंडर बनाना, प्रोजेक्ट
  में कैलेंडर जोड़ना, और प्रोजेक्ट को XML के रूप में सहेजना सीखें।
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: Aspose.Tasks का उपयोग करके प्रोजेक्ट में कैलेंडर जोड़ें
og_description: Aspose.Tasks for Java का उपयोग करके प्रोग्रामेटिक रूप से MS Project
  कैलेंडर बनाएं। कैलेंडर जोड़ें, शेड्यूल को कस्टमाइज़ करें, और मिनटों में XML में
  निर्यात करें।
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: Aspose.Tasks for Java के साथ MS Project कैलेंडर बनाएं
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: Aspose.Tasks for Java के साथ MS Project कैलेंडर बनाएं
url: /hi/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java के साथ ms project कैलेंडर बनाएं

## परिचय
आधुनिक प्रोजेक्ट‑मैनेजमेंट वर्कफ़्लोज़ में, प्रोग्रामेटिक रूप से **create ms project calendar** करने की क्षमता मैन्युअल एडिटिंग में घंटों की बचत कर सकती है। Aspose.Tasks for Java आपको एक साफ़, टाइप‑सेफ़ API प्रदान करता है जिससे आप Microsoft Project फ़ाइलों को डेस्कटॉप क्लाइंट खोले बिना ही हेर-फेर कर सकते हैं। इस ट्यूटोरियल में आप सीखेंगे कि कैलेंडर कैसे जोड़ें, MS Project कैलेंडर कैसे बनाएं, और प्रोजेक्ट को XML के रूप में कैसे सहेजें—सिर्फ कुछ ही लाइनों के Java कोड के साथ।

## त्वरित उत्तर
- **“create ms project calendar” क्या मतलब है?**  
  इसका मतलब है कि कोड के माध्यम से Microsoft Project फ़ाइल में एक नया कार्य‑समय परिभाषा (कैलेंडर) सम्मिलित करना।  
- **यह कौन सी लाइब्रेरी संभालती है?**  
  Aspose.Tasks for Java `Calendar` क्लास और `Project` कंटेनर प्रदान करता है जिससे कैलेंडर प्रबंधित किए जा सकते हैं।  
- **क्या मुझे लाइसेंस चाहिए?**  
  टेस्टिंग के लिए एक अस्थायी इवैल्यूएशन लाइसेंस काम करता है; प्रोडक्शन उपयोग के लिए पूर्ण लाइसेंस आवश्यक है।  
- **क्या मैं फ़ाइल को XML के रूप में सहेज सकता हूँ?**  
  हाँ—`SaveFileFormat.Xml` का उपयोग करके प्रोजेक्ट को XML फ़ाइल के रूप में एक्सपोर्ट करें।  
- **पूर्वापेक्षाएँ क्या हैं?**  
  Java JDK 8+ और आपके क्लासपाथ पर Aspose.Tasks for Java JAR।  

## create ms project calendar क्या है?
MS Project कैलेंडर बनाना मतलब प्रोग्रामेटिक रूप से एक नई कैलेंडर परिभाषा को प्रोजेक्ट फ़ाइल में जोड़ना है, जिसमें कार्य दिवस, अपवाद, और दैनिक कार्य घंटे निर्दिष्ट किए जाते हैं, फिर उस कैलेंडर को टास्क, रिसोर्सेज, या पूरे प्रोजेक्ट को असाइन किया जाता है ताकि शेड्यूल गणनाएँ परिभाषित कार्य समय का सम्मान करें।

## प्रोजेक्ट में कैलेंडर जोड़ने के लिए Aspose.Tasks for Java का उपयोग क्यों करें?
आपको Aspose.Tasks for Java का उपयोग करना चाहिए क्योंकि यह एक पूरी तरह टाइप‑सेफ़ API प्रदान करता है जो Microsoft Project स्थापित किए बिना काम करता है, सभी प्रमुख प्रोजेक्ट संस्करणों (2007‑2021, 5+ रिलीज़) का समर्थन करता है, और XML, MPP, और **10+** अन्य फ़ॉर्मेट्स में एक्सपोर्ट कर सकता है, जिससे किसी भी सर्वर पर स्वचालित बुल्क कैलेंडर निर्माण संभव हो जाता है।

## पूर्वापेक्षाएँ
- **Java Development Kit (JDK) 8 या नया** स्थापित और कॉन्फ़िगर किया हुआ।  
- **Aspose.Tasks for Java** लाइब्रेरी – [official website](https://releases.aspose.com/tasks/java/) से डाउनलोड करें और JAR को अपने प्रोजेक्ट के क्लासपाथ में जोड़ें।  
- अपनी पसंद का IDE या बिल्ड टूल (Maven/Gradle)।

## स्टेप‑बाय‑स्टेप गाइड

### स्टेप 1: आवश्यक Aspose.Tasks पैकेज इम्पोर्ट करें
पहले, Aspose.Tasks क्लासेस को स्कोप में लाएँ ताकि आप प्रोजेक्ट्स और कैलेंडर के साथ काम कर सकें।

```java
import com.aspose.tasks.*;
```

### स्टेप 2: डेटा डायरेक्टरी पाथ सेट करें
परिभाषित करें कि जेनरेटेड प्रोजेक्ट फ़ाइल कहाँ लिखी जाएगी। प्लेसहोल्डर को अपने मशीन पर एक एब्सोल्यूट या रिलेटिव पाथ से बदलें।

```java
String dataDir = "Your Data Directory";
```

### स्टेप 3: नया Project इंस्टेंस बनाएं
`Project` वह कोर क्लास है जो मेमोरी में Microsoft Project फ़ाइल का प्रतिनिधित्व करता है।

```java
Project prj = new Project();
```

### स्टेप 4: वह कैलेंडर परिभाषित करें जिन्हें आप जोड़ना चाहते हैं
`Calendar` एक शेड्यूल को परिभाषित करता है जिसमें कार्य दिवस, अपवाद, और प्रोजेक्ट के लिए कार्य समय शामिल होते हैं।

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Pro tip:** कैलेंडर जोड़ने के बाद, आप `cal1.getWeekDays().add(...)` से उसके कार्य दिवस कस्टमाइज़ कर सकते हैं और `cal1.getBaseCalendar().setWorkingTime(...)` से दैनिक कार्य घंटे सेट कर सकते हैं।

### स्टेप 5: प्रोजेक्ट सहेजें (प्रोजेक्ट को XML के रूप में सहेजें)
`SaveFileFormat.Xml` Aspose.Tasks को बताता है कि प्रोजेक्ट को XML फ़ॉर्मेट में लिखें।

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### स्टेप 6: पूर्णता संदेश दिखाएँ
उपयोगकर्ता को बताएं कि ऑपरेशन सफलतापूर्वक समाप्त हो गया है।

```java
System.out.println("Process completed Successfully");
```

इन छह संक्षिप्त चरणों का पालन करके, आपने सफलतापूर्वक **added a calendar to a project** किया और परिणाम को XML फ़ाइल के रूप में सहेजा।

## सामान्य समस्याएँ और समाधान
| Issue | Reason | Fix |
|-------|--------|-----|
| **`NullPointerException` on `prj.getCalendars()`** | प्रोजेक्ट ऑब्जेक्ट सही ढंग से इनिशियलाइज़ नहीं किया गया है। | कैलेंडर तक पहुंचने से पहले `new Project()` को कॉल किया गया है, यह सुनिश्चित करें। |
| **फ़ाइल सहेजते समय नहीं मिली** | `dataDir` एक गैर‑मौजूद फ़ोल्डर की ओर इशारा करता है। | पहले डायरेक्टरी बनाएं या एब्सोल्यूट पाथ का उपयोग करें। |
| **कैलेंडर नाम “no info” दिखा रहा है** | सैंपल में प्लेसहोल्डर नाम उपयोग किए गए थे। | शेड्यूल को दर्शाने वाले सार्थक नामों से बदलें (जैसे, “US Holiday Calendar”). |
| **सहेजा गया XML MS Project में नहीं खुल रहा** | पुराने Aspose.Tasks संस्करण का उपयोग किया जा रहा है। | नवीनतम Aspose.Tasks for Java रिलीज़ में अपडेट करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.Tasks कई अपवादों वाले जटिल कैलेंडर को संभाल सकता है?**  
A: हाँ – कैलेंडर जोड़ने के बाद आप `WeekDay` और `Exception` क्लासेज़ का उपयोग करके अपवाद, कार्य घंटे, और गैर‑कार्य दिवस परिभाषित कर सकते हैं।

**Q: क्या नया कैलेंडर विशिष्ट टास्क को असाइन करना संभव है?**  
A: बिल्कुल। `prj.getRootTask().getChildren().add("Task Name")` के माध्यम से टास्क प्राप्त करें और `task.set(Tsk.CALENDAR, cal3);` सेट करें।

**Q: क्या लाइब्रेरी MPP जैसे अन्य फ़ॉर्मेट्स में सहेजने का समर्थन करती है?**  
A: हाँ। आवश्यकतानुसार `SaveFileFormat.Xml` को `SaveFileFormat.Mpp` या `SaveFileFormat.P6` से बदलें; Aspose.Tasks **12** आउटपुट फ़ॉर्मेट्स का समर्थन करता है।

**Q: क्या विकास बिल्ड्स के लिए मुझे लाइसेंस चाहिए?**  
A: टेस्टिंग के लिए एक अस्थायी इवैल्यूएशन लाइसेंस पर्याप्त है; प्रोडक्शन डिप्लॉयमेंट के लिए पूर्ण लाइसेंस आवश्यक है।

**Q: यदि मुझे समस्याएँ आती हैं तो मैं मदद कहाँ से प्राप्त कर सकता हूँ?**  
A: Aspose.Tasks कम्युनिटी फ़ोरम एक उत्कृष्ट संसाधन है: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**अंतिम अपडेट:** 2026-08-03  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12 (लेखन समय पर नवीनतम)  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [MS Project कैलेंडर में सप्ताह के दिन कैसे परिभाषित करें – Aspose.Tasks Java](/tasks/java/calendars/)
- [Aspose.Tasks के साथ प्रोजेक्ट कैलेंडर Java कैसे सेट करें](/tasks/java/calendars/properties/)
- [Aspose.Tasks for Java के साथ कस्टम कैलेंडर अपवाद बनाएं](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}