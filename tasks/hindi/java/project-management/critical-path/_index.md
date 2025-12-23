---
date: 2025-12-23
description: Aspose.Tasks for Java का उपयोग करके MS Project में कार्य निर्भरताएँ बनाना
  और महत्वपूर्ण पथ की गणना करना सीखें। प्रोजेक्ट प्रबंधन के लिए चरण‑दर‑चरण मार्गदर्शिका।
linktitle: Calculate Critical Path in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में कार्य निर्भरताएँ बनाएं और महत्वपूर्ण पथ की गणना करें
url: /hi/java/project-management/critical-path/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में टास्क डिपेंडेंसी बनाएं और क्रिटिकल पाथ निकालें

## परिचय
इस ट्यूटोरियल में, **आप सीखेंगे कि कैसे टास्क डिपेंडेंसी बनाते हैं** और Aspose.Tasks for Java का उपयोग करके MS Project फ़ाइल में क्रिटिकल पाथ निकालते हैं। क्रिटिकल पाथ को समझना और विज़ुअलाइज़ करना आपके प्रोजेक्ट को समय पर रखने में मदद करता है, जबकि टास्क को सही ढंग से लिंक करना किसी भी देरी को तुरंत दिखाता है। चलिए पूरे प्रोसेस को देखते हैं, पर्यावरण सेटअप से लेकर अंतिम क्रिटिकल पाथ दिखाने तक।

## त्वरित उत्तर
- **पहला कदम क्या है?** अपना Java प्रोजेक्ट सेट करें और Aspose.Tasks लाइब्रेरी जोड़ें।  
- **कौन सा मोड सक्षम होना चाहिए?** `CalculationMode.Automatic` (ऑटोमैटिक कैलकुलेशन सेट करें)।  
- **मैं टास्क को कैसे लिंक करूँ?** `project.getTaskLinks().add(...)` का उपयोग करके टास्क डिपेंडेंसी बनाएं।  
- **मैं क्रिटिकल पाथ को कैसे देखूँ?** `project.getCriticalPath()` पर इटरेट करें और प्रत्येक टास्क का नाम प्रिंट करें।  
- **क्या मुझे लाइसेंस चाहिए?** हाँ, प्रोडक्शन उपयोग के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है।

## “टास्क डिपेंडेंसी बनाना” क्या है?
टास्क डिपेंडेंसी बनाना मतलब टास्कों के बीच संबंध (जैसे, Finish‑to‑Start) निर्धारित करना है ताकि शेड्यूल वास्तविक दुनिया की प्रतिबंधों को दर्शाए। Aspose.Tasks में यह `TaskLink` ऑब्जेक्ट्स के माध्यम से किया जाता है।

## MS Project में क्रिटिकल पाथ क्यों निकालें?
**MS Project क्रिटिकल पाथ** सबसे लंबी निर्भर टास्क श्रृंखला को दिखाता है जो प्रोजेक्ट की न्यूनतम अवधि निर्धारित करती है। इसे निकालकर आप जल्दी से उन टास्कों की पहचान कर सकते हैं जो बिना कुल टाइमलाइन को प्रभावित किए स्लिप नहीं हो सकते—जो प्रभावी **project management Java** एप्लिकेशन्स के लिए आवश्यक है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

