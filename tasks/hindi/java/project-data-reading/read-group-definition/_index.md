---
date: 2026-10-26
description: Aspose.Tasks for Java का उपयोग करके group definition data कैसे पढ़ें।
  रिपोर्टिंग और माइग्रेशन को स्वचालित करने के लिए Microsoft Project फ़ाइलों से task
  grouping, criteria, और formatting निकालें।
keywords:
- how to read group
- generate group report
- automate project grouping
lastmod: 2026-10-26
linktitle: Aspose.Tasks में group definition data पढ़ें
og_description: Aspose.Tasks for Java का उपयोग करके group definition data कैसे पढ़ें।
  रिपोर्टिंग और माइग्रेशन को स्वचालित करने के लिए Microsoft Project फ़ाइलों से task
  grouping, criteria, और formatting निकालें।
og_image_alt: 'Tutorial guide: Read group definition data in Aspose.Tasks for Java'
og_title: Aspose.Tasks for Java के साथ group definition data कैसे पढ़ें
schemas:
- author: Aspose
  dateModified: '2026-10-26'
  description: How to read group definition data using Aspose.Tasks for Java. Extract
    task grouping, criteria, and formatting from Microsoft Project files to automate
    reporting and migration.
  headline: How to read group definition data with Aspose.Tasks for Java
  type: TechArticle
- description: How to read group definition data using Aspose.Tasks for Java. Extract
    task grouping, criteria, and formatting from Microsoft Project files to automate
    reporting and migration.
  name: How to read group definition data with Aspose.Tasks for Java
  steps:
  - name: set up your data directory
    text: Define the folder that contains the `.mpp` file you want to inspect. Using
      `java.nio.file.Paths` guarantees platform‑independent path handling.
  - name: load the project file
    text: Create a `Project` instance by pointing it to your `.mpp` file. The constructor
      reads the file header and builds an in‑memory model.
  - name: retrieve task groups count
    text: Print the total number of task groups defined in the project. This quick
      check confirms that the file actually contains grouping information.
  - name: retrieve specific task group information
    text: Grab a particular group (index 1 in this example) and display its name and
      the number of criteria it contains. Each group can have multiple criteria that
      define how tasks are grouped.
  - name: retrieve group criterion information
    text: Each group can have one or more criteria. The snippet below extracts details
      such as the field used for grouping, the grouping mode, cell color, and pattern.
  - name: check parent group
    text: Sometimes a criterion belongs to a parent group. This check confirms the
      relationship and prevents null‑pointer issues when navigating the hierarchy.
  - name: retrieve criterion’s font information
    text: Group criteria can have custom font styling. The following code prints the
      font family, size, style, and sorting direction, allowing you to recreate the
      exact look in your own UI.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read/write capabilities for Microsoft Project
      formats, allowing you to add tasks, change resources, and update group definitions
      programmatically.
    question: Can I use Aspose.Tasks for Java to modify project files?
  - answer: It supports MPP, XML, CSV, and other common Project formats across versions
      from Project 2000 up to the latest 2024 release.
    question: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project
      files?
  - answer: Wrap file operations in `try‑catch` blocks and catch `TasksException`
      for detailed error information; inspect the exception’s `getMessage()` for clues.
    question: How should I handle errors while working with Aspose.Tasks for Java?
  - answer: Absolutely – you can export to PDF, XLSX, HTML, and more using the library’s
      dedicated export APIs.
    question: Does Aspose.Tasks for Java offer export to other formats?
  - answer: Visit the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for API references and the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for community assistance.
    question: Where can I find additional resources and support?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read group definition
- Aspose.Tasks
- Java project data
- group reporting
title: Aspose.Tasks for Java के साथ group definition data कैसे पढ़ें
url: /hi/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java में समूह परिभाषा डेटा पढ़ें

