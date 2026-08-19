---
date: 2026-02-28
description: Aspose.Tasks for Java का उपयोग करके मिनट, दिन, घंटे, सप्ताह और महीने
  में अवधि कैसे प्राप्त करें, सीखें। कोड उदाहरणों के साथ विस्तृत गाइड।
linktitle: Task Duration in Different Units with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks के साथ विभिन्न इकाइयों में अवधि कैसे प्राप्त करें
url: /hi/java/task-properties/task-duration-different-units/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ विभिन्न इकाइयों में अवधि कैसे प्राप्त करें

## परिचय
कार्य की **अवधि प्राप्त करने** को समझना किसी भी प्रोजेक्ट‑मैनेजमेंट वर्कफ़्लो का मूल भाग है। चाहे आपको सूक्ष्म ट्रैकिंग के लिए मिनट चाहिए हों या उच्च‑स्तरीय योजना के लिए महीने, Aspose.Tasks for Java रूपांतरण को सरल बनाता है। इस ट्यूटोरियल में हम आपको कार्य की अवधि को मिनट, दिन, घंटे, सप्ताह और महीने में प्राप्त करने के चरण बताएँगे, साथ ही यह समझाएँगे कि वास्तविक प्रोजेक्ट्स में प्रत्येक इकाई क्यों उपयोगी हो सकती है।

## त्वरित उत्तर
- **“अवधि प्राप्त करने” का क्या अर्थ है?** यह कार्य की समयावधि को निकालने और उसे आवश्यक इकाई में बदलने की प्रक्रिया है।  
- **कौन सा API मेथड रूपांतरण करता है?** `Task.get(Tsk.DURATION).convert(TimeUnitType.<Unit>)`.  
- **क्या कोड चलाने के लिए मुझे लाइसेंस चाहिए?** परीक्षण के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **क्या मैं कस्टम इकाइयों में रूपांतरण कर सकता हूँ?** आप रूपांतरणों को चेन कर सकते हैं या कस्टम गणनाओं के लिए `TimeSpan` का उपयोग कर सकते हैं।  
- **क्या कोड Java 17 के साथ संगत है?** हाँ, Aspose.Tasks Java 8 और उसके बाद के संस्करणों को सपोर्ट करता है।

## Aspose.Tasks में “अवधि प्राप्त करने” क्या है?
Aspose.Tasks कार्य की लंबाई को `Duration` ऑब्जेक्ट के रूप में संग्रहीत करता है। `convert` मेथड को कॉल करके और `TimeUnitType` (Minute, Hour, Day, Week, Month) निर्दिष्ट करके, आप वही मूल मान वांछित इकाई में प्राप्त कर सकते हैं। यह लचीलापन आपको रिपोर्ट बनाने, गणनाएँ करने, या डेटा को अन्य सिस्टम में मैन्युअल गणना के बिना फ़ीड करने की अनुमति देता है।

## अवधि रूपांतरण के लिए Aspose.Tasks क्यों उपयोग करें?
- **सटीकता:** कैलेंडर अपवाद, कार्य समय, और गैर‑मानक कैलेंडरों को स्वचालित रूप से संभालता है।  
- **प्रदर्शन:** सिंगल‑लाइन रूपांतरण लूप या कस्टम पार्सिंग से बचाता है।  
- **पोर्टेबिलिटी:** Windows, Linux, और macOS वातावरण में समान रूप से काम करता है।  
- **एकीकरण:** मौजूदा Java एप्लिकेशन में सहजता से फिट बैठता है जो पहले से ही Aspose.Tasks का उपयोग करते हैं।

## पूर्वापेक्षाएँ
कोड में डुबकी लगाने से पहले सुनिश्चित करें कि आपके पास है:

