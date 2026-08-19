---
date: 2026-02-28
description: Aspose.Tasks for Java का उपयोग करके टास्क टाइमफ़ेज़्ड डेटा को प्रबंधित
  करना सीखें, लाइब्रेरी डाउनलोड करें, इसे मुफ्त में आज़माएँ, और प्रोजेक्ट ट्रैकिंग
  को सुगम बनाएं।
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks का उपयोग करके टास्क टाइमफ़ेज़्ड डेटा को प्रबंधित कैसे करें (Java)
url: /hi/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks को टास्क टाइमफ़ेज़्ड डेटा के लिए कैसे उपयोग करें

## परिचय
यदि आप **how to use Aspose** की तलाश में हैं ताकि आप अपने प्रोजेक्ट शेड्यूल पर कड़ी पकड़ बना सकें, तो आप सही जगह पर आए हैं। टास्क टाइमफ़ेज़्ड डेटा का सटीक ट्रैकिंग सफल प्रोजेक्ट मैनेजमेंट की नींव है, और Aspose.Tasks for Java आपको इस प्रक्रिया को स्वचालित करने के लिए आवश्यक टूल्स प्रदान करता है। इस ट्यूटोरियल में हम एक पूर्ण, एंड‑टू‑एंड उदाहरण के माध्यम से दिखाएंगे कि कैसे Aspose.Tasks का उपयोग करके प्रोजेक्ट बनाएं, रिसोर्स असाइन करें, बेसलाइन सेट करें, और अंत में टाइमफ़ेज़्ड डेटा को प्राप्त और प्रदर्शित करें।

## त्वरित उत्तर
- **timephased data** का क्या अर्थ है? यह डेटा समय अंतराल (दिन, सप्ताह, महीने) के अनुसार विभाजित होता है जो प्रोजेक्ट टाइमलाइन पर कार्य, लागत, या शेष कार्य को दर्शाता है।  
- **यह क्षमता कौन सी लाइब्रेरी प्रदान करती है?** Aspose.Tasks for Java.  
- **क्या मुझे सैंपल चलाने के लिए लाइसेंस चाहिए?** विकास के लिए एक फ्री ट्रायल काम करता है; प्रोडक्शन के लिए लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण आवश्यक है?** Java 8 या उससे ऊपर।  
- **क्या मैं परिणामों को Excel में एक्सपोर्ट कर सकता हूँ?** हाँ – आप `TimephasedData` कलेक्शन को इटरेट करके आवश्यक किसी भी फ़ॉर्मेट में वैल्यू लिख सकते हैं।

## टास्क टाइमफ़ेज़्ड डेटा क्या है?
टास्क टाइमफ़ेज़्ड डेटा प्रोजेक्ट कैलेंडर के प्रत्येक समय स्लाइस में किसी टास्क के लिए निर्धारित कार्य (या लागत) की मात्रा को दर्शाता है। यह आपको कार्य के वितरण को देखने, ओवरएलोकेशन पहचानने, और नियोजित बनाम वास्तविक प्रगति की तुलना करने में मदद करता है।

## टाइमफ़ेज़्ड डेटा प्रबंधन के लिए Aspose.Tasks क्यों उपयोग करें?
- **पूर्ण नियंत्रण** – Microsoft Project खोले बिना प्रोग्रामेटिकली टाइमफ़ेज़्ड जानकारी बनाएं, संशोधित करें और क्वेरी करें।  
- **क्रॉस‑प्लेटफ़ॉर्म** – वह किसी भी OS पर काम करता है जो Java को सपोर्ट करता है।  
- **कोई COM निर्भरताएँ नहीं** – सर्वर‑साइड ऑटोमेशन के लिए आदर्श।  
- **समृद्ध API** – बॉक्स से ही बेसलाइन, वर्क कंटूर और कस्टम फ़ील्ड्स को सपोर्ट करता है।

## पूर्वापेक्षाएँ
कोड में डुबकी लगाने से पहले, सुनिश्चित करें कि आपके पास है:

- **Java Development Environment** – JDK 8+ इंस्टॉल हो और `JAVA_HOME` कॉन्फ़िगर किया गया हो।  
- **Aspose.Tasks for Java Library** – Aspose.Tasks लाइब्रेरी को डाउनलोड करके अपने प्रोजेक्ट में शामिल करें। आप लाइब्रेरी [here](https://releases.aspose.com/tasks/java/) पर पा सकते हैं।  
- **Document Directory** – आपके मशीन पर एक फ़ोल्डर जहाँ सैंपल प्रोजेक्ट फ़ाइल (`project.xml`) पढ़ी और लिखी जाएगी।

## पैकेज इम्पोर्ट करें
अपने Java प्रोजेक्ट में, आवश्यक Aspose.Tasks क्लासेस को इम्पोर्ट करें:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```

## चरण 1: प्रोजेक्ट की प्रारंभ तिथि सेट करें
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*व्याख्या:* हम एक `Project` इंस्टेंस बनाते हैं, इच्छित प्रारंभ तिथि के साथ एक `Calendar` इनिशियलाइज़ करते हैं, और इसे प्रोजेक्ट की `START_DATE` प्रॉपर्टी को असाइन करते हैं।

## चरण 2: टास्क और रिसोर्स परिभाषित करें
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*व्याख्या:* रूट टास्क के अंतर्गत **Task** नाम का नया टास्क जोड़ा जाता है। हम **Rsc** नाम का एक रिसोर्स भी बनाते हैं और उसकी स्टैंडर्ड तथा ओवरटाइम रेट सेट करते हैं।

## चरण 3: टास्क की अवधि सेट करें
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*व्याख्या:* टास्क को **6 दिनों** की अवधि के लिए शेड्यूल किया गया है।

## चरण 4: रिसोर्स को टास्क से असाइन करें
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*व्याख्या:* पहले परिभाषित रिसोर्स को `ResourceAssignment` के माध्यम से टास्क से जोड़ा जाता है।

## चरण 5: रिसोर्स असाइनमेंट कॉन्फ़िगर करें
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*व्याख्या:* हम असाइनमेंट की स्टॉप और रिज्यूम तिथियों को (प्लेसहोल्डर वैल्यू का उपयोग करके) सेट करते हैं और **Back‑Loaded** वर्क कंटूर लागू करते हैं, जो असाइनमेंट के अंत की ओर अधिक कार्य स्थानांतरित करता है।

## चरण 6: बेसलाइन सेट करें
```java
project.setBaseline(BaselineType.Baseline);
```
*व्याख्या:* बेसलाइन को कैप्चर करने से बाद में नियोजित बनाम वास्तविक मानों की तुलना करना संभव होता है।

## चरण 7: टास्क पूर्णता अपडेट करें
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*व्याख्या:* टास्क को **50 % पूर्ण** के रूप में चिह्नित किया गया है, जो शेष कार्य की गणना को प्रभावित करेगा।

## चरण 8: टाइमफ़ेज़्ड डेटा प्राप्त करें
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*व्याख्या:* यह कॉल असाइनमेंट के **शेष कार्य** को प्रोजेक्ट के समय अंतरालों के अनुसार विभाजित करके प्राप्त करता है।

## चरण 9: टाइमफ़ेज़्ड डेटा प्रदर्शित करें
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*व्याख्या:* हम केवल टाइमफ़ेज़्ड एंट्रीज़ की संख्या और पहली एंट्री का मान प्रिंट करते हैं। वास्तविक परिदृश्य में आप सूची को इटरेट करके डेटा को रिपोर्ट या UI में एक्सपोर्ट करेंगे।

## सामान्य समस्याएँ और समाधान
- **`getTimephasedData` पर NullPointerException** – मेथड कॉल करने से पहले असाइनमेंट की `START` और `FINISH` तिथियों को सेट करना सुनिश्चित करें।  
- **गलत वर्क कंटूर** – सुनिश्चित करें कि आप जिस `WorkContourType` को चुनते हैं वह आपके शेड्यूलिंग स्ट्रेटेजी से मेल खाता है; `BackLoaded` कई विकल्पों में से एक है।  
- **बेसलाइन परिवर्तन नहीं दर्शा रही** – याद रखें कि टास्क, रिसोर्स और असाइनमेंट परिभाषित करने के बाद `project.setBaseline` को कॉल करें।

## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं Aspose.Tasks for Java को किसी भी Java प्रोजेक्ट में उपयोग कर सकता हूँ?
A: हाँ, Aspose.Tasks for Java किसी भी Java‑आधारित प्रोजेक्ट के साथ संगत है।

### प्रश्न: Aspose.Tasks for Java के लिए अतिरिक्त समर्थन कहाँ मिल सकता है?
A: समर्थन और चर्चा के लिए [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) पर जाएँ।

### प्रश्न: क्या Aspose.Tasks for Java के लिए फ्री ट्रायल उपलब्ध है?
A: हाँ, आप एक फ्री ट्रायल [here](https://releases.aspose.com/) पर देख सकते हैं।

### प्रश्न: Aspose.Tasks for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?
A: आप एक अस्थायी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

### प्रश्न: Aspose.Tasks for Java कहाँ खरीद सकते हैं?
A: आप Aspose.Tasks for Java को [here](https://purchase.aspose.com/buy) से खरीद सकते हैं।

---

**अंतिम अपडेट:** 2026-02-28  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12 (लेखन के समय नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}