1. आपके सिस्टम पर Java Development Kit (JDK) स्थापित हो।  
2. Aspose.Tasks for Java लाइब्रेरी डाउनलोड की हुई और आपके प्रोजेक्ट में जोड़ी गई हो। आप इसे [यहाँ](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।  

## पैकेज इम्पोर्ट करें
शुरू करने के लिए, अपने Java क्लास में आवश्यक पैकेज इम्पोर्ट करें:
```java
import com.aspose.tasks.*;
```

## ऑटोमैटिक कैलकुलेशन कैसे सेट करें?
कैलकुलेशन मोड को ऑटोमैटिक सेट करने से टास्क या लिंक में कोई भी बदलाव तुरंत शेड्यूल को अपडेट करता है, जिसमें क्रिटिकल पाथ भी शामिल है।
```java
project.setCalculationMode(CalculationMode.Automatic);
```

## चरण‑दर‑चरण गाइड

### चरण 1: डेटा डायरेक्टरी सेट करें
उस फ़ोल्डर का पाथ परिभाषित करें जिसमें आपका MS Project फ़ाइल है।
```java
String dataDir = "Your Data Directory";
```

### चरण 2: MS Project फ़ाइल लोड करें
Aspose.Tasks का उपयोग करके मौजूदा प्रोजेक्ट फ़ाइल (जैसे *New project 2013.mpp*) लोड करें।
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```

### चरण 3: टास्क जोड़ें
तीन सरल सबटास्क बनाएं जिन्हें हम बाद में लिंक करेंगे।
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```

### चरण 4: टास्क लिंक बनाएं (create task dependencies)
टास्कों के बीच डिपेंडेंसी परिभाषित करें। यहाँ हम सबसे सामान्य प्रकार, Finish‑to‑Start लिंक, का उपयोग कर रहे हैं।
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
project.getTaskLinks().add(subtask2, subtask3, TaskLinkType.FinishToStart);
```

### चरण 5: क्रिटिकल पाथ दिखाएं (display critical path)
क्रिटिकल पाथ प्राप्त करें और प्रिंट करें। `getCriticalPath()` मेथड टास्क की सूची लौटाता है जो क्रिटिकल चेन बनाते हैं।
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```

### चरण 6: पूर्णता की पुष्टि करें
प्रोसेस समाप्त होने पर एक मैत्रीपूर्ण संदेश दिखाएँ।
```java
System.out.println("Process completed Successfully");
```

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| **क्रिटिकल पाथ खाली है** | लिंक जोड़ने से पहले `CalculationMode.Automatic` सेट किया गया है यह सुनिश्चित करें। |
| **टास्क लिंक नहीं हो रहे** | प्रत्येक डिपेंडेंसी के लिए `TaskLink` ऑब्जेक्ट जोड़े हैं यह जांचें। |
| **लाइसेंस एक्सेप्शन** | `Project` इंस्टेंस बनाने से पहले एक वैध Aspose.Tasks लाइसेंस लोड करें। |

## अक्सर पूछे जाने वाले प्रश्न
### Q: क्या मैं Aspose.Tasks for Java को किसी भी संस्करण की MS Project फ़ाइलों के साथ उपयोग कर सकता हूँ?
A: हाँ, Aspose.Tasks for Java विभिन्न संस्करणों की MS Project फ़ाइलों को सपोर्ट करता है, जिसमें MS Project 2003 से लेकर MS Project 2019 तक की .mpp फ़ाइलें शामिल हैं।  

### Q: क्या Aspose.Tasks for Java के लिए कोई फ्री ट्रायल उपलब्ध है?
A: हाँ, आप एक फ्री ट्रायल [यहाँ](https://releases.aspose.com/) से डाउनलोड कर सकते हैं।  

### Q: Aspose.Tasks for Java के लिए सपोर्ट कहाँ मिल सकता है?
A: आप सपोर्ट [Aspose.Tasks फ़ोरम](https://forum.aspose.com/c/tasks/15) पर पा सकते हैं।  

### Q: क्या मैं Aspose.Tasks for Java के लिए एक टेम्पररी लाइसेंस खरीद सकता हूँ?
A: हाँ, आप एक टेम्पररी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) से खरीद सकते हैं।  

### Q: मैं Aspose.Tasks for Java कैसे खरीद सकता हूँ?
A: आप Aspose.Tasks for Java को वेबसाइट [यहाँ](https://purchase.aspose.com/buy) से खरीद सकते हैं।  

## निष्कर्ष
इन चरणों का पालन करके आपने **टास्क डिपेंडेंसी बनाई**, **ऑटोमैटिक कैलकुलेशन सेट किया**, और अपने MS Project फ़ाइल के लिए सफलतापूर्वक **क्रिटिकल पाथ दिखाया**। यह वर्कफ़्लो आपको शेड्यूल लॉजिक पर पूर्ण नियंत्रण देता है और Java‑आधारित **project management** कोड का उपयोग करके प्रोजेक्ट को ट्रैक पर रखने में मदद करता है।

---

**अंतिम अपडेट:** 2025-12-23  
**टेस्ट किया गया संस्करण:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}