- Java Development Kit (JDK) स्थापित
- Aspose.Tasks for Java लाइब्रेरी। आप इसे [here](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं
- Java प्रोग्रामिंग की बुनियादी समझ

## पैकेज आयात करें
अपने Java प्रोजेक्ट में Aspose.Tasks लाइब्रेरी को शामिल करें। कोड की शुरुआत में निम्नलिखित इम्पोर्ट स्टेटमेंट जोड़ें:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## चरण 1: अपना प्रोजेक्ट सेट अप करें
अपने पसंदीदा IDE (IntelliJ, Eclipse, VS Code, आदि) में एक नया Java प्रोजेक्ट बनाएं और Aspose.Tasks JAR को प्रोजेक्ट की क्लासपाथ में जोड़ें। यह सुनिश्चित करता है कि ऊपर दी गई क्लासेज़ कंपाइल समय पर उपलब्ध हों।

## चरण 2: प्रोजेक्ट टेम्पलेट पढ़ें
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read MS Project template file
String fileName = dataDir + "project.xml";
// Read the input file as Project
Project project = new Project(fileName);
```

`"Your Document Directory"` को उस वास्तविक फ़ोल्डर से बदलें जिसमें आपका `.xml` या `.mpp` प्रोजेक्ट फ़ाइल मौजूद है।

## चरण 3: एक कार्य प्राप्त करें
```java
// Get a task to calculate its duration in different formats
Task task = project.getRootTask().getChildren().getById(1);
```

`getById(1)` कॉल ID 1 वाले कार्य को प्राप्त करता है। अपनी फ़ाइल में किसी अन्य कार्य को लक्षित करने के लिए ID को समायोजित करें।

## चरण 4: मिनट में अवधि – मिनट में अवधि कैसे प्राप्त करें?
```java
// Get the duration in Minutes
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```

`mins` वेरिएबल अब कार्य की लंबाई को मिनट में रखता है।

## चरण 5: दिनों में अवधि – दिनों में अवधि कैसे प्राप्त करें?
```java
// Get the duration in Days
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```

रिपोर्टिंग या संसाधन आवंटन के लिए दिन‑स्तर की ग्रैन्युलैरिटी की आवश्यकता होने पर इस मान का उपयोग करें।

## चरण 6: घंटों में अवधि – घंटों में अवधि कैसे प्राप्त करें?
```java
// Get the duration in Hours
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```

समय‑शीट्स या जब आप एक दिन को कार्य शिफ्ट में विभाजित करना चाहते हैं, तो घंटे उपयोगी होते हैं।

## चरण 7: हफ़्तों में अवधि – हफ़्तों में अवधि कैसे प्राप्त करें?
```java
// Get the duration in Weeks
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```

उच्च‑स्तरीय Gantt चार्ट या माइलस्टोन योजना में अक्सर हफ़्तों का उपयोग किया जाता है।

## चरण 8: महीनों में अवधि – महीनों में अवधि कैसे प्राप्त करें?
```java
// Get the duration in Months
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```

जब आप प्रोजेक्ट चरणों को वित्तीय अवधियों के साथ संरेखित कर रहे हों, तो महीने‑स्तर की अवधि मददगार होती है।

## सामान्य समस्याएँ और समाधान
| लक्षण | संभावित कारण | समाधान |
|---------|--------------|-----|
| `task` पर NullPointerException | गलत कार्य ID या चाइल्ड्स की कमी | `project.getRootTask().getChildren()` का उपयोग करके जांचें कि कार्य ID मौजूद है। |
| अप्रत्याशित मान (जैसे, 0) | प्रोजेक्ट एक कस्टम कैलेंडर उपयोग करता है जिसमें गैर‑कार्य दिवस हैं | सुनिश्चित करें कि प्रोजेक्ट का कैलेंडर सही ढंग से परिभाषित है या निरीक्षण के लिए `project.getCalendar()` का उपयोग करें। |
| रूपांतरण अंशात्मक हफ़्ते लौटाता है | हफ़्ते प्रोजेक्ट की डिफ़ॉल्ट हफ़्ता लंबाई (आमतौर पर 5 दिन) के आधार पर गणना किए जाते हैं | यदि आपको कैलेंडर हफ़्ते चाहिए तो 5 से गुणा करें, या कैलेंडर सेटिंग्स समायोजित करें। |

## अक्सर पूछे जाने वाले प्रश्न
### Q: क्या मैं Aspose.Tasks for Java को किसी भी Java IDE के साथ उपयोग कर सकता हूँ?
A: हाँ, Aspose.Tasks for Java किसी भी Java Integrated Development Environment (IDE) के साथ संगत है।

### Q: Microsoft Project फ़ाइल में कार्य का ID कैसे प्राप्त करूँ?
A: आप प्रोजेक्ट फ़ाइल को मैन्युअल रूप से निरीक्षण कर सकते हैं या `project.getRootTask().getChildren()` को कॉल करके कलेक्शन पर इटरेट कर प्रत्येक कार्य का `ID` पढ़ सकते हैं।

### Q: क्या Aspose.Tasks बड़े‑पैमाने के प्रोजेक्ट्स को संभालने के लिए उपयुक्त है?
A: बिल्कुल। Aspose.Tasks हज़ारों कार्यों और संसाधनों वाले प्रोजेक्ट्स को कुशलता से प्रोसेस करने के लिए डिज़ाइन किया गया है।

### Q: आगे का दस्तावेज़ कहाँ मिल सकता है?
A: व्यापक API रेफ़रेंसेज़, कोड नमूने, और बेस्ट‑प्रैक्टिस गाइड्स के लिए [documentation](https://reference.aspose.com/tasks/java/) देखें।

### Q: क्या मैं खरीदने से पहले Aspose.Tasks for Java को आज़मा सकता हूँ?
A: हाँ, आप इसकी क्षमताओं का मूल्यांकन करने के लिए एक [free trial](https://releases.aspose.com/) का उपयोग कर सकते हैं।

**अंतिम अपडेट:** 2026-02-28  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}