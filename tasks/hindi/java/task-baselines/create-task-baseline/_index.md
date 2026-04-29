---
date: 2026-01-18
description: जानेँ कि जावा में टास्क सूची कैसे बनाएं और माइक्रोसॉफ्ट प्रोजेक्ट में
  टास्क कैसे जोड़ें, Aspose.Tasks का उपयोग करके बिना MS प्रोजेक्ट के बेसलाइन सेट करें।
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks का उपयोग करके जावा में टास्क लिस्ट बनाएं – एमएस प्रोजेक्ट बेसलाइन
url: /hi/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# टास्क लिस्ट जावा बनाएं – MS प्रोजेक्ट बेसलाइन Aspose.Tasks के साथ

## परिचय
इस ट्यूटोरियल में, आप Aspose.Tasks for Java का उपयोग करके Microsoft Project टास्क बेसलाइन जेनरेट करके **create task list Java** करेंगे। Aspose.Tasks आपको Microsoft Project इंस्टॉल किए बिना प्रोजेक्ट फ़ाइलों के साथ काम करने देता है, इसलिए आप **add task to Microsoft Project**, रिसोर्सेज़ को मैनीपुलेट कर सकते हैं, और यहाँ तक कि **set baseline without MS Project**—सिर्फ शुद्ध Java कोड से कर सकते हैं।

## त्वरित उत्तर
- **What does Aspose.Tasks do?** यह Microsoft Project फ़ाइलों को बनाने, पढ़ने और एडिट करने के लिए एक Java API प्रदान करता है, बिना MS Project के।  
- **Do I need Microsoft Project installed?** नहीं, Aspose.Tasks स्वतंत्र रूप से काम करता है।  
- **Which Java version is required?** JDK 8 या उससे ऊपर।  
- **Can I set a baseline for a single task?** हाँ, `setBaseline` को टास्क लिस्ट के साथ उपयोग करें।  
- **Is a license needed for production?** हाँ, एक कमर्शियल लाइसेंस मूल्यांकन सीमाओं को हटाता है।

## टास्क बेसलाइन क्या है?
एक टास्क बेसलाइन टास्क के मूल योजना प्रारंभ, समाप्ति और कार्य मानों को रिकॉर्ड करती है। यह वास्तविक प्रगति की तुलना मूल योजना से करने के लिए एक संदर्भ बिंदु के रूप में कार्य करती है।

## Aspose.Tasks का उपयोग करके टास्क लिस्ट जावा क्यों बनाएं?
- **No MS Project dependency** – सर्वर‑साइड ऑटोमेशन के लिए आदर्श।  
- **Full control** टास्क, रिसोर्सेज़ और कैलेंडर पर Java कोड के माध्यम से।  
- **Cross‑version compatibility** Project 2007‑2024 फ़ाइलों के साथ।

