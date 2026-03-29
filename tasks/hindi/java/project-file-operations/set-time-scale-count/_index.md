---
date: 2026-03-29
description: Aspose.Tasks for Java का उपयोग करके Gantt चार्ट के टाइम‑स्केल काउंट को
  कस्टमाइज़ करते हुए प्रोजेक्ट PDF फ़ाइलें बनाना सीखें। यह गाइड आपको चरण‑दर‑चरण दिखाता
  है कि कैसे पूर्ण नियंत्रण के साथ Gantt को PDF में निर्यात किया जाए।
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: प्रोजेक्ट PDF बनाएं – गैंट चार्ट का समय स्केल अनुकूलित करें
url: /hi/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# प्रोजेक्ट PDF बनाएं – गैंट चार्ट टाइम स्केल को कस्टमाइज़ करें

## परिचय
यदि आपको **create project PDF** फ़ाइलें चाहिए जो एक पूरी तरह से ट्यून किए गए गैंट चार्ट को दर्शाती हों, तो टाइम‑स्केल काउंट को नियंत्रित करना मुख्य है। Aspose.Tasks for Java के साथ आप प्रोग्रामेटिक रूप से नीचे और मध्य टाइम‑स्केल टियर्स सेट कर सकते हैं, टिक मार्क्स को छिपा सकते हैं, और फिर आसान वितरण के लिए **save project as PDF** कर सकते हैं। इस ट्यूटोरियल में हम सब कुछ बताएँगे—डेवलपमेंट एनवायरनमेंट सेटअप से लेकर एक पॉलिश्ड PDF जनरेट करने तक जो आपके कस्टमाइज़्ड गैंट व्यू को दिखाता है।

## त्वरित उत्तर
- **“customize Gantt chart” का क्या मतलब है?** Adjusting time‑scale tiers, colors, and layout to match your reporting needs.  
- **निचले टियर काउंट को सेट करने वाला कौन सा API मेथड है?** `view.getBottomTimescaleTier().setCount(int)`.  
- **क्या मैं प्रोजेक्ट से सीधे PDF जेनरेट कर सकता हूँ?** Yes—use `project.save(..., SaveFileFormat.Pdf)`.  
- **उत्पादन उपयोग के लिए मुझे लाइसेंस चाहिए?** A commercial license is required; a free trial is available.  
- **कौन सा Java संस्करण समर्थित है?** Java 8 or higher works with the latest Aspose.Tasks library.

## Aspose.Tasks में “customize Gantt chart” क्या है?
गैंट चार्ट को कस्टमाइज़ करना मतलब है प्रोग्रामेटिक रूप से उसके दृश्य घटकों—जैसे टाइम‑स्केल अंतराल, टिक मार्क्स, और टास्क बार—को बदलना, ताकि चार्ट उस तरीके से मेल खाए जिसमें आप **manage project visualization** करना चाहते हैं। टाइम‑स्केल काउंट बदलकर आप नियंत्रित करते हैं कि प्रत्येक सेगमेंट कितने दिन, सप्ताह या महीने दर्शाता है, जिससे विभिन्न दर्शकों के लिए चार्ट अधिक स्पष्ट हो जाता है।

## कस्टमाइज़्ड गैंट चार्ट के साथ प्रोजेक्ट PDF क्यों बनाएं?
- **स्टेकहोल्डर‑रेडी आउटपुट:** PDF सार्वभौमिक रूप से देखा जा सकता है, जिससे सभी को एक ही शेड्यूल लेआउट दिखता है।  
- **प्रिंट‑फ्रेंडली:** टाइम‑स्केल टियर्स पर सटीक नियंत्रण भीड़भाड़ या अस्पष्ट प्रिंटआउट्स को रोकता है।  
- **ऑटोमेशन:** PDF जेनरेशन को CI पाइपलाइन्स या रिपोर्टिंग सर्विसेज़ में इंटीग्रेट करें, जिससे शून्य‑मैन्युअल प्रयास हो।

## आवश्यकताएँ
Before you begin, make sure you have:

1. **Java Development Environment** – JDK 8 या उससे नया स्थापित हो।  
2. **Aspose.Tasks for Java Library** – इसे [यहाँ](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. **Basic Java Knowledge** – Java सिंटैक्स और ऑब्जेक्ट‑ओरिएंटेड कॉन्सेप्ट्स की परिचितता।

## पैकेज इम्पोर्ट करें
Import the necessary classes into your Java project:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## स्टेप‑बाय‑स्टेप गाइड

### स्टेप 1: डेटा डायरेक्टरी सेट करें
Define where your project files will be read from and written to:

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` को अपने मशीन पर पूर्ण पाथ से बदलें।

### स्टेप 2: नया प्रोजेक्ट इंस्टेंस बनाएं
एक नया `Project` ऑब्जेक्ट इंस्टैंशिएट करें जो सभी टास्क और व्यू सेटिंग्स को रखेगा:

```java
Project project = new Project();
```

### स्टेप 3: गैंट चार्ट व्यू कॉन्फ़िगर करें
एक `GanttChartView` ऑब्जेक्ट बनाएं—यहाँ आप चार्ट की उपस्थिति को नियंत्रित करने के लिए **generate Gantt view Java** कोड जनरेट करेंगे:

```java
GanttChartView view = new GanttChartView();
```

### स्टेप 4: नीचे टियर के लिए टाइम स्केल काउंट सेट करें
नीचे टियर को दो अंतराल दिखाने और टिक मार्क्स को छिपाने के लिए समायोजित करें:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### स्टेप 5: मध्य टियर के लिए टाइम स्केल काउंट सेट करें
इसी कॉन्फ़िगरेशन को मध्य टियर पर लागू करें:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### स्टेप 6: कस्टमाइज़्ड व्यू को प्रोजेक्ट में जोड़ें
व्यू को जो आपने अभी कॉन्फ़िगर किया है, उसे `Project` इंस्टेंस से अटैच करें:

```java
project.getViews().add(view);
```

### स्टेप 7: सैंपल टास्क जोड़ें (टेस्ट डेटा)
विशिष्ट अवधि वाले कुछ टास्क बनाएं ताकि कस्टमाइज़्ड गैंट चार्ट को दर्शाया जा सके:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### स्टेप 8: प्रोजेक्ट को PDF के रूप में सेव करें
अंत में, प्रोजेक्ट को—जिसमें आपका **customized Gantt chart** शामिल है—एक PDF फ़ाइल में एक्सपोर्ट करें:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

परिणामी PDF दर्शाता है कि नीचे और मध्य टाइम‑स्केल टियर्स को कैसे **customized** किया गया है, जिससे स्टेकहोल्डर्स को शेड्यूल का स्पष्ट, प्रिंटेबल व्यू मिलता है।

## सामान्य समस्याएँ और ट्रबलशूटिंग
- **PDF is blank** – सुनिश्चित करें कि `dataDir` पाथ फ़ाइल सेपरेटर (`/` या `\`) पर समाप्त हो और डायरेक्टरी मौजूद हो।  
- **Ticks still appear** – जांचें कि `setShowTicks(false)` दोनों टियर्स पर कॉल किया गया है।  
- **Duration not applied** – पुष्टि करें कि आप ड्यूरेशन बनाते समय `TimeUnitType.Hour` (या उपयुक्त यूनिट) का उपयोग कर रहे हैं।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.Tasks for Java बड़े‑स्केल प्रोजेक्ट फ़ाइलों को संभाल सकता है?**  
A: हाँ, लाइब्रेरी बड़े प्रोजेक्ट डेटा की हाई‑परफ़ॉर्मेंस प्रोसेसिंग के लिए ऑप्टिमाइज़्ड है।

**Q: क्या Aspose.Tasks for Java विभिन्न Java IDEs के साथ संगत है?**  
A: बिल्कुल – यह Eclipse, IntelliJ IDEA, NetBeans और अन्य लोकप्रिय IDEs के साथ सहजता से काम करता है।

**Q: क्या मैं टाइम‑स्केल सेटिंग्स से आगे गैंट चार्ट की उपस्थिति को कस्टमाइज़ कर सकता हूँ?**  
A: हाँ, Aspose.Tasks बार रंग, फ़ॉन्ट और ग्रिड लाइन्स जैसी विस्तृत स्टाइलिंग विकल्प प्रदान करता है।

**Q: क्या Aspose.Tasks for Java के लिए कोई ट्रायल संस्करण उपलब्ध है?**  
A: हाँ, आप [यहाँ](https://releases.aspose.com/) से मुफ्त ट्रायल संस्करण प्राप्त कर सकते हैं।

**Q: Aspose.Tasks for Java के लिए समर्थन कहाँ प्राप्त कर सकता हूँ?**  
A: आप Aspose.Tasks फ़ोरम पर समर्थन और सहायता पा सकते हैं [यहाँ](https://forum.aspose.com/c/tasks/15)।

**Q: मैं प्रोग्रामेटिक रूप से गैंट चार्ट की बैकग्राउंड कलर कैसे बदलूँ?**  
A: `java.awt.Color` इम्पोर्ट करने के बाद `view.getGanttChartProperties().setBackgroundColor(Color)` मेथड का उपयोग करें।

## निष्कर्ष
इन चरणों का पालन करके आपने **create project PDF** फ़ाइलें बनाना सीखा है, जिसमें पूरी तरह से कस्टमाइज़्ड गैंट चार्ट टाइम‑स्केल शामिल है, **project visualization** को बेहतर बनाया है, और Aspose.Tasks for Java का उपयोग करके **save project as PDF** किया है। यह तरीका आपको विज़ुअल आउटपुट पर पूर्ण नियंत्रण देता है, जिससे आप अपनी टीम या क्लाइंट्स के साथ स्पष्ट, प्रोफेशनल शेड्यूल आसानी से साझा कर सकते हैं।

---

**अंतिम अपडेट:** 2026-03-29  
**परीक्षण किया गया:** Aspose.Tasks for Java (latest)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}