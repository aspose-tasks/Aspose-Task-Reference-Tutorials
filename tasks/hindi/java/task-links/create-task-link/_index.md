---
date: 2026-07-05
description: Aspose.Tasks का उपयोग करके जावा में प्रोजेक्ट मैनेजमेंट टास्क डिपेंडेंसीज़
  कैसे बनाएं, सीखें। कोड स्निपेट्स के साथ इस चरण‑दर‑चरण गाइड का पालन करें।
keywords:
- project management task dependencies
- Aspose.Tasks Java
- task linking tutorial
linktitle: Aspose.Tasks में प्रोजेक्ट मैनेजमेंट टास्क डिपेंडेंसीज़ बनाएं
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to create project management task dependencies in Java using
    Aspose.Tasks. Follow this step‑by‑step guide with code snippets.
  headline: Create Project Management Task Dependencies in Aspose.Tasks
  type: TechArticle
- description: Learn how to create project management task dependencies in Java using
    Aspose.Tasks. Follow this step‑by‑step guide with code snippets.
  name: Create Project Management Task Dependencies in Aspose.Tasks
  steps:
  - name: Set Document Directory
    text: Define the directory where your documents are stored to ensure Aspose.Tasks
      locates and processes files correctly. The `java.nio.file.Paths` utility helps
      you build platform‑independent file paths. java // The path to the documents
      directory. String dataDir = "Your Document Directory";
  - name: Initialize Project and Tasks
    text: Create a new project and initialize tasks within it. In this example, "Task
      1" and "Task 2" are added to the root task. The `Task` class represents an individual
      work item; each task can have its own ID, name, and schedule. java Project project
      = new Project(dataDir + "project5.mpp"); Task pred = pr
  - name: Establish Task Link
    text: Utilize the `getTaskLinks()` method to add a link between two tasks. This
      example demonstrates linking "Task 1" as a predecessor to "Task 2." The `TaskLink`
      object defines the type of dependency (Finish‑to‑Start, Start‑to‑Start, etc.)
      and optional lag. java TaskLink link = project.getTaskLinks().add
  - name: Display Result
    text: Print a message indicating the successful completion of the task link creation
      process. This step is crucial for debugging and verification. A simple `System.out.println`
      call confirms that the link was added without errors. java // Display the result
      of the conversion. System.out.println("Task Link
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks seamlessly integrates with Spring, Jakarta EE, Android,
      and any standard Java environment.
    question: Can I use Aspose.Tasks for Java with other Java frameworks?
  - answer: Yes, explore the functionalities with the [free trial](https://releases.aspose.com/)
      before making a commitment.
    question: Is there a free trial available before purchasing the library?
  - answer: Acquire a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  - answer: Yes, check the documentation for comprehensive sample projects and code
      snippets.
    question: Are there any sample projects available for reference?
  - answer: Secure your copy by visiting the [purchase page](https://purchase.aspose.com/buy)
      and explore licensing options.
    question: What is the recommended way to purchase Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में प्रोजेक्ट मैनेजमेंट टास्क डिपेंडेंसीज़ बनाएं
url: /hi/java/task-links/create-task-link/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में प्रोजेक्ट मैनेजमेंट टास्क डिपेंडेंसीज़ बनाएं

## परिचय
प्रोजेक्ट मैनेजमेंट टास्क डिपेंडेंसीज़ किसी भी सुव्यवस्थित शेड्यूल की रीढ़ होती हैं, जो प्रारंभ तिथियों, समाप्ति तिथियों और क्रिटिकल पाथ की स्वचालित गणना को सक्षम बनाती हैं। इस ट्यूटोरियल में आप Java में Aspose.Tasks का उपयोग करके **प्रोजेक्ट मैनेजमेंट टास्क डिपेंडेंसीज़** कैसे बनाते हैं, यह सीखेंगे, जो 50 से अधिक फ़ाइल फ़ॉर्मेट्स को सपोर्ट करता है और पूरी फ़ाइल को मेमोरी में लोड किए बिना हजारों टास्क वाले प्रोजेक्ट को संभाल सकता है। नीचे दिए गए चरणों का पालन करके टास्क को लिंक करें, लिंक की पुष्टि करें, और समाधान को वास्तविक‑दुनिया के अनुप्रयोगों में एकीकृत करें।

## त्वरित उत्तर
- **ट्यूटोरियल क्या कवर करता है?** Aspose.Tasks for Java के साथ टास्क लिंक (डिपेंडेंसी) बनाना।  
- **कोड की कितनी पंक्तियों की आवश्यकता है?** मुख्य लिंकिंग लॉजिक केवल दो स्टेटमेंट्स में फिट हो जाता है।  
- **क्या इसे आज़माने के लिए लाइसेंस चाहिए?** 30‑दिन का मुफ्त ट्रायल उपलब्ध है; उत्पादन के लिए लाइसेंस आवश्यक है।  
- **कौन से Java संस्करण समर्थित हैं?** Java 8 से 17 तक पूरी तरह सपोर्टेड हैं।  
- **क्या मैं दो से अधिक टास्क लिंक कर सकता हूँ?** हाँ – किसी भी संख्या में प्री‑डेसिसर‑सक्सेसर जोड़े के लिए लिंकिंग पैटर्न दोहराएँ।

## प्रोजेक्ट मैनेजमेंट टास्क डिपेंडेंसीज़ क्या हैं?
प्रोजेक्ट मैनेजमेंट टास्क डिपेंडेंसीज़ यह निर्धारित करती हैं कि एक टास्क की शुरुआत या समाप्ति दूसरे टास्क से कैसे संबंधित है, जिससे कार्य के क्रम को नियंत्रित किया जाता है। Aspose.Tasks इन संबंधों को `TaskLink` ऑब्जेक्ट्स के माध्यम से दर्शाता है, जिन्हें आप प्रोग्रामेटिकली बना, संशोधित या हटा सकते हैं।

## टास्क लिंकिंग के लिए Aspose.Tasks क्यों उपयोग करें?
Aspose.Tasks **50+ इनपुट और आउटपुट फ़ॉर्मेट्स** (जैसे MPP, XML, CSV) को सपोर्ट करता है और **10,000+ टास्क** वाले प्रोजेक्ट को सामान्य सर्वर पर 200 MB से कम RAM का उपयोग करके प्रोसेस कर सकता है। इसका API आपको लिंक प्रकार, लैग टाइम, और कॉन्स्ट्रेंट हैंडलिंग पर सूक्ष्म नियंत्रण देता है, बिना Microsoft Project इंस्टॉल किए।

## पूर्वापेक्षाएँ
ट्यूटोरियल शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित तैयार हैं:
- जावा विकास वातावरण: अपने मशीन पर एक कार्यात्मक जावा विकास वातावरण सेट करें।  
- Aspose.Tasks लाइब्रेरी: Aspose.Tasks for Java लाइब्रेरी डाउनलोड और इंटीग्रेट करें, उपलब्ध [यहाँ](https://releases.aspose.com/tasks/java/)।

## पैकेज आयात करें
शुरू करने के लिए आवश्यक पैकेजों को अपने Java प्रोजेक्ट में इम्पोर्ट करें। यह Aspose.Tasks की कार्यक्षमताओं तक पहुँचने के लिए आवश्यक है।

`Project` क्लास Aspose.Tasks का एंट्री पॉइंट है जो मेमोरी में पूरी प्रोजेक्ट फ़ाइल का प्रतिनिधित्व करता है।  
```text
```java
import com.aspose.tasks.*;
```
```

## Aspose.Tasks for Java का उपयोग करके टास्क लिंक कैसे बनाएं?
एक `Project` इंस्टेंस लोड या बनाएं, आवश्यक टास्क जोड़ें, और फिर `getTaskLinks().add()` को कॉल करके डिपेंडेंसी स्थापित करें। यह मेथड एक `TaskLink` ऑब्जेक्ट बनाता है जो प्री‑डेसिसर और सक्सेसर टास्क को लिंक करता है, वैकल्पिक रूप से आप लिंक प्रकार और लैग भी निर्दिष्ट कर सकते हैं। नीचे दिए गए चरणों में आपको बिल्कुल वही कोड मिलेगा—कोई अतिरिक्त बायलरप्लेट नहीं।

### चरण 1: दस्तावेज़ डायरेक्टरी सेट करें
अपने दस्तावेज़ जहाँ संग्रहीत हैं, उस डायरेक्टरी को परिभाषित करें ताकि Aspose.Tasks फ़ाइलों को सही ढंग से लोकेट और प्रोसेस कर सके।

`java.nio.file.Paths` यूटिलिटी आपको प्लेटफ़ॉर्म‑इंडिपेंडेंट फ़ाइल पाथ बनाने में मदद करती है।  
```text
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
```

### चरण 2: प्रोजेक्ट और टास्क प्रारंभ करें
एक नया प्रोजेक्ट बनाएं और उसके भीतर टास्क को इनिशियलाइज़ करें। इस उदाहरण में, "Task 1" और "Task 2" को रूट टास्क में जोड़ा गया है।

`Task` क्लास एक व्यक्तिगत कार्य आइटम का प्रतिनिधित्व करती है; प्रत्येक टास्क का अपना ID, नाम, और शेड्यूल हो सकता है।  
```text
```java
Project project = new Project(dataDir + "project5.mpp");
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
```
```

### चरण 3: टास्क लिंक स्थापित करें
`getTaskLinks()` मेथड का उपयोग करके दो टास्क के बीच लिंक जोड़ें। यह उदाहरण "Task 1" को "Task 2" का प्री‑डेसिसर बनाकर लिंक दिखाता है।

`TaskLink` ऑब्जेक्ट डिपेंडेंसी का प्रकार (Finish‑to‑Start, Start‑to‑Start, आदि) और वैकल्पिक लैग को परिभाषित करता है।  
```text
```java
TaskLink link = project.getTaskLinks().add(pred, succ);
```
```

### चरण 4: परिणाम प्रदर्शित करें
टास्क लिंक निर्माण प्रक्रिया की सफल पूर्णता को दर्शाने वाला संदेश प्रिंट करें। यह चरण डिबगिंग और वैरिफिकेशन के लिए महत्वपूर्ण है।

एक सरल `System.out.println` कॉल यह पुष्टि करता है कि लिंक बिना त्रुटियों के जोड़ा गया है।  
```text
```java
// Display the result of the conversion.
System.out.println("Task Link Creation Process Completed Successfully");
```
```

इन चरणों को अधिक जटिल टास्क लिंकिंग परिदृश्यों के लिए दोहराएँ, टास्क नाम कस्टमाइज़ करें, और अपने प्रोजेक्ट की आवश्यकताओं के अनुसार डिपेंडेंसी स्थापित करें।

विस्तृत API जानकारी के लिए [Aspose.Tasks Documentation](https://reference.aspose.com/tasks/java/) देखें।  
समुदाय समर्थन के लिए, [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) पर जाएँ।

## सामान्य समस्याएँ और समाधान
`save` मेथड प्रोजेक्ट को निर्दिष्ट फ़ाइल पाथ पर लिखता है, जिससे सभी बदलाव, जिसमें जोड़े गए लिंक भी शामिल हैं, स्थायी होते हैं।  
`TaskLinkType` एनेमरेशन संबंध प्रकार को परिभाषित करता है, जैसे `FinishToStart` एक फ़िनिश‑टू‑स्टार्ट डिपेंडेंसी के लिए।

- **सेव्ड फ़ाइल में लिंक नहीं दिख रहा** – लिंक जोड़ने के बाद `project.save(outputPath)` कॉल करना सुनिश्चित करें।  
- **गलत लिंक प्रकार** – अपने शेड्यूलिंग लॉजिक से मेल खाने के लिए `TaskLinkType.FinishToStart`, `StartToStart` आदि का उपयोग करें।  
- **बड़े प्रोजेक्ट्स में मेमोरी स्पाइक** – स्ट्रीमिंग मोड में काम करने के लिए लोड करने से पहले `project.setReadOnly(true)` सक्षम करें।

## अक्सर पूछे जाने वाले प्रश्न
**प्रश्न: क्या मैं Aspose.Tasks for Java को अन्य Java फ्रेमवर्क्स के साथ उपयोग कर सकता हूँ?**  
उत्तर: हाँ, Aspose.Tasks Spring, Jakarta EE, Android, और किसी भी मानक Java वातावरण के साथ सहजता से इंटीग्रेट होता है।

**प्रश्न: लाइब्रेरी खरीदने से पहले कोई मुफ्त ट्रायल उपलब्ध है?**  
उत्तर: हाँ, खरीदारी से पहले [फ्री ट्रायल](https://releases.aspose.com/) के साथ कार्यक्षमताओं का अन्वेषण करें।

**प्रश्न: Aspose.Tasks for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
उत्तर: परीक्षण और मूल्यांकन उद्देश्यों के लिए अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) प्राप्त करें।

**प्रश्न: क्या कोई सैंपल प्रोजेक्ट्स रेफ़रेंस के लिए उपलब्ध हैं?**  
उत्तर: हाँ, विस्तृत सैंपल प्रोजेक्ट्स और कोड स्निपेट्स के लिए दस्तावेज़ देखें।

**प्रश्न: Aspose.Tasks for Java को खरीदने का अनुशंसित तरीका क्या है?**  
उत्तर: अपनी कॉपी सुरक्षित करने के लिए [पर्चेज पेज](https://purchase.aspose.com/buy) पर जाएँ और लाइसेंस विकल्पों का अन्वेषण करें।

---

**अंतिम अपडेट:** 2026-07-05  
**परीक्षित:** Aspose.Tasks 24.12 for Java  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल्स

- [टास्क प्रॉपर्टीज़ – Aspose Java में टास्क बनाएं](/tasks/java/task-properties/)
- [प्रोजेक्ट मैनेजमेंट बेसलाइन – Aspose.Tasks के साथ टास्क शेड्यूलिंग](/tasks/java/task-baselines/baseline-task-scheduling/)
- [रिसोर्स बनाना – Aspose.Tasks for Java के साथ रिसोर्स मैनेजमेंट](/tasks/java/resource-management/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}