## पूर्वापेक्षाएँ
1. **Java Development Kit (JDK)** – JDK 8 या नवीनतम इंस्टॉल करें।  
2. **Aspose.Tasks for Java** – लाइब्रेरी को [download link](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  

## पैकेज इम्पोर्ट करें
Aspose.Tasks को अपने Java प्रोजेक्ट में उपयोग करने के लिए आवश्यक पैकेज इम्पोर्ट करें:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## चरण 1: प्रोजेक्ट ऑब्जेक्ट बनाएं
```java
Project project = new Project();
```
यहाँ हम एक नया `Project` ऑब्जेक्ट इंस्टैंशिएट करते हैं – यह वह MS Project फ़ाइल दर्शाता है जो हमारी टास्क लिस्ट को रखेगी।

## चरण 2: प्रोजेक्ट में टास्क जोड़ें
```java
Task task = project.getRootTask().getChildren().add("Task");
```
`getRootTask()` का उपयोग करके हम प्रोजेक्ट हायरार्की की रूट तक पहुँचते हैं और **add task to Microsoft Project**। स्ट्रिंग `"Task"` टास्क का नाम है; आप इसे अपनी आवश्यकता अनुसार किसी भी विवरण से बदल सकते हैं।

## चरण 3: निर्दिष्ट टास्क के लिए बेसलाइन सेट करें
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
**set baseline without MS Project** करने के लिए, उन टास्कों की एक लिस्ट बनाएं जिन्हें आप बेसलाइन करना चाहते हैं (यहाँ `myList`) और इसे `setBaseline` को पास करें। यदि आपको केवल चयनात्मक बेसलाइन चाहिए तो `myList` को जोड़े गए टास्कों से भरें।

## चरण 4: पूरे प्रोजेक्ट के लिए बेसलाइन सेट करें
```java
project.setBaseline(BaselineType.Baseline);
```
यदि आप पूरे प्रोजेक्ट को एक कॉल में बेसलाइन करना चाहते हैं, तो बस इच्छित `BaselineType` के साथ `setBaseline` को कॉल करें।

## Aspose.Tasks का उपयोग करके Microsoft Project में टास्क कैसे जोड़ें
ऊपर दिखाए गए एकल टास्क के अलावा, आप कई टास्क, सब‑टास्क जोड़ सकते हैं और रिसोर्सेज़ असाइन कर सकते हैं। `add()` का प्रत्येक कॉल एक `Task` ऑब्जेक्ट लौटाता है जिसे आप आगे कॉन्फ़िगर कर सकते हैं (अवधि, प्रारंभ तिथि, आदि)।

## MS Project के बिना बेसलाइन कैसे सेट करें
Aspose.Tasks पूरी तरह कोड के माध्यम से बेसलाइन निर्माण सक्षम करता है। आप `BaselineType` एन्‍युम को बदलकर विभिन्न बेसलाइन प्रकार (Baseline, Baseline1‑Baseline10) सेट कर सकते हैं, जिससे आप कई रिवीजन बेसलाइन को ट्रैक कर सकते हैं बिना कभी MS Project खोले।

## सामान्य समस्याएँ और समाधान
- **Baseline not appearing:** सुनिश्चित करें कि बेसलाइन सेट करने के बाद आप `project.save("output.mpp")` कॉल कर रहे हैं (संक्षिप्तता के लिए यहाँ सेव स्टेप छोड़ा गया है)।  
- **Task list appears empty:** जाँचें कि आप टास्क सही पैरेंट (`getRootTask()` या एक सब‑टास्क) में जोड़ रहे हैं।  
- **Version mismatch errors:** नवीनतम Aspose.Tasks JAR का उपयोग करें ताकि नए .mpp फ़ॉर्मेट के साथ संगतता सुनिश्चित हो सके।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Tasks for Java को Microsoft Project इंस्टॉल किए बिना उपयोग कर सकता हूँ?**  
A: हाँ, Aspose.Tasks स्वतंत्र रूप से काम करता है और होस्ट मशीन पर Microsoft Project की आवश्यकता नहीं होती।

**Q: क्या Aspose.Tasks for Java विभिन्न Microsoft Project संस्करणों के साथ संगत है?**  
A: बिल्कुल। यह लाइब्रेरी 2007 से लेकर नवीनतम 2024 रिलीज़ तक के प्रोजेक्ट फ़ाइलों को सपोर्ट करती है।

**Q: क्या मैं Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट रिसोर्सेज़ को मैनीपुलेट कर सकता हूँ?**  
A: हाँ, आप प्रोग्रामेटिक रूप से रिसोर्सेज़ को जोड़, अपडेट और डिलीट कर सकते हैं, ठीक टास्क की तरह।

**Q: क्या Aspose.Tasks for Java टास्क डिपेंडेंसी सेट करने का समर्थन करता है?**  
A: हाँ, आप `TaskLink` क्लास का उपयोग करके प्रीडिसेसर‑सक्सेसर रिलेशनशिप परिभाषित कर सकते हैं।

**Q: क्या Aspose.Tasks for Java के लिए तकनीकी समर्थन उपलब्ध है?**  
A: हाँ, आप [support forum](https://forum.aspose.com/c/tasks/15) के माध्यम से मदद प्राप्त कर सकते हैं, जहाँ Aspose स्टाफ और कम्युनिटी प्रश्नों का उत्तर देती है।

## निष्कर्ष
इन चरणों का पालन करके, आपने **create task list Java**, **add task to Microsoft Project**, और **set baseline without MS Project** को Aspose.Tasks का उपयोग करके सीखा। यह दृष्टिकोण प्रोजेक्ट ऑटोमेशन को सरल बनाता है, डेस्कटॉप Project इंस्टॉलेशन की आवश्यकता को समाप्त करता है, और आपके प्रोजेक्ट डेटा पर पूर्ण प्रोग्रामेटिक नियंत्रण प्रदान करता है।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2026-01-18  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose  

---