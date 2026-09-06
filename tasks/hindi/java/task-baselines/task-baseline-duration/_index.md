---
date: 2026-08-29
description: Aspose.Tasks for Java का उपयोग करके baseline duration को सेट करना और
  project progress को ट्रैक करना सीखें। यह step‑by‑step गाइड आपको task baselines को
  प्रभावी ढंग से प्रबंधित करने में मदद करता है।
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: Aspose.Tasks for Java में Baseline Duration कैसे सेट करें
og_description: Aspose.Tasks for Java का उपयोग करके baseline duration को सेट करना
  और project progress को ट्रैक करना सीखें। task baselines को प्रभावी ढंग से प्रबंधित
  करने के लिए इस विस्तृत गाइड का पालन करें।
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: baseline duration को सेट करके project progress को ट्रैक करने का तरीका
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: baseline duration को सेट करके project progress को ट्रैक करने का तरीका
url: /hi/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# प्रोजेक्ट प्रगति को ट्रैक करने के लिए बेसलाइन अवधि कैसे सेट करें

## परिचय
प्रोजेक्ट की प्रगति को ट्रैक करना एक ठोस बेसलाइन से शुरू होता है। इस ट्यूटोरियल में आप Microsoft Project फ़ाइलों में कार्यों के लिए Aspose.Tasks लाइब्रेरी (Java) का उपयोग करके **how to set baseline duration** कैसे सेट करें, यह जानेंगे, और समझेंगे कि प्रारंभ में बेसलाइन स्थापित करने से आप शेड्यूल ड्रिफ्ट, लागत में अंतर, और संसाधन ओवरएलोकेशन को प्रोजेक्ट के पूरे जीवनकाल में मॉनिटर कर सकते हैं।

## त्वरित उत्तर
- **“set baseline” क्या मतलब है?** यह एक कार्य की मूल प्रारंभ, समाप्ति, और अवधि को रिकॉर्ड करता है ताकि आप भविष्य में होने वाले बदलावों की तुलना कर सकें।  
- **कौन सा Aspose.Tasks क्लास प्रोजेक्ट बनाता है?** `Project` क्लास – आप यह भी सीखेंगे कि **create a project instance** सही ढंग से कैसे किया जाए।  
- **कोड चलाने के लिए मुझे लाइसेंस चाहिए?** टेस्टिंग के लिए एक मुफ्त इवैल्यूएशन लाइसेंस काम करता है; प्रोडक्शन के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **क्या मैं इंटरिम बेसलाइन प्राप्त कर सकता हूँ?** हां, Aspose.Tasks आपको इंटरिम बेसलाइन और उनके फिक्स्ड कॉस्ट को क्वेरी करने की अनुमति देता है।  
- **कौन सा Java संस्करण आवश्यक है?** Java 8 या बाद का संस्करण अनुशंसित है।  
- **यह प्रोजेक्ट प्रगति को ट्रैक करने में कैसे मदद करता है?** एक बार बेसलाइन सेट हो जाने पर, आप बिल्ट‑इन रिपोर्टिंग फीचर्स का उपयोग करके वास्तविक तिथियों की मूल योजना से तुरंत तुलना कर सकते हैं।

## कार्य बेसलाइन क्या है और इसे क्यों सेट करें?
एक कार्य बेसलाइन एक विशिष्ट समय बिंदु पर नियोजित शेड्यूल (प्रारंभ तिथि, समाप्ति तिथि, और अवधि) को कैप्चर करती है। बेसलाइन सेट करके आप एक रेफ़रेंस पॉइंट बनाते हैं जिससे प्रोजेक्ट के विकसित होने पर शेड्यूल ड्रिफ्ट, लागत अधिकता, और संसाधन ओवरएलोकेशन को आसानी से पहचाना जा सके।

