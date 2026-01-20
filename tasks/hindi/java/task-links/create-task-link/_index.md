---
date: 2026-01-20
description: Aspose.Tasks for Java के साथ कार्यों को लिंक करना सीखें। यह चरण‑दर‑चरण
  गाइड आपको कार्य लिंक को कुशलतापूर्वक बनाने का तरीका दिखाता है।
linktitle: Create Task Link in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java में कार्यों को कैसे लिंक करें
url: /hi/java/task-links/create-task-link/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में कार्यों को लिंक कैसे करें

## Introduction
कार्य को लिंक करना वास्तविक प्रोजेक्ट शेड्यूल बनाने का एक मुख्य भाग है, और Aspose.Tasks for Java के साथ **कार्य को लिंक करने का तरीका** जानना आपके मैन्युअल काम के घंटों को बचा सकता है। इस ट्यूटोरियल में आप हर वह कदम देखेंगे जो **टास्क लिंक** ऑब्जेक्ट बनाने, प्रीडेससर‑सक्सेसर संबंध स्थापित करने, और परिणाम को सत्यापित करने के लिए आवश्यक है—सभी स्पष्ट, चलाने योग्य कोड के साथ।

## Quick Answers
- **कार्य को लिंक करने के लिए मुख्य क्लास कौन सी है?** `TaskLink` जिसे `project.getTaskLinks()` द्वारा प्राप्त किया जाता है
- **उदाहरण चलाने के लिए लाइसेंस चाहिए?** परीक्षण के लिए एक अस्थायी लाइसेंस काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।
- **कौन सा Maven आर्टिफैक्ट Aspose.Tasks को शामिल करता है?** `com.aspose:aspose-tasks`
- **क्या मैं दो से अधिक कार्यों को लिंक कर सकता हूँ?** हाँ, जटिल निर्भरताओं के लिए कई `TaskLink` इंस्टेंस जोड़ सकते हैं।
- **सेटअप में कितना समय लगता है?** बेसिक लिंक के लिए 10 मिनट से कम।

## Prerequisites
शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

- **Java Development Environment** – JDK 8 या उससे नया स्थापित हो।
- **Aspose.Tasks Library** – Aspose.Tasks for Java लाइब्रेरी डाउनलोड और इंटीग्रेट करें, उपलब्ध [यहाँ](https://releases.aspose.com/tasks/java/)।

## Import Packages
शुरू करने के लिए, Aspose.Tasks नेमस्पेस इम्पोर्ट करें ताकि आप प्रोजेक्ट, टास्क और लिंक के साथ काम कर सकें।

```java
import com.aspose.tasks.*;
```

## Step 1: Set Document Directory
परिभाषित करें कि आपका प्रोजेक्ट फ़ाइल कहाँ स्थित है। यह पाथ Aspose.Tasks को स्रोत MPP फ़ाइल खोजने में मदद करता है।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Step 2: Initialize Project and Tasks
एक `Project` इंस्टेंस बनाएं और दो सरल टास्क जोड़ें। वास्तविक परिदृश्यों में आप कई टास्क जोड़ेंगे, लेकिन बेसिक लिंक के लिए यह पर्याप्त है।

```java
Project project = new Project(dataDir + "project5.mpp");
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
```

## Step 3: Establish Task Link
`getTaskLinks()` कलेक्शन का उपयोग करके एक लिंक बनाएं जहाँ **Task 1** **Task 2** का प्रीडेससर बन जाता है। यह **कार्य को लिंक करने का तरीका** का मूल है।

```java
TaskLink link = project.getTaskLinks().add(pred, succ);
```

## Step 4: Display Result
एक पुष्टि संदेश प्रिंट करें। उत्पादन में आप लिंक ID को लॉग कर सकते हैं या अपडेटेड प्रोजेक्ट को डिस्क पर लिख सकते हैं।

```java
// Display the result of the conversion.
System.out.println("Task Link Creation Process Completed Successfully");
```

### Why Create Task Links?
- **Dependency Management** – प्रीडेससर प्रतिबंधों के आधार पर स्वचालित रूप से स्टार्ट/फ़िनिश डेट्स की गणना करता है।
- **Clear Visualisation** – गैंट चार्ट वास्तविक‑विश्व कार्य संबंधों को दर्शाते हैं।
- **Risk Reduction** – योजना चरण में ही शेड्यूलिंग टकराव को रोकता है।

### Common Pitfalls & Tips
- **Missing License** – वैध लाइसेंस न होने पर API इवैल्यूएशन मोड में चलती है और वॉटरमार्क जोड़ सकती है।
- **Incorrect Paths** – सुनिश्चित करें कि `dataDir` फ़ाइल सेपरेटर (`/` या `\`) के साथ समाप्त हो ताकि `FileNotFoundException` न आए।
- **Multiple Links** – कई लिंक जोड़ते समय प्रत्येक प्रीडेससर‑सक्सेसर जोड़ी को सत्यापित करें ताकि सर्कुलर डिपेंडेंसी न बनें।

## Conclusion
इन चरणों का पालन करके आप अब **Aspose.Tasks for Java** का उपयोग करके **कार्य को लिंक करने का तरीका** जानते हैं, और आपने **टास्क लिंक बनाने** का एक व्यावहारिक उदाहरण देखा है। कोड को विस्तारित करने के लिए स्वतंत्र महसूस करें: लेग टाइम जोड़ें, लिंक प्रकार बदलें (FS, SS, FF, SF), या टास्क कलेक्शन के माध्यम से लूप करके जटिल शेड्यूल बनाएं।

यदि आपको कोई समस्या आती है, तो [Aspose.Tasks Documentation](https://reference.aspose.com/tasks/java/) देखें या समुदाय से [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) पर पूछें।

## FAQs
### Q: क्या मैं Aspose.Tasks for Java को अन्य Java फ्रेमवर्क के साथ उपयोग कर सकता हूँ?
A: हाँ, Aspose.Tasks विभिन्न Java फ्रेमवर्क के साथ सहजता से इंटीग्रेट होता है, जिससे इसकी बहुमुखी प्रतिभा बढ़ती है।

### Q: लाइब्रेरी खरीदने से पहले कोई फ्री ट्रायल उपलब्ध है?
A: हाँ, प्रतिबद्धता से पहले कार्यक्षमताओं को जांचने के लिए [free trial](https://releases.aspose.com/) का उपयोग करें।

### Q: Aspose.Tasks for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?
A: परीक्षण और मूल्यांकन के लिए अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) प्राप्त करें।

### Q: क्या कोई सैंपल प्रोजेक्ट रेफ़रेंस के लिए उपलब्ध हैं?
A: हाँ, विस्तृत सैंपल प्रोजेक्ट और कोड स्निपेट्स के लिए डॉक्यूमेंटेशन देखें।

### Q: Aspose.Tasks for Java को खरीदने का अनुशंसित तरीका क्या है?
A: [purchase page](https://purchase.aspose.com/buy) पर जाकर अपनी कॉपी सुरक्षित करें और लाइसेंस विकल्पों का अन्वेषण करें।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-20  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

---