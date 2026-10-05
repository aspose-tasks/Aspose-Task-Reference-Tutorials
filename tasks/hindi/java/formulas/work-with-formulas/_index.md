---
date: 2026-10-05
description: Learn how to create test project और dates के बीच दिनों की गणना करने के
  लिए Aspose.Tasks for Java का उपयोग करें, एक custom field जोड़ें, और MPP फ़ाइलों
  को कुशलतापूर्वक manipulate करें.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Aspose.Tasks में formulas के साथ काम करें
og_description: Create test project और dates के बीच दिनों की गणना करने के लिए Aspose.Tasks
  for Java का उपयोग करें। यह गाइड दिखाता है कि कैसे एक custom field जोड़ें, task deadlines
  सेट करें, और प्रोजेक्ट को MPP फ़ाइल के रूप में save करें.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: Create test project और dates के बीच दिनों की गणना करें
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: Create test project और dates के बीच दिनों की गणना करें
url: /hi/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# टेस्ट प्रोजेक्ट बनाएं और तिथियों के बीच दिनों की गणना करें

इस ट्यूटोरियल में आप **टेस्ट प्रोजेक्ट बनाएँगे** और **तिथियों के बीच दिनों की गणना करेंगे** एक कस्टम फ़ील्ड जोड़कर, एक विस्तारित एट्रिब्यूट परिभाषित करके, और Aspose.Tasks लाइब्रेरी फॉर जावा के माध्यम से एक Microsoft Project फ़ॉर्मूला लागू करके। चाहे आपको शेड्यूल बनाना हो, डेडलाइन की गणना करनी हो, या रिपोर्टिंग को स्वचालित करना हो, Aspose.Tasks आपको डेस्कटॉप इंस्टॉलेशन के बिना प्रोग्रामेटिकली प्रोजेक्ट डेटा को मैनीपुलेट करने देता है, 50+ इनपुट और आउटपुट फॉर्मैट्स को सपोर्ट करता है और मेमोरी‑इफ़िशिएंट मोड में कई‑सौ‑पेज फ़ाइलों को संभालता है।

## त्वरित उत्तर

- **ट्यूटोरियल क्या कवर करता है?** यह दिखाता है कि कैसे एक टेस्ट प्रोजेक्ट बनाएं, एक विस्तारित एट्रिब्यूट परिभाषित करें, टास्क की डेडलाइन सेट करें, और तिथियों के बीच दिनों की गणना करने के लिए फ़ॉर्मूला का उपयोग करें।  
- **कौनसी लाइब्रेरी आवश्यक है?** Aspose.Tasks for Java (नवीनतम संस्करण)।  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए एक फ्री ट्रायल काम करता है; उत्पादन उपयोग के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **मैं कौन सा IDE उपयोग कर सकता हूँ?** कोई भी Java IDE (IntelliJ IDEA, Eclipse, VS Code) जो JDK 8+ को सपोर्ट करता है।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** कोड को कॉपी करने और चलाने में लगभग 10‑15 मिनट।

## Aspose.Tasks में “तिथियों के बीच दिनों की गणना” क्या है?

Aspose.Tasks में, एक फ़ॉर्मूला एक स्ट्रिंग है जो टास्क फ़ील्ड्स को रेफ़र कर सकती है और गणनाएँ कर सकती है। `[Deadline] - [Finish]` वह फ़ॉर्मूला सिंटैक्स है जिसका उपयोग Aspose.Tasks दो तिथि फ़ील्ड्स के बीच दिनों में संख्यात्मक अंतर लौटाने के लिए करता है। परिणाम को एक संख्यात्मक मान के रूप में संग्रहीत किया जाता है जो पूरे दिनों का प्रतिनिधित्व करता है, जिसे आप कस्टम फ़ील्ड में दिखा सकते हैं या आगे की गणनाओं में उपयोग कर सकते हैं।

## तिथियों के बीच दिनों की गणना के लिए Aspose.Tasks क्यों उपयोग करें?

