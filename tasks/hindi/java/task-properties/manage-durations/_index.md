---
date: 2026-02-20
description: Aspose.Tasks for Java के साथ प्रोजेक्ट में टास्क जोड़ने और अवधि प्रबंधित
  करने के तरीकों का अन्वेषण करें। सीखें कि अवधि कैसे सेट करें और अवधि को आसानी से
  कैसे परिवर्तित करें।
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks के साथ प्रोजेक्ट में कार्य जोड़ें और अवधि प्रबंधित करें
url: /hi/java/task-properties/manage-durations/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# प्रोजेक्ट में टास्क जोड़ें और Aspose.Tasks के साथ अवधि प्रबंधित करें

## परिचय
इस ट्यूटोरियल में आप **प्रोजेक्ट में टास्क कैसे जोड़ें** और Aspose.Tasks for Java का उपयोग करके उसकी अवधि कैसे नियंत्रित करें, सीखेंगे। चाहे आप नया प्रोजेक्ट‑प्लानिंग टूल बना रहे हों या मौजूदा समाधान का विस्तार कर रहे हों, टास्क‑अवधि को संभालना सटीक शेड्यूलिंग और रिपोर्टिंग के लिए आवश्यक है।

## त्वरित उत्तर
- **“प्रोजेक्ट में टास्क जोड़ना” का क्या अर्थ है?** यह प्रोजेक्ट की रूट या किसी विशिष्ट समरी टास्क के तहत एक नया टास्क ऑब्जेक्ट बनाता है।  
- **कौन सा क्लास अवधि को दर्शाता है?** `com.aspose.tasks.Duration`।  
- **अवधि कैसे सेट करें?** `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))` का उपयोग करें।  
- **क्या मैं अवधि को किसी अन्य इकाई में बदल सकता हूँ?** हाँ, `duration.convert(TimeUnitType.Hour)` या किसी भी अन्य `TimeUnitType` को कॉल करें।  
- **क्या उत्पादन के लिए लाइसेंस चाहिए?** व्यावसायिक उपयोग के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है।

## “प्रोजेक्ट में टास्क जोड़ना” क्या है?
प्रोजेक्ट में टास्क जोड़ना का अर्थ है एक `Task` ऑब्जेक्ट बनाना और उसे प्रोजेक्ट की टास्क हायरार्की में संलग्न करना। यह ऑपरेशन वह पहला कदम है जिसके बाद आप उस टास्क के लिए कार्य, संसाधन या अवधि निर्धारित कर सकते हैं।

## टास्क अवधि क्यों प्रबंधित करें?
सटीक अवधि वास्तविक टाइमलाइन, संसाधन आवंटन और क्रिटिकल‑पाथ विश्लेषण को चलाती है। Aspose.Tasks के साथ आप प्रोग्रामेटिक रूप से अवधि सेट, पढ़, बदल और समायोजित कर सकते हैं, जिससे प्रोजेक्ट शेड्यूल पर पूर्ण नियंत्रण मिलता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हों:

- Java Development Kit (JDK): सुनिश्चित करें कि आपके मशीन पर Java स्थापित है। आप इसे [here](https://www.oracle.com/java/technologies/javase-downloads.html) से डाउनलोड कर सकते हैं।  
- Aspose.Tasks लाइब्रेरी: Aspose.Tasks लाइब्रेरी को डाउनलोड करें और अपने प्रोजेक्ट में शामिल करें। लाइब्रेरी आप [here](https://releases.aspose.com/tasks/java/) पर पा सकते हैं।

## पैकेज इम्पोर्ट करें
अपने Java प्रोजेक्ट में Aspose.Tasks के साथ काम करने के लिए आवश्यक पैकेज इम्पोर्ट करें:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## चरण 1: अपना प्रोजेक्ट सेट अप करें
```java
// Create a new project
Project project = new Project();
```

## चरण 2: नया टास्क जोड़ें (add task to project)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## अवधि कैसे सेट करें
अब टास्क मौजूद है, आप उसकी लंबाई निर्धारित कर सकते हैं। डिफ़ॉल्ट रूप से, अवधि दिनों में व्यक्त की जाती है।

## चरण 3: टास्क अवधि प्राप्त करें और बदलें
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## अवधि कैसे बदलें
`convert` मेथड आपको एक `Duration` को एक `TimeUnitType` से दूसरे में बदलने की अनुमति देता है (जैसे, दिन → घंटे, सप्ताह → दिन)।

## चरण 4: टास्क अवधि को 1 सप्ताह में अपडेट करें
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## चरण 5: टास्क अवधि घटाएँ
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

इन चरणों का पालन करके आपने सफलतापूर्वक **प्रोजेक्ट में टास्क जोड़ा** और Aspose.Tasks for Java का उपयोग करके उसकी अवधि प्रबंधित की।

## सामान्य त्रुटियाँ और सुझाव
- **त्रुटि:** गणितीय संचालन से पहले अवधि को बदलना न भूलें, अन्यथा गलत परिणाम मिल सकते हैं। हमेशा `duration.getTimeUnit()` से इकाई सत्यापित करें।  
- **सुझाव:** बाद में बदलने की बजाय इच्छित इकाई में अवधि बनाने के लिए `project.getDuration(value, TimeUnitType)` का उपयोग करें।  
- **त्रुटि:** नकारात्मक अवधि सेट करने पर एक्सेप्शन फेंका जाएगा। इनपुट मानों को वैधता जांचें।

## निष्कर्ष
इस गाइड में हमने **प्रोजेक्ट में टास्क जोड़ना**, उसकी डिफ़ॉल्ट अवधि पढ़ना, **अवधि सेट करना**, और विभिन्न समय इकाइयों में **अवधि बदलना** कवर किया। अब आप इन तकनीकों को बड़े शेड्यूलिंग एप्लिकेशन में एकीकृत करके सटीक प्रोजेक्ट प्लानिंग कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.Tasks सभी Java संस्करणों के साथ संगत है?
Aspose.Tasks Java 6 और उसके बाद के संस्करणों के साथ संगत है।

### क्या मैं Aspose.Tasks को व्यावसायिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?
हां, आप Aspose.Tasks को व्यक्तिगत और व्यावसायिक दोनों प्रकार के प्रोजेक्ट्स में उपयोग कर सकते हैं। लाइसेंस विवरण के लिए [here](https://purchase.aspose.com/buy) देखें।

### अतिरिक्त समर्थन और संसाधन कहाँ मिलेंगे?
समुदाय समर्थन और चर्चा के लिए [Aspose.Tasks फोरम](https://forum.aspose.com/c/tasks/15) देखें।

### परीक्षण उद्देश्यों के लिए अस्थायी लाइसेंस कैसे प्राप्त करें?
परीक्षण और मूल्यांकन के लिए आप अस्थायी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

### क्या Aspose.Tasks के लिए मुफ्त ट्रायल उपलब्ध है?
हां, आप खरीदारी से पहले Aspose.Tasks का अन्वेषण करने के लिए मुफ्त ट्रायल [here](https://releases.aspose.com/) पर एक्सेस कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: सेट की गई अवधि को बाद में कैसे बदलें?**  
उत्तर: वर्तमान अवधि को `task.get(Tsk.DURATION)` से प्राप्त करें, उसे संशोधित करें (जैसे, `add`, `subtract`, या `convert`), और फिर `task.set(Tsk.DURATION, newDuration)` से वापस सेट करें।

**प्रश्न: क्या मैं मिनट में अवधि सेट कर सकता हूँ?**  
उत्तर: हां, `project.getDuration(value, TimeUnitType.Minute)` कॉल करते समय `TimeUnitType.Minute` का उपयोग करें।

**प्रश्न: क्या अवधि बदलने से टास्क की प्रारंभ और समाप्ति तिथियां स्वचालित रूप से अपडेट हो जाती हैं?**  
उत्तर: केवल तभी जब प्रोजेक्ट की शेड्यूलिंग मोड ऑटोमैटिक पर सेट हो। अन्यथा आपको `project.calculateCriticalPath()` से शेड्यूल पुनः गणना करनी पड़ सकती है।

**प्रश्न: क्या अवधि को कच्चे संख्या के रूप में प्राप्त करना संभव है?**  
उत्तर: वर्तमान समय इकाई में संख्यात्मक मान पाने के लिए `duration.getTimeSpan()` कॉल करें।

**प्रश्न: यदि मैं वर्तमान अवधि से अधिक घटा दूँ तो क्या होगा?**  
उत्तर: API `ArgumentOutOfRangeException` फेंकेगा। हमेशा यह सुनिश्चित करें कि परिणामी अवधि सकारात्मक बनी रहे।

---

**अंतिम अपडेट:** 2026-02-20  
**परीक्षित संस्करण:** Aspose.Tasks for Java (नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}