## परिचय
Aspose.Tasks for Java आपको प्रोग्रामेटिक रूप से Microsoft Project फ़ाइलों तक पहुँचने, उन्हें संशोधित करने और उनका विश्लेषण करने की सुविधा देता है। इस ट्यूटोरियल में आप **समूह परिभाषा डेटा** को `.mpp` फ़ाइल से कैसे पढ़ें, प्रत्येक समूह का नाम, मानदंड और दृश्य शैली निकालें, और फिर उस जानकारी का उपयोग कस्टम रिपोर्ट बनाने या सेटिंग्स को अन्य प्रोजेक्ट्स में माइग्रेट करने के लिए सीखेंगे। इस क्षमता में निपुणता से आप रिपोर्टिंग को स्वचालित कर सकते हैं, प्रोजेक्ट संरचनाओं को सत्यापित कर सकते हैं, और डेटा‑ड्रिवेन वर्कफ़्लो को सुव्यवस्थित कर सकते हैं।

## त्वरित उत्तर
- **“समूह परिभाषा पढ़ना” का क्या अर्थ है?** इसका मतलब है Microsoft Project द्वारा कार्यों को व्यवस्थित करने के लिए उपयोग किए जाने वाले समूह नियमों (नाम, मानदंड, रंग, फ़ॉन्ट) को निकालना।  
- **मुझे कौन सी लाइब्रेरी चाहिए?** Aspose.Tasks for Java।  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन से IDE समर्थित हैं?** कोई भी Java IDE जैसे IntelliJ IDEA या Eclipse।  
- **कितना कोड आवश्यक है?** प्रोजेक्ट लोड करने और समूह विवरण दिखाने के लिए 30 से कम लाइनों का Java कोड।

## समूह परिभाषा डेटा कैसे पढ़ें
प्रोजेक्ट लोड करें, उसके समूहों को सूचीबद्ध करें, और प्रत्येक समूह के मानदंड की जाँच करें। सीधा उत्तर है: **एक `Project` इंस्टेंस बनाएं, `project.getTaskGroups()` को कॉल करें, और नाम, मानदंड, फ़ॉन्ट और रंग पढ़ने के लिए संग्रह पर इटररेट करें।** निम्नलिखित अनुभाग प्रक्रिया को स्पष्ट चरणों में विभाजित करते हैं, प्रत्येक के साथ एक छोटा कोड प्लेसहोल्डर है जिसे आप Aspose.Tasks दस्तावेज़ से वास्तविक स्निपेट से बदलेंगे।

## समूह परिभाषा पढ़ना क्या है?
समूह परिभाषा पढ़ना का अर्थ है उन समूह नियमों (नाम, मानदंड, फ़ॉर्मेटिंग) को निकालना जो Microsoft Project कार्यों को व्यवस्थित करने के लिए लागू करता है। ये नियम एप्लिकेशन को बताते हैं कि कार्यों को स्थिति, प्राथमिकता या कस्टम फ़ील्ड के आधार पर कैसे क्लस्टर किया जाए, और इनमें फ़ॉन्ट शैली और सेल रंग जैसी दृश्य विशेषताएँ शामिल होती हैं।

## समूह परिभाषा डेटा क्यों पढ़ें?
समूह परिभाषा डेटा पढ़ने से आप **रिपोर्ट जनरेशन को स्वचालित** कर सकते हैं, **समूह लॉजिक को अन्य प्रोजेक्ट्स में माइग्रेट** कर सकते हैं, और **बड़े अपडेट से पहले आवश्यक समूहों के अस्तित्व की पुष्टि** कर सकते हैं। Aspose.Tasks for Java **10,000 से अधिक कार्यों** वाले प्रोजेक्ट्स को पूरी फ़ाइल को मेमोरी में लोड किए बिना प्रोसेस कर सकता है, जिससे उच्च‑प्रदर्शन बैच ऑपरेशन्स संभव होते हैं। अतिरिक्त रूप से, आप फ़ॉन्ट रंग, पैटर्न और सॉर्टिंग दिशा निकाल सकते हैं ताकि कस्टम डैशबोर्ड में सटीक दृश्य लेआउट पुनः निर्मित किया जा सके।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

