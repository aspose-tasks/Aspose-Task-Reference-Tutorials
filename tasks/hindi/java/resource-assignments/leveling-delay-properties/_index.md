---
date: 2026-01-07
description: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट में संसाधन जोड़ना और संसाधन
  असाइनमेंट के लिए लेवलिंग डिले गुणों को संभालना सीखें।
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में प्रोजेक्ट में रिसोर्स कैसे जोड़ें और लेवलिंग डिले प्रॉपर्टीज़
  को संभालें
url: /hi/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में प्रोजेक्ट में रिसोर्स जोड़ने और लेवलिंग डिले प्रॉपर्टीज़ को संभालने का तरीका

## परिचय
इस ट्यूटोरियल में, आप **प्रोजेक्ट में रिसोर्स कैसे जोड़ें** सीखेंगे जबकि Aspose.Tasks for Java के साथ रिसोर्स असाइनमेंट्स के लिए लेवलिंग डिले प्रॉपर्टीज़ को भी मैनेज करेंगे। चाहे आप एक शेड्यूलिंग इंजन बना रहे हों या प्रोजेक्ट अपडेट्स को ऑटोमेट कर रहे हों, इन चरणों में महारत हासिल करने से आप अपना प्रोजेक्ट डेटा सटीक रख सकते हैं बिना Microsoft Project स्थापित किए।

## त्वरित उत्तर
- **“add resource to project” का क्या अर्थ है?** यह एक नया रिसोर्स एंट्री बनाता है जिसे टास्क्स को असाइन किया जा सकता है।  
- **क्या मैं असाइनमेंट के बाद लेवलिंग डिले सेट कर सकता हूँ?** हाँ, `Asn.DELAY` या `Asn.LEVELING_DELAY` फ़ील्ड्स का उपयोग करके।  
- **क्या इस कोड को चलाने के लिए लाइसेंस चाहिए?** विकास के लिए एक फ्री ट्रायल काम करता है; प्रोडक्शन के लिए पेड लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण समर्थित है?** Java 8 या बाद का।  
- **क्या यह सभी MS Project फ़ाइल फ़ॉर्मैट्स के साथ संगत है?** Aspose.Tasks .MPP, .XML, .XER, और अधिक को सपोर्ट करता है।

## Aspose.Tasks में “add resource to project” क्या है?
प्रोजेक्ट में रिसोर्स जोड़ना मतलब `Project` मॉडल के अंदर एक `Resource` ऑब्जेक्ट बनाना है। यह ऑब्जेक्ट बाद में `ResourceAssignment` के माध्यम से टास्क्स से लिंक किया जा सकता है, जिससे आप कार्य, लागत और लेवलिंग सेटिंग्स को ट्रैक कर सकते हैं।

## लेवलिंग डिले प्रॉपर्टीज़ को क्यों संभालें?
लेवलिंग डिले शेड्यूलर को तब काम को फैलाने में मदद करता है जब रिसोर्स ओवर‑एलोकेटेड होते हैं। डिले सेट करके, आप इंजन को असाइनमेंट की शुरुआत को टालने के लिए कहते हैं, जिससे टकराव से बचा जा सके और प्रोजेक्ट यथार्थवादी बना रहे।

