---
date: 2026-02-26
description: Aspose.Tasks for Java के साथ कार्यों को विभाजित करना सीखें – कार्यों
  को विभाजित करने, प्रोजेक्ट कैलेंडर सेट करने और संसाधन असाइनमेंट बनाने के बारे में
  अंतिम मार्गदर्शिका।
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में कार्यों को कैसे विभाजित करें
url: /hi/java/task-properties/split-tasks/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में टास्क को कैसे विभाजित करें

## परिचय
यदि आप Java‑आधारित प्रोजेक्ट में **how to split tasks** की तलाश में हैं, तो आप सही जगह पर आए हैं। Aspose.Tasks for Java आपको एक साफ़, प्रोग्रामेटिक तरीका प्रदान करता है जिससे आप एक लंबी चलने वाली टास्क को छोटे, प्रबंधनीय भागों में विभाजित कर सकते हैं, जो रिसोर्स लेवलिंग, सटीक रिपोर्टिंग, और कड़े प्रोजेक्ट टाइमलाइन में मदद करता है। इस ट्यूटोरियल में हम पूरी प्रक्रिया को कवर करेंगे—प्रोजेक्ट कैलेंडर सेट करने से लेकर रिसोर्स असाइनमेंट बनाने और अंत में टास्क को कई भागों में विभाजित करने तक।

## त्वरित उत्तर
- **What is task splitting?** एक एकल टास्क को कई छोटे अंतरालों में विभाजित करना, जबकि उसकी कुल अवधि को बरकरार रखना।  
- **Why split tasks in Java?** यह सटीक रिसोर्स आवंटन और बेहतर प्रोग्रेस ट्रैकिंग को सक्षम बनाता है।  
- **Which library helps?** Aspose.Tasks for Java विभाजन और टाइम‑फ़ेजिंग के लिए बिल्ट‑इन मेथड्स प्रदान करता है।  
- **Do I need a license?** विकास के लिए एक फ्री ट्रायल काम करता है; उत्पादन के लिए लाइसेंस आवश्यक है।  
- **What Java version is supported?** यह लाइब्रेरी Java 8 और उससे नए संस्करणों के साथ काम करती है।

## पूर्वापेक्षाएँ
ट्यूटोरियल में डुबकी लगाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- आपके मशीन पर Java Development Kit (JDK) स्थापित हो।  
- Aspose.Tasks for Java लाइब्रेरी डाउनलोड करके अपने प्रोजेक्ट में जोड़ें। आप इसे [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।

## पैकेज आयात करें
अपने Java प्रोजेक्ट में आवश्यक पैकेज आयात करके शुरू करें:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## चरण 1: नया प्रोजेक्ट बनाएं
Aspose.Tasks लाइब्रेरी का उपयोग करके नया प्रोजेक्ट बनाकर शुरू करें:

```java
// Create a new project
Project splitTaskProject = new Project();
```

## चरण 2: प्रोजेक्ट कैलेंडर सेट करें
**project calendar** सेट करने से कार्य दिवस, छुट्टियां और आपके शेड्यूल की कुल टाइमलाइन निर्धारित होती है। यह चरण सटीक टाइम‑फ़ेज्ड गणनाओं के लिए आवश्यक है।

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## चरण 3: रूट टास्क जोड़ें
हर प्रोजेक्ट को एक रूट कंटेनर की आवश्यकता होती है। रूट टास्क जोड़ने से आप सभी बाद के टास्क को संलग्न करने की जगह प्राप्त करते हैं।

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## चरण 4: विभाजन के लिए नया टास्क जोड़ें
वह टास्क बनाएं जिसे आप विभाजित करना चाहते हैं। यहाँ हमने उदाहरण के तौर पर तीन दिनों की अवधि सेट की है।

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## चरण 5: रिसोर्स असाइनमेंट बनाएं
**resource assignment** एक रिसोर्स (या प्लेसहोल्डर) को टास्क से जोड़ता है। यह टाइम‑फ़ेज्ड डेटा उत्पन्न करने से पहले आवश्यक है।

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## चरण 6: टाइम‑फ़ेज्ड डेटा उत्पन्न करें
टाइम‑फ़ेज्ड डेटा दर्शाता है कि कार्य टास्क की अवधि में कैसे वितरित होता है। इसे उत्पन्न करने से टास्क को विभाजन के लिए तैयार किया जाता है।

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## चरण 7: टास्क को विभाजित करें
अब हम **टास्क को भागों में विभाजित** करते हैं। इस उदाहरण में हम तीन‑दिन के टास्क को तीन एक‑दिन के हिस्सों में विभाजित करते हैं।

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## टास्क को विभाजित क्यों करें?
टास्क को विभाजित करने से आपको अधिक सूक्ष्म नियंत्रण मिलता है:
- **Resource leveling:** प्रत्येक भाग को अलग-अलग रिसोर्स असाइन करें।  
- **Progress tracking:** प्रत्येक भाग के आधार पर स्थिति अपडेट करें।  
- **Reporting:** अधिक विस्तृत गैंट चार्ट और रिपोर्ट जनरेट करें।

## सामान्य समस्याएँ और समाधान
- **Missing calendar data:** विभाजन से पहले `timephasedDataFromTaskDuration` कॉल करना सुनिश्चित करें।  
- **Zero‑duration segments:** प्रत्येक विभाजन अंतराल की अवधि शून्य नहीं हो, यह जांचें; अन्यथा लाइब्रेरी इसे अनदेखा कर देगी।  
- **License exceptions:** वैध लाइसेंस के बिना चलाने पर एक्सपोर्टेड फाइलों में वॉटरमार्क जुड़ सकता है।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं विभिन्न अवधि वाले टास्क को विभाजित कर सकता हूँ?
हाँ, आप प्रत्येक भाग की अवधि को अपने प्रोजेक्ट आवश्यकताओं के अनुसार समायोजित कर सकते हैं।

### क्या Aspose.Tasks for Java सभी Java संस्करणों के साथ संगत है?
Aspose.Tasks for Java को Java 8 और उससे नए संस्करणों के साथ सहजता से काम करने के लिए डिज़ाइन किया गया है, जिससे व्यापक संगतता सुनिश्चित होती है।

### क्या मैं Aspose.Tasks for Java मुफ्त में उपयोग कर सकता हूँ?
Aspose.Tasks for Java एक फ्री ट्रायल प्रदान करता है, जिससे आप खरीदारी से पहले इसकी सुविधाओं को एक्सप्लोर कर सकते हैं।

### मैं Aspose.Tasks for Java के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
सहायता प्राप्त करने और समुदाय से जुड़ने के लिए [Aspose.Tasks for Java support forum](https://forum.aspose.com/c/tasks/15) पर जाएँ।

### क्या मुझे Aspose.Tasks for Java के लिए एक टेम्पररी लाइसेंस की आवश्यकता है?
आप परीक्षण और मूल्यांकन के लिए [इस लिंक](https://purchase.aspose.com/temporary-license/) से एक टेम्पररी लाइसेंस प्राप्त कर सकते हैं।

**अंतिम अपडेट:** 2026-02-26  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}