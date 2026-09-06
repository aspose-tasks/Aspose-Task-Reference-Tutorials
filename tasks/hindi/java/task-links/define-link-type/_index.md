---
date: 2026-08-29
description: Aspose.Tasks for Java के साथ लिंक प्रकार सेट करना और टास्क डिपेंडेंसीज़
  को प्रबंधित करना सीखें, एक चरण-दर-चरण ट्यूटोरियल में।
keywords:
- how to set link
- Aspose.Tasks link types
- Java task dependencies
lastmod: 2026-08-29
linktitle: Aspose.Tasks for Java में लिंक प्रकार कैसे सेट करें
og_description: Aspose.Tasks for Java के साथ लिंक प्रकार सेट करना और टास्क डिपेंडेंसीज़
  को प्रबंधित करना सीखें। डेवलपर्स के लिए चरण-दर-चरण गाइड।
og_image_alt: Screenshot of Aspose.Tasks Java code setting task link types
og_title: Aspose.Tasks for Java में लिंक प्रकार कैसे सेट करें
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set link types and manage task dependencies with Aspose.Tasks
    for Java in a step‑by‑step tutorial.
  headline: How to Set Link Types in Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates with standard Java SE, Java EE, and Android
      development kits without additional dependencies.
    question: Is Aspose.Tasks compatible with different Java environments?
  - answer: Absolutely. The `TaskLinkType` enum provides four standard types, and
      you can combine them with lag values to model complex schedules.
    question: Can I customize link types based on my project requirements?
  - answer: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for in‑depth guidance, API reference, and code samples.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to acquire a temporary license for testing purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15)
      for assistance and discussions.
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task link
title: Aspose.Tasks for Java में लिंक प्रकार कैसे सेट करें
url: /hi/java/task-links/define-link-type/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java में लिंक प्रकार कैसे सेट करें

## परिचय
यदि आप किसी प्रोजेक्ट में टास्क के बीच **लिंक कैसे सेट करें** और *टास्क निर्भरताओं को प्रबंधित करें* के बारे में सोच रहे हैं, तो आप सही जगह पर आए हैं। इस ट्यूटोरियल में हम नया प्रोजेक्ट बनाना, टास्क जोड़ना, और Aspose.Tasks for Java का उपयोग करके लिंक प्रकार (Start‑to‑Start, Finish‑to‑Start, आदि) निर्धारित करना दिखाएंगे। अंत तक आप वास्तविक‑दुनिया की शेड्यूलिंग आवश्यकताओं के अनुसार टास्क संबंधों को अनुकूलित करने में आत्मविश्वास महसूस करेंगे और देखेंगे कि API 10,000 तक टास्क वाले बड़े‑पैमाने के प्लान को कैसे संभालता है।

## त्वरित उत्तर
- **निर्भरता को दर्शाने वाला क्लास कौन सा है?** `TaskLink` दो टास्क के बीच लिंक को मॉडल करने वाला कोर ऑब्जेक्ट है।  
- **संबंध प्रकार को परिभाषित करने वाला enum कौन सा है?** `TaskLinkType` (उदा., `StartToStart`, `FinishToStart`)।  
- **क्या मैं मौजूदा लिंक प्रकार पढ़ सकता हूँ?** हाँ – `Project.getTaskLinks()` को इटरेट करें और `getLinkType()` को कॉल करें।  
- **क्या इस कोड के लिए लाइसेंस चाहिए?** परीक्षण के लिए एक अस्थायी लाइसेंस काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **क्या यह Java 8+ के साथ संगत है?** बिल्कुल – Aspose.Tasks Java 8 से लेकर Java 21 तक सपोर्ट करता है, जो 13 प्रमुख रिलीज़ को कवर करता है।

## टास्क लिंक क्या है?
एक **टास्क लिंक** प्रोजेक्ट शेड्यूल में दो टास्क के बीच निर्भरत को मॉडल करता है।  
आप `TaskLink` को बना, संशोधित या हटाकर predecessor‑successor संबंधों को दर्शा सकते हैं, जिससे शेड्यूलर स्वचालित रूप से प्रारंभ और समाप्ति तिथियों की गणना करता है।

## Aspose.Tasks लिंक प्रकारों का उपयोग क्यों करें?
Aspose.Tasks **30+ इनपुट और आउटपुट फॉर्मैट** को सपोर्ट करता है और **10,000 तक टास्क** वाले प्रोजेक्ट को पूरी फ़ाइल को मेमोरी में लोड किए बिना प्रोसेस कर सकता है। यह मापी गई क्षमता एंटरप्राइज़‑स्तर के प्लानों के लिए भी तेज़ प्रदर्शन सुनिश्चित करती है, और लाइब्रेरी सभी Microsoft Project सुविधाओं जैसे कस्टम फ़ील्ड और रिसोर्स असाइनमेंट को संरक्षित रखती है।

