---
date: 2026-02-26
description: Aspose.Tasks for Java का उपयोग करके कार्य समाप्ति तिथियों को विभाजित
  करना और प्रोजेक्ट टाइमलाइन को प्रबंधित करना सीखें। यह गाइड दिखाता है कि कार्य को
  कुशलतापूर्वक कैसे विभाजित किया जाए।
linktitle: Split Task Finish Date in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: प्रोजेक्ट टाइमलाइन प्रबंधन – Aspose.Tasks में विभाजित कार्य समाप्ति तिथि
url: /hi/java/task-properties/split-task-finish-date/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में टास्क समाप्ति तिथि को विभाजित करना

## परिचय
Effectively **परियोजना समयसीमा प्रबंधन** is a cornerstone of successful project delivery. When a task’s duration changes, its finish date must be recalculated to keep the schedule accurate. In this tutorial we’ll show you **कैसे टास्क समाप्ति तिथियों को विभाजित किया जाए** Aspose.Tasks for Java के साथ, giving you precise control over your project’s timeline.

## त्वरित उत्तर
- **एक टास्क समाप्ति तिथि को विभाजित करने से क्या प्राप्त होता है?** यह आपको किसी भी दी गई अवधि के लिए अंत तिथि की गणना करने देता है, जिससे आप शेड्यूल को तुरंत समायोजित कर सकते हैं।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Tasks for Java (आधिकारिक साइट से डाउनलोड योग्य)।  
- **क्या विकास के लिए लाइसेंस चाहिए?** परीक्षण के लिए एक अस्थायी लाइसेंस काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **क्या इसे किसी भी प्रोजेक्ट कैलेंडर के साथ उपयोग कर सकते हैं?** हाँ, API प्रोजेक्ट के कैलेंडर का उपयोग करके कार्य दिवस और छुट्टियों का सम्मान करता है।  
- **कितनी लाइनों का कोड चाहिए?** किसी भी अवधि के लिए समाप्ति तिथि प्राप्त करने के लिए दस से कम लाइनों की आवश्यकता है।

## “परियोजना समयसीमा प्रबंधन” Aspose.Tasks के संदर्भ में क्या है?
परियोजना समयसीमा प्रबंधन का अर्थ है प्रत्येक टास्क की शुरूआत और समाप्ति तिथियों को समग्र शेड्यूल के साथ समन्वित रखना, जिसमें कैलेंडर, संसाधन, और टास्क निर्भरताएँ शामिल हों। सटीक समाप्ति‑तिथि गणनाएँ वास्तविक प्रोजेक्शन और स्टेकहोल्डर विश्वास के लिए आवश्यक हैं।

## टास्क की समाप्ति तिथि को क्यों विभाजित करें?
- **लचीलापन:** जल्दी से देखें कि विभिन्न कार्य‑घंटे आवंटन डिलीवरी को कैसे प्रभावित करते हैं।  
- **जोखिम मूल्यांकन:** मूल योजना को बदले बिना “क्या‑अगर” परिदृश्यों का मूल्यांकन करें।  
- **संसाधन योजना:** टास्क अवधि को टीम क्षमता और कैलेंडर प्रतिबंधों के साथ संरेखित करें।

## आवश्यकताएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- Java प्रोग्रामिंग का मूल ज्ञान।  
- Aspose.Tasks for Java लाइब्रेरी स्थापित। आप इसे [here](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।  
- एक Java विकास वातावरण सेट अप किया हुआ।

## पैकेज आयात करें
Start by including the necessary packages in your Java project:
```java
import com.aspose.tasks.*;
```

## Step 1: Find a Split Task
Locate the task you want to split within the project:
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read project
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```

## Step 2: Find the Project Calendar
Retrieve the project calendar for accurate date calculations:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```

## Step 3: Calculate Task Finish Date with Different Durations
Now, calculate the task's finish date for various durations.

### Step 3.1: Duration of 8 Hours
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```

*ऊपर दिया गया कोड विभिन्न अवधियों के लिए दोहराएँ, घंटों को उसी अनुसार समायोजित करें, ताकि आप देख सकें कि प्रत्येक परिवर्तन समाप्ति तिथि को कैसे प्रभावित करता है।*

## सामान्य समस्याएँ और समाधान
- **गलत कैलेंडर संदर्भ:** सुनिश्चित करें कि आप प्रोजेक्ट का कैलेंडर (`project.get(Prj.CALENDAR)`) प्राप्त कर रहे हैं, न कि नया बनाते हैं।  
- **गलत टास्क UID:** UID को किसी वास्तविक टास्क से मिलना चाहिए; अन्यथा `getByUid` `null` लौटाता है और `NullPointerException` उत्पन्न होता है।  
- **समय क्षेत्र असंगतियाँ:** API कैलेंडर के समय क्षेत्र के साथ काम करता है; यदि परिणाम गलत दिखें तो अपने सिस्टम के डिफ़ॉल्ट ज़ोन की जाँच करें।

## निष्कर्ष
**परियोजना समयसीमा प्रबंधन** की कला को टास्क समाप्ति तिथियों को विभाजित करके महारत हासिल करना प्रभावी प्रोजेक्ट मैनेजमेंट के लिए महत्वपूर्ण है। Aspose.Tasks for Java इस प्रक्रिया को सरल बनाता है, जिससे आप अपने शेड्यूल को आसानी से सुव्यवस्थित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न
### Q1: मैं Aspose.Tasks for Java कैसे डाउनलोड करूँ?
A1: आप इसे [here](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।

### Q2: Aspose.Tasks के लिए दस्तावेज़ीकरण कहाँ मिल सकता है?
A2: दस्तावेज़ीकरण के लिए देखें [here](https://reference.aspose.com/tasks/java/)।

### Q3: Aspose.Tasks के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?
A3: अस्थायी लाइसेंस प्राप्त करें [here](https://purchase.aspose.com/temporary-license/)।

### Q4: Aspose.Tasks के लिए समर्थन कहाँ प्राप्त करूँ?
A4: समर्थन फ़ोरम पर जाएँ [here](https://forum.aspose.com/c/tasks/15)।

### Q5: क्या मैं Aspose.Tasks खरीद सकता हूँ?
A5: हाँ, आप इसे खरीद सकते हैं [here](https://purchase.aspose.com/buy)।

## अतिरिक्त अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं इस तकनीक को कस्टम कैलेंडर के साथ उपयोग कर सकता हूँ?**  
A: बिल्कुल। बस `project.get(Prj.CALENDAR)` को अपने कस्टम `Calendar` इंस्टेंस से बदल दें।

**Q: क्या यह विधि गैर‑कार्य दिवसों को ध्यान में रखती है?**  
A: हाँ, कैलेंडर की कार्य समय परिभाषाएँ समाप्ति तिथि की गणना में लागू होती हैं।

**Q: क्या फ्रैक्शनल घंटे (जैसे, 3.5 घंटे) के लिए समाप्ति तिथि प्राप्त करने का कोई तरीका है?**  
A: `getTaskFinishDateFromDuration` को `3.5d` जैसे `double` मान पास करें; API फ्रैक्शनल अवधि को संभालता है।

**Q: मैं आउटपुट तिथि को कैसे फॉर्मेट करूँ?**  
A: लौटाए गए `Date` ऑब्जेक्ट पर `java.time.format.DateTimeFormatter` का उपयोग करके अपनी पसंदीदा फॉर्मेट में प्रदर्शित करें।

---

**अंतिम अपडेट:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}