1. **Java Development Kit (JDK) 8+** – कोई भी नवीनतम संस्करण काम करेगा।  
2. **Aspose.Tasks for Java** – नवीनतम JAR [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. **एक Java IDE** – IntelliJ IDEA, Eclipse, या कोई भी पसंदीदा एडिटर।  

> **Pro tip:** Aspose.Tasks निर्भरता को प्रबंधित करने के लिए Maven या Gradle का उपयोग करें; इससे मैन्युअल JAR हैंडलिंग से बचा जा सकता है।

## पैकेज आयात करें
`Project` Aspose.Tasks for Java में Microsoft Project फ़ाइल का प्रतिनिधित्व करने वाली मुख्य क्लास है।  

```java
import com.aspose.tasks.*;
```

## चरण-दर-चरण मार्गदर्शिका

### चरण 1: अपना डेटा डायरेक्टरी सेट करें
उस फ़ोल्डर को परिभाषित करें जिसमें वह `.mpp` फ़ाइल हो जिसे आप निरीक्षण करना चाहते हैं। `java.nio.file.Paths` का उपयोग करने से प्लेटफ़ॉर्म‑स्वतंत्र पाथ हैंडलिंग सुनिश्चित होती है।

```java
String dataDir = "Your Data Directory";
```

### चरण 2: प्रोजेक्ट फ़ाइल लोड करें
अपने `.mpp` फ़ाइल की ओर इशारा करके एक `Project` इंस्टेंस बनाएं। कंस्ट्रक्टर फ़ाइल हेडर पढ़ता है और मेमोरी में मॉडल बनाता है।

```java
Project project = new Project(dataDir + "project.mpp");
```

### चरण 3: टास्क समूहों की संख्या प्राप्त करें
प्रोजेक्ट में परिभाषित कुल टास्क समूहों की संख्या प्रिंट करें। यह त्वरित जांच पुष्टि करती है कि फ़ाइल में वास्तव में समूह जानकारी मौजूद है।

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### चरण 4: विशिष्ट टास्क समूह जानकारी प्राप्त करें
इस उदाहरण में (इंडेक्स 1) एक विशेष समूह को प्राप्त करें और उसका नाम तथा उसमें मौजूद मानदंडों की संख्या प्रदर्शित करें। प्रत्येक समूह में कई मानदंड हो सकते हैं जो निर्धारित करते हैं कि कार्य कैसे समूहित होते हैं।

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### चरण 5: समूह मानदंड जानकारी प्राप्त करें
प्रत्येक समूह में एक या अधिक मानदंड हो सकते हैं। नीचे दिया गया स्निपेट समूह बनाने के लिए उपयोग किए गए फ़ील्ड, समूह मोड, सेल रंग और पैटर्न जैसी विवरण निकालता है।

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### चरण 6: पैरेंट समूह जांचें
कभी‑कभी एक मानदंड पैरेंट समूह से जुड़ा होता है। यह जांच संबंध की पुष्टि करती है और पदानुक्रम में नेविगेट करते समय null‑pointer समस्याओं से बचाती है।

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### चरण 7: मानदंड का फ़ॉन्ट जानकारी प्राप्त करें
समूह मानदंडों में कस्टम फ़ॉन्ट स्टाइलिंग हो सकती है। निम्नलिखित कोड फ़ॉन्ट फ़ैमिली, आकार, शैली और सॉर्टिंग दिशा को प्रिंट करता है, जिससे आप अपने UI में सटीक लुक पुनः बना सकते हैं।

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## सामान्य समस्याएँ और समाधान
| समस्या | क्यों होता है | समाधान |
|-------|----------------|-----|
| **`NullPointerException` on `criterion.getParentGroup()`** | मानदंड का पैरेंट समूह नहीं हो सकता। | पैरेंट तक पहुँचने से पहले null‑check जोड़ें। |
| **File not found** | `dataDir` पाथ गलत है या फ़ाइल नाम में टाइपो है। | `Paths.get(dataDir, "project.mpp").toAbsolutePath()` का उपयोग करें और फ़ाइल मौजूद है यह सत्यापित करें। |
| **License not set** | Aspose मूल्यांकन मोड में चल रहा है और आउटपुट को ट्रंकेट कर सकता है। | प्रोजेक्ट लोड करने से पहले `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` के साथ लाइसेंस रजिस्टर करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट फ़ाइलों को संशोधित कर सकता हूँ?**  
A: हाँ, लाइब्रेरी Microsoft Project फ़ॉर्मेट के लिए पूर्ण read/write क्षमताएँ प्रदान करती है, जिससे आप प्रोग्रामेटिक रूप से कार्य जोड़ सकते हैं, संसाधनों को बदल सकते हैं, और समूह परिभाषाओं को अपडेट कर सकते हैं।

**Q: क्या Aspose.Tasks for Java सभी संस्करणों की Microsoft Project फ़ाइलों के साथ संगत है?**  
A: यह MPP, XML, CSV और अन्य सामान्य प्रोजेक्ट फ़ॉर्मेट को सपोर्ट करता है, जो Project 2000 से लेकर नवीनतम 2024 रिलीज़ तक के सभी संस्करणों को कवर करता है।

**Q: Aspose.Tasks for Java के साथ काम करते समय त्रुटियों को कैसे संभालें?**  
A: फ़ाइल ऑपरेशन्स को `try‑catch` ब्लॉक्स में रैप करें और विस्तृत त्रुटि जानकारी के लिए `TasksException` को कैच करें; अपवाद के `getMessage()` को देखें ताकि कारण पता चल सके।

**Q: क्या Aspose.Tasks for Java अन्य फ़ॉर्मेट में निर्यात की सुविधा देता है?**  
A: बिल्कुल – आप लाइब्रेरी के समर्पित एक्सपोर्ट API का उपयोग करके PDF, XLSX, HTML आदि में निर्यात कर सकते हैं।

**Q: अतिरिक्त संसाधन और समर्थन कहाँ मिल सकता है?**  
A: API रेफ़रेंस के लिए [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) देखें और समुदाय सहायता के लिए [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर जाएँ।

## निष्कर्ष
इस ट्यूटोरियल में हमने Aspose.Tasks for Java का उपयोग करके Microsoft Project फ़ाइल से **समूह परिभाषा डेटा** को पढ़ने की प्रक्रिया को समझा। `Project` को लोड करके, उसके `TaskGroupCollection` को इटररेट करके, और प्रत्येक समूह के मानदंड, फ़ॉन्ट और रंग की जाँच करके आप स्वचालित रिपोर्टिंग पाइपलाइन बना सकते हैं, समूह नियमों को माइग्रेट कर सकते हैं, या प्रोजेक्ट संरचनाओं को आत्मविश्वास के साथ सत्यापित कर सकते हैं। यही तरीका बड़े प्रोजेक्ट्स में हजारों कार्यों के साथ भी मेमोरी उपयोग को कम रखता है।

---

**अंतिम अपडेट:** 2026-10-26  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Tasks for Java के साथ Microsoft Project से प्रोजेक्ट जानकारी पढ़ें](/tasks/java/project-properties/read-project-info/)
- [Aspose.Tasks में टेबल फ़ील्ड प्राप्त करें और टेबल डेटा पढ़ें](/tasks/java/project-data-reading/read-table-data/)
- [read gantt chart java – विशिष्ट Gantt डेटा निकालें](/tasks/java/project-data-reading/read-specific-gantt-chart-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}