## पूर्वापेक्षाएँ
- **Java Development Environment** – JDK 8 या नया स्थापित और कॉन्फ़िगर किया हुआ।  
- **Aspose.Tasks Library** – नवीनतम JAR को [download link](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
- **Document Directory** – अपने मशीन पर एक फ़ोल्डर बनाएं जहाँ आप सैंपल प्रोजेक्ट फ़ाइलें रखेंगे।

## पैकेज आयात करें
हम आवश्यक Aspose.Tasks क्लासेस को आयात करके शुरू करते हैं। यह IDE को बाद में उपयोग किए जाने वाले API कॉल्स को पहचानने के लिए तैयार करता है।

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```

## Aspose.Tasks for Java में लिंक प्रकार कैसे सेट करें?
एक नया `Project` इंस्टेंस लोड करें, दो टास्क जोड़ें, और फिर इच्छित `TaskLinkType` के साथ एक `TaskLink` बनाएं। यह दो‑स्टेप पैटर्न आपको एक कॉल में चार मानक निर्भरत प्रकारों में से कोई भी परिभाषित करने देता है। `Project` पूरे प्रोजेक्ट फ़ाइल और उसके शेड्यूल को दर्शाता है। `Task` प्रोजेक्ट के भीतर एक व्यक्तिगत कार्य वस्तु है। `TaskLink` predecessor टास्क को successor टास्क से जोड़ता है। `TaskLinkType` एक enumeration है जो संबंध (Start‑to‑Start, Finish‑to‑Start, आदि) को निर्दिष्ट करता है।

### चरण 1: लिंक प्रकार सेट करना
`TaskLink` दो टास्क के बीच निर्भरत को दर्शाता है, जबकि `TaskLinkType` संभावित संबंध प्रकारों जैसे `StartToStart` को enumerate करता है। इस चरण में हम एक नया प्रोजेक्ट बनाते हैं, दो टास्क जोड़ते हैं, और उन्हें **Start‑to‑Start** संबंध का उपयोग करके लिंक करते हैं।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

Project project = new Project();
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
TaskLink link = project.getTaskLinks().add(pred, succ);
link.setLinkType(TaskLinkType.StartToStart);
```

> **Pro tip:** आप `StartToStart` को `FinishToStart`, `StartToFinish`, या `FinishToFinish` से बदल सकते हैं, यह निर्भरत पर निर्भर करता है जिसे आपको **टास्क निर्भरताओं को प्रबंधित करने** की आवश्यकता है।

### चरण 2: लिंक प्रकार प्राप्त करना
`Project.getTaskLinks()` शेड्यूल में सभी `TaskLink` ऑब्जेक्ट्स का संग्रह लौटाता है। इस संग्रह को इटरेट करके आप प्रत्येक लिंक का `TaskLinkType` पढ़ सकते हैं और सत्यापित कर सकते हैं कि सही संबंध सहेजा गया था।

```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```

कंसोल `StartToStart`, `FinishToStart` आदि मान आउटपुट करेगा, जिससे आप पहले सेट किए गए लिंक प्रकार की पुष्टि कर सकते हैं।

## सामान्य समस्याएँ और समाधान
- **लिंक जोड़ते समय NullPointerException** – `TaskLink` बनाने से पहले सुनिश्चित करें कि दोनों predecessor और successor टास्क प्रोजेक्ट में जोड़े गए हैं।  
- **सेव करने के बाद गलत लिंक प्रकार** – लिंक प्रकार सेट करने के बाद हमेशा `project.save("output.mpp")` (या कोई अन्य समर्थित फ़ॉर्मेट) को कॉल करें ताकि परिवर्तन सहेजे जा सकें।  
- **लाइसेंस नहीं मिला** – अपने Aspose.Tasks लाइसेंस फ़ाइल को प्रोजेक्ट की क्लासपाथ में रखें और इसे `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` से लोड करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.Tasks विभिन्न Java वातावरणों के साथ संगत है?**  
A: हाँ, Aspose.Tasks मानक Java SE, Java EE, और Android विकास किट्स के साथ अतिरिक्त निर्भरताओं के बिना एकीकृत होता है।

**Q: क्या मैं अपने प्रोजेक्ट आवश्यकताओं के आधार पर लिंक प्रकार को कस्टमाइज़ कर सकता हूँ?**  
A: बिल्कुल। `TaskLinkType` enum चार मानक प्रकार प्रदान करता है, और आप उन्हें लैग वैल्यूज़ के साथ मिलाकर जटिल शेड्यूल बना सकते हैं।

**Q: Aspose.Tasks for Java की विस्तृत दस्तावेज़ीकरण कहाँ मिल सकती है?**  
A: गहन मार्गदर्शन, API रेफ़रेंस, और कोड सैंपल्स के लिए [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) देखें।

**Q: Aspose.Tasks के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
A: परीक्षण उद्देश्यों के लिए अस्थायी लाइसेंस प्राप्त करने हेतु [temporary license page](https://purchase.aspose.com/temporary-license/) पर जाएँ।

**Q: Aspose.Tasks‑संबंधित प्रश्नों के लिए समर्थन कहाँ मिल सकता है?**  
A: सहायता और चर्चा के लिए [support forum](https://forum.aspose.com/c/tasks/15) पर Aspose.Tasks समुदाय में शामिल हों।

**Q: क्या प्रोजेक्ट सेव होने के बाद लिंक प्रकार बदल सकता हूँ?**  
A: हाँ। प्रोजेक्ट लोड करें, `TaskLink` प्राप्त करें, नई enum वैल्यू के साथ `setLinkType()` कॉल करें, और प्रोजेक्ट को फिर से सेव करें।

**Q: क्या Aspose.Tasks Microsoft Project (MPP) फ़ाइलें पढ़ने का समर्थन करता है?**  
A: हाँ। `new Project("file.mpp")` का उपयोग करके MPP फ़ाइलें लोड करें और उनके टास्क लिंक को ऊपर के XML उदाहरण की तरह काम करें।

---

**अंतिम अपडेट:** 2026-08-29  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Tasks में क्रॉस‑प्रोजेक्ट टास्क लिंक बनाएं](/tasks/java/task-links/create-cross-project-task-link/)
- [Aspose.Tasks में प्रोजेक्ट प्रारंभ तिथि सेट करें और पैरेंट व चाइल्ड टास्क प्रबंधित करें](/tasks/java/task-properties/parent-child-tasks/)
- [Java में MPP फ़ाइल लोड करें - Aspose.Tasks के साथ प्रोजेक्ट प्रॉपर्टीज़ प्रबंधित करें](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}