## पूर्वापेक्षाएँ
1. Java Development Kit (JDK): सुनिश्चित करें कि आपके सिस्टम पर Java JDK स्थापित है। आप इसे [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html) से डाउनलोड और इंस्टॉल कर सकते हैं।  
2. Aspose.Tasks for Java लाइब्रेरी: Aspose.Tasks for Java लाइब्रेरी को [download page](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।

## पैकेज इम्पोर्ट करें
First, import the necessary packages into your Java project to use Aspose.Tasks functionalities:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## चरण 1: एक प्रोजेक्ट ऑब्जेक्ट बनाएं
Instantiate a `Project` object, which will serve as the container for all tasks, resources, and assignments:
```java
Project prj = new Project();
```

## चरण 2: एक टास्क बनाएं
Add a task to the project. This demonstrates **टास्क कैसे जोड़ें** programmatically:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## चरण 3: टास्क की शुरूआत तिथि और अवधि सेट करें
Define when the task starts and how long it will run:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## चरण 4: एक रिसोर्स जोड़ें
Now we **प्रोजेक्ट में रिसोर्स जोड़ें** by creating a new `Resource` entry:
```java
Resource resource = prj.getResources().add("Resource 1");
```

## चरण 5: एक रिसोर्स असाइनमेंट बनाएं
Link the task and the newly added resource together:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## चरण 6: लेवलिंग डिले सेट करें
Configure the leveling delay for the assignment. Setting it to zero means no additional delay, but you can adjust the value as needed:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## चरण 7: परिणाम प्रदर्शित करें
Print the important properties to verify that everything was set correctly:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## सामान्य गलतियां और टिप्स
- **गलती:** टास्क की शुरूआत तिथि सेट करना भूल जाने से असाइनमेंट प्रोजेक्ट की शुरुआत पर डिफ़ॉल्ट हो सकता है।  
- **टिप:** डिले की ग्रैन्युलैरिटी को नियंत्रित करने के लिए `prj.getDuration(value, TimeUnitType.Day)` का उपयोग करें।  
- **टिप:** कई रिसोर्सेज़ जोड़ने के बाद, शेड्यूलर को लेवलिंग पुनः गणना करने के लिए `prj.updateResourceAssignments()` को कॉल करें।

## निष्कर्ष
इन चरणों का पालन करके, आप अब **प्रोजेक्ट में रिसोर्स कैसे जोड़ें** जानते हैं, इसे टास्क को असाइन कर सकते हैं, और Aspose.Tasks for Java का उपयोग करके लेवलिंग डिले प्रॉपर्टीज़ को मैनेज कर सकते हैं। यह ज्ञान आपको वास्तविक‑विश्व रिसोर्स प्रतिबंधों के साथ सिंक में रहने वाले मजबूत प्रोजेक्ट‑ऑटोमेशन समाधान बनाने में मदद करता है।

## अक्सर पूछे जाने वाले प्रश्न
### प्र: क्या मैं Aspose.Tasks को अन्य Java लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?
A: हाँ, Aspose.Tasks को अन्य Java लाइब्रेरीज़ के साथ इंटीग्रेट करके प्रोजेक्ट मैनेजमेंट क्षमताओं को बढ़ाया जा सकता है।

### प्र: क्या Aspose.Tasks विभिन्न संस्करणों की Microsoft Project फ़ाइलों के साथ संगत है?
A: हाँ, Aspose.Tasks विभिन्न संस्करणों की Microsoft Project फ़ाइलों को सपोर्ट करता है, जिससे विभिन्न वातावरणों में संगतता सुनिश्चित होती है।

### प्र: मैं Aspose.Tasks के लिए अतिरिक्त समर्थन कहाँ पा सकता हूँ?
A: आप समर्थन और संसाधन [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर पा सकते हैं।

### प्र: क्या मैं खरीदने से पहले Aspose.Tasks को ट्राय कर सकता हूँ?
A: हाँ, आप [releases page](https://releases.aspose.com/) से Aspose.Tasks का फ्री ट्रायल प्राप्त कर सकते हैं।

### प्र: मैं Aspose.Tasks के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?
A: आप मूल्यांकन उद्देश्यों के लिए [temporary license page](https://purchase.aspose.com/temporary-license/) से अस्थायी लाइसेंस का अनुरोध कर सकते हैं।

## अतिरिक्त अक्सर पूछे जाने वाले प्रश्न

**प्र: यदि मैं शून्य‑से‑भिन्न लेवलिंग डिले सेट करता हूँ तो क्या होता है?**  
A: शेड्यूलर असाइनमेंट की शुरुआत को निर्दिष्ट अवधि द्वारा टाल देगा, जिससे ओवर‑एलोकेशन को हल करने में मदद मिलती है।

**प्र: क्या मैं प्रोजेक्ट सहेजने के बाद लेवलिंग डिले पुनः प्राप्त कर सकता हूँ?**  
A: हाँ, आप प्रोजेक्ट फ़ाइल को फिर से खोल सकते हैं और असाइनमेंट से `Asn.DELAY` प्रॉपर्टी पढ़ सकते हैं।

**प्र: क्या सभी असाइनमेंट्स पर एक साथ लेवलिंग डिले लागू करने का कोई तरीका है?**  
A: आप `prj.getResourceAssignments()` के माध्यम से इटररेट करके प्रत्येक असाइनमेंट पर लूप में डिले सेट कर सकते हैं।

**अंतिम अपडेट:** 2026-01-07  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}