## बेसलाइन प्रबंधन के लिए Aspose.Tasks क्यों उपयोग करें?
Aspose.Tasks **पूर्ण .mpp संगतता** प्रदान करता है – आप Microsoft Office स्थापित किए बिना मूल Microsoft Project फ़ाइलों को पढ़ और लिख सकते हैं। API आपको **50+ इनपुट और आउटपुट फ़ॉर्मेट** तक प्रोग्रामेटिक एक्सेस देता है, **इंटरिम बेसलाइन 1‑10** को सपोर्ट करता है, और **सैकड़ों पृष्ठों वाले प्रोजेक्ट** को पूरी फ़ाइल को मेमोरी में लोड किए बिना संभाल सकता है, जो हाई‑परफ़ॉर्मेंस बैच प्रोसेसिंग के लिए आवश्यक है।

## पूर्वापेक्षाएँ
1. **Java Development Environment** – JDK 8+ स्थापित और कॉन्फ़िगर किया हुआ।  
2. **Aspose.Tasks for Java** – लाइब्रेरी को [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. **IDE या बिल्ड टूल** – Maven, Gradle, या कोई भी IDE जो आप पसंद करते हैं।

## पैकेज इम्पोर्ट करें
निम्नलिखित इम्पोर्ट्स उन कोर Aspose.Tasks क्लासेज़ को लाते हैं जो प्रोजेक्ट्स, टास्क, बेसलाइन, और टाइम‑फ़ेज़्ड डेटा के साथ काम करने के लिए आवश्यक हैं।

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## चरण 1: प्रोजेक्ट इंस्टेंस बनाएं
`Project` क्लास मेमोरी में एक Microsoft Project फ़ाइल का प्रतिनिधित्व करता है और सभी ऑपरेशन्स के लिए एंट्री पॉइंट है।

```java
Project project = new Project();
```

## चरण 2: टास्क बेसलाइन बनाएं
`TaskBaseline` एक विशिष्ट टास्क के लिए नियोजित प्रारंभ, समाप्ति, और अवधि को संग्रहीत करता है।

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## चरण 3: टास्क बेसलाइन जानकारी प्रदर्शित करें
`getBaselines()` मेथड टास्क से जुड़ी बेसलाइन की कलेक्शन लौटाता है।

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## चरण 4: इंटरिम बेसलाइन और फिक्स्ड कॉस्ट जांचें
`BaselineType` प्राथमिक और इंटरिम बेसलाइन (Baseline, Baseline1‑Baseline10) को एनेमरेट करता है।

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## चरण 5: टाइम‑फ़ेज़्ड डेटा प्रिंट करें
`TimephasedData` एक विशिष्ट समय अंतराल के लिए शेड्यूल जानकारी का एक भाग दर्शाता है।

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

इन चरणों का पालन करके, आप किसी भी टास्क के लिए **set baseline duration** सेट कर सकते हैं और Aspose.Tasks for Java का उपयोग करके विस्तृत बेसलाइन जानकारी प्राप्त कर सकते हैं, जो आपको प्रोजेक्ट लाइफ़साइकल के दौरान **track project progress** करने का एक विश्वसनीय तरीका प्रदान करता है।

## सामान्य समस्याएँ और समाधान
- **Baseline MS Project में नहीं दिख रहा है:** `project.setBaseline(BaselineType.Baseline)` को टास्क जोड़ने के **बाद** कॉल किया है, यह सुनिश्चित करें।  
- **`getBaselines()` पर NullPointerException:** बेसलाइन सेट करने से पहले यह सुनिश्चित करें कि टास्क प्रोजेक्ट में जोड़ा गया था।  
- **Time unit mismatch:** ड्यूरेशन को सही ढंग से फॉर्मेट करने के लिए `TimeUnitType` का उपयोग करें, विशेष रूप से कस्टम कैलेंडर के साथ काम करते समय।

## अक्सर पूछे जाने वाले प्रश्न
### MS Project में टास्क बेसलाइन क्या है?
MS Project में टास्क बेसलाइन एक टास्क के प्रारंभिक नियोजित शेड्यूल का स्नैपशॉट है, जिसमें उसकी प्रारंभ तिथि, समाप्ति तिथि, और अवधि शामिल होती है।

### टास्क बेसलाइन का प्रबंधन क्यों महत्वपूर्ण है?
टास्क बेसलाइन का प्रबंधन नियोजित शेड्यूल की वास्तविक प्रोजेक्ट प्रगति से तुलना करने में मदद करता है, जिससे बेहतर ट्रैकिंग और निर्णय‑लेने की प्रक्रिया आसान होती है।

### एक बार सेट होने के बाद क्या मैं टास्क बेसलाइन को संशोधित कर सकता हूँ?
हां, आप प्रोजेक्ट योजना में बदलाव को दर्शाने के लिए MS Project में टास्क बेसलाइन को संशोधित कर सकते हैं। हालांकि, मूल बेसलाइन से किसी भी विचलन को दस्तावेज़ित करना आवश्यक है।

### क्या Aspose.Tasks अन्य प्रोजेक्ट मैनेजमेंट कार्यात्मकताओं का समर्थन करता है?
हां, Aspose.Tasks प्रोजेक्ट मैनेजमेंट के लिए विभिन्न सुविधाएँ प्रदान करता है, जिसमें टास्क शेड्यूलिंग, रिसोर्स अलोकेशन, और गैंट चार्ट जेनरेशन शामिल हैं।

### Aspose.Tasks के लिए समर्थन कहाँ मिल सकता है?
आप Aspose.Tasks के समर्थन को [Aspose.Tasks फोरम](https://forum.aspose.com/c/tasks/15) पर पा सकते हैं, जहाँ आप प्रश्न पूछ सकते हैं और अन्य उपयोगकर्ताओं के साथ इंटरैक्ट कर सकते हैं।

## अतिरिक्त अक्सर पूछे जाने वाले प्रश्न
**Q: क्या मुझे प्रत्येक टास्क के लिए अलग-अलग `setBaseline` कॉल करना पड़ेगा?**  
A: नहीं। `project.setBaseline(BaselineType.Baseline)` को कॉल करने से प्रोजेक्ट के सभी टास्क के लिए एक साथ बेसलाइन रिकॉर्ड हो जाता है।

**Q: किसी विशिष्ट टास्क के लिए इंटरिम बेसलाइन कैसे सेट करूँ?**  
A: `project.setBaseline(BaselineType.Baseline1)` (या Baseline2‑Baseline10) का उपयोग करें, टास्क के शेड्यूल को अपडेट करने के बाद।

**Q: क्या बेसलाइन डेटा को CSV में एक्सपोर्ट करना संभव है?**  
A: हां। `task.getBaselines()` पर इटरेट करें और मानक Java I/O का उपयोग करके इच्छित फ़ील्ड को CSV फ़ाइल में लिखें।

**Q: क्या मैं मौजूदा .mpp फ़ाइल पढ़ सकता हूँ जिसमें पहले से बेसलाइन मौजूद हैं?**  
A: बिल्कुल। फ़ाइल को `new Project("myproject.mpp")` से लोड करें और फिर ऊपर दिखाए अनुसार प्रत्येक टास्क की बेसलाइन तक पहुँचें।

**Q: क्या Aspose.Tasks मल्टी‑प्रोजेक्ट फ़ाइलों को संभालता है?**  
A: Aspose.Tasks सिंगल‑प्रोजेक्ट .mpp फ़ाइलों के साथ काम करता है। मल्टी‑प्रोजेक्ट परिदृश्यों के लिए, प्रोग्रामेटिक रूप से प्रोजेक्ट्स को संयोजित करें।

---

**अंतिम अपडेट:** 2026-08-29  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [टास्क लिस्ट जावा बनाएं – Aspose.Tasks का उपयोग करके MS Project बेसलाइन](/tasks/java/task-baselines/create-task-baseline/)
- [MPP प्रोजेक्ट जावा बनाएं – Aspose.Tasks के साथ टास्क प्रोग्रेस बदलें](/tasks/java/task-properties/change-progress/)
- [प्रोजेक्ट मैनेजमेंट बेसलाइन – Aspose.Tasks के साथ टास्क शेड्यूलिंग](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}