Aspose.Tasks हर प्रोजेक्ट, टास्क, और रिसोर्स प्रॉपर्टी के लिए **पूर्ण API कवरेज** प्रदान करता है, Windows, Linux, और macOS पर चलता है, और **Microsoft Project या Office की आवश्यकता नहीं** होती है। यह इंजन सामान्य सर्वर हार्डवेयर पर एक सेकंड से कम समय में **500+ टास्क** वाले प्रोजेक्ट्स को प्रोसेस कर सकता है, जिससे यह CI पाइपलाइन्स, Docker कंटेनर्स, और हाई‑वॉल्यूम बैच प्रोसेसिंग के लिए आदर्श बनता है।

## टास्क के लिए डेडलाइन कैसे सेट करें

`java.util.Calendar` एक Java क्लास है जो समय के एक विशिष्ट क्षण को दर्शाता है। आप एक डेडलाइन सेट करते हैं `java.util.Calendar` मान को टास्क के `Tsk.DEADLINE` फ़ील्ड को असाइन करके। Calendar इंस्टेंस बनाने के बाद, उसका वर्ष, माह, और दिन इच्छित डेडलाइन पर सेट करें, फिर `task.set(Tsk.DEADLINE, calendar);` कॉल करें। डेडलाइन प्रोजेक्ट फ़ाइल में संग्रहीत होती है और इसे फ़ॉर्मूलों जैसे `[Deadline] - [Finish]` में उपयोग किया जा सकता है।

## विस्तारित एट्रिब्यूट कैसे परिभाषित करें

एक विस्तारित एट्रिब्यूट एक कस्टम फ़ील्ड है जो आपके फ़ॉर्मूला का परिणाम संग्रहीत करता है। आप इसे एक बार बनाते हैं, इसे एक उपयोगी उपनाम देते हैं, और `[Deadline] - [Finish]` अभिव्यक्ति संलग्न करते हैं ताकि हर टास्क स्वचालित रूप से अंतर की गणना कर सके। इसे `ExtendedAttribute` को इंस्टैंसिएट करके, उसका Alias सेट करके, फ़ॉर्मूला असाइन करके, और प्रोजेक्ट के कलेक्शन में जोड़कर बनाएं।

## पूर्वापेक्षाएँ

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- **Java Development Kit (JDK) 8+** – Oracle वेबसाइट से डाउनलोड करें या OpenJDK अपनाएँ।  
- **Aspose.Tasks for Java** – नवीनतम JAR को [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) से प्राप्त करें और इसे अपने प्रोजेक्ट की क्लासपाथ या Maven/Gradle डिपेंडेंसीज़ में जोड़ें।

## पैकेज इम्पोर्ट करें

First, import the classes we’ll need:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## चरण‑दर‑चरण गाइड

### चरण 1: कस्टम फ़ील्ड के साथ एक टेस्ट प्रोजेक्ट बनाएं

हम **एक टेस्ट प्रोजेक्ट बनाकर** शुरू करते हैं और एक कस्टम फ़ील्ड जोड़ते हैं जो बाद में हमारे फ़ॉर्मूला परिणाम को रखेगा।

```java
Project project = CreateTestProjectWithCustomField();
```

> *प्रो टिप:* `CreateTestProjectWithCustomField()` एक हेल्पर मेथड है जो न्यूनतम शेड्यूल बनाता है और फ़ॉर्मूला असाइनमेंट के लिए तैयार एक विस्तारित एट्रिब्यूट रजिस्टर करता है।

### चरण 2: विस्तारित एट्रिब्यूट परिभाषित करें (कस्टम फ़ील्ड जोड़ें)

अब हम **एक विस्तारित एट्रिब्यूट परिभाषित करते हैं** – मूलतः कस्टम फ़ील्ड – और इसे एक उपयोगी उपनाम देते हैं। यहाँ हम **कस्टम फ़ील्ड** लॉजिक जोड़ते हैं।

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** फ़ील्ड को प्रोजेक्ट में पढ़ने योग्य बनाता है।  
- **Formula** टास्क की *Finish* तिथि और उसके *Deadline* के बीच दिनों की संख्या की गणना करता है – *तिथियों के बीच दिनों की गणना* का मूल।

### चरण 3: टास्क के लिए डेडलाइन सेट करें (डेडलाइन टास्क जोड़ें और टास्क डेडलाइन सेट करें)

अब हम एक विशिष्ट टास्क पर *Deadline* प्रॉपर्टी सेट करके **डेडलाइन टास्क** डेटा जोड़ते हैं।

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- `Calendar` इंस्टेंस सटीक डेडलाइन क्षण को परिभाषित करता है।  
- `set(Tsk.DEADLINE, …)` चुने हुए टास्क के लिए **टास्क डेडलाइन सेट करता है**।

### चरण 4: प्रोजेक्ट सहेजें (Microsoft Project फ़ाइल को मैनीपुलेट करें)

अंत में, हम परिवर्तन को एक MPP फ़ाइल में सहेजकर **Microsoft Project को मैनीपुलेट** करते हैं।

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

आप `SaveFile.mpp` को Microsoft Project में खोल सकते हैं ताकि कस्टम फ़ील्ड, फ़ॉर्मूला परिणाम, और डेडलाइन शेड्यूल में प्रतिबिंबित देखें।

## सामान्य समस्याएँ और समाधान

| समस्या | समाधान |
|-------|----------|
| **फ़ॉर्मूला मूल्यांकन नहीं कर रहा** | सुनिश्चित करें कि एट्रिब्यूट की `Formula` स्ट्रिंग सही फ़ील्ड नामों (जैसे, `[Deadline]`, `[Finish]`) का उपयोग करती है। |
| **टास्क नहीं मिला** | जाँचें कि टास्क ID (`1` उदाहरण में) मौजूद है; डिबग करने के लिए `project.getRootTask().getChildren().size()` का उपयोग करें। |
| **लाइसेंस अपवाद** | किसी भी API मेथड को कॉल करने से पहले एक वैध Aspose.Tasks लाइसेंस लागू करें (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Tasks को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?**  
**उत्तर:** हाँ, Aspose.Tasks .NET, Java, और अन्य प्लेटफ़ॉर्म के लिए APIs प्रदान करता है, जिससे आप अपनी पसंद की भाषा में Microsoft Project फ़ाइलों को मैनीपुलेट कर सकते हैं।

**प्रश्न: क्या Aspose.Tasks के लिए कोई फ्री ट्रायल उपलब्ध है?**  
**उत्तर:** बिल्कुल। पूर्ण कार्यात्मक ट्रायल को [Aspose.Tasks डाउनलोड पेज](https://releases.aspose.com/) से डाउनलोड करें।

**प्रश्न: Aspose.Tasks के विस्तृत डॉक्यूमेंटेशन कहां मिल सकता है?**  
**उत्तर:** आधिकारिक दस्तावेज़ [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/) पर होस्ट किए गए हैं।

**प्रश्न: मैं Aspose.Tasks के लिए सपोर्ट कैसे प्राप्त कर सकता हूँ?**  
**उत्तर:** प्रश्न पूछने और समुदाय के साथ अनुभव साझा करने के लिए [Aspose.Tasks फ़ोरम](https://forum.aspose.com/c/tasks/15) पर जाएँ।

**प्रश्न: क्या मूल्यांकन के लिए मुझे अस्थायी लाइसेंस चाहिए?**  
**उत्तर:** छोटे‑समय परीक्षण के लिए एक अस्थायी लाइसेंस उपलब्ध है; आप इसे [अस्थायी लाइसेंस अनुरोध पेज](https://purchase.aspose.com/temporary-license/) से अनुरोध कर सकते हैं।

**अंतिम अपडेट:** 2026-10-05  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.12 (लेखन के समय नवीनतम)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [MPP फ़ाइल कैसे बनाएं – Aspose.Tasks के साथ MPP फ़ॉर्मेट में खाली प्रोजेक्ट बनाएं और सहेजें](/tasks/java/project-configuration/create-save-mpp/)
- [Aspose.Tasks for Java का उपयोग करके MS Project में प्रोजेक्ट शुरू तिथि सेट करें](/tasks/java/project-properties/write-project-info/)
- [Aspose.Tasks के साथ Java में विस्तारित एट्रिब्यूट कैसे बनाएं](/tasks/java/resource-management/extended-resource-attributes/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}