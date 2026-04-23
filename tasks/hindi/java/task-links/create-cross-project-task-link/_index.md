---
date: 2026-01-20
description: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट्स को लिंक करना और प्रोजेक्ट्स
  के बीच टास्क को लिंक करना सीखें। क्रॉस‑प्रोजेक्ट टास्क लिंक बनाने के लिए चरण‑दर‑चरण
  गाइड का पालन करें।
linktitle: Create Cross-Project Task Link in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'परियोजनाओं को लिंक कैसे करें: Aspose.Tasks में क्रॉस‑प्रोजेक्ट टास्क लिंक
  बनाएं'
url: /hi/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# प्रोजेक्ट्स को लिंक कैसे करें: Aspose.Tasks में क्रॉस-प्रोजेक्ट टास्क लिंक बनाएं

## Aspose.Tasks के साथ प्रोजेक्ट्स को कैसे लिंक योजनाओं सटीक चरण सीखेंगे, आवश्यक कोड स्निपेट्स देखेंगे, और समझेंगे कि यह तकनीक टीम के सदस्यों के बीच सहयोग को कैसे नाटकीय रूप से सुधार सकती है।

## त्वरित उत्तर
- **मुख्य लाभ क्या है?** विभिन्न प्रोजेक्ट फ़ाइलों में निर्भर कार्य आइटम्स को सहजता से समकालिक किया जा सकता है।  
- **कौनसी लाइब्रेरी आवश्यक है?** Aspose.Tasks for Java (नवीनतम संस्करण)।  
- **क्या मुझे लाइसेंस चाहिए?** प्रोडक्शन उपयोग के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है।  
- **इसे लागू करने में कितना समय लगेगा?** बुनियादी लिंक के लिए लगभग 10–15 मिनट।  
- **क्या मैं विभिन्न फ़ाइल फ़ॉर्मेट्स के बीच टास्क लिंक कर सकता हूँ?** हाँ – API MPP, XML और अन्य फ़ॉर्मेट्स को सपोर्ट करता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित तैयार हैं:

- Java प्रोग्रामिंग का कार्यशील ज्ञान।  
- Aspose.Tasks for Java स्थापित है। आप इसे [Aspose.Tasks for Java release page](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।  
- प्रोजेक्ट मैनेजमेंट अवधारणाओं जैसे टास्क डिपेंडेंसीज़ और समरी टास्क्स की बुनियादी समझ।

## पैकेज इम्पोर्ट करें
पहले, उन क्लासेज़ को इम्पोर्ट करें जिनकी आपको आवश्यकता होगी। यह आपको कोर Aspose.Tasks कार्यक्षमता तक पहुँच देता है:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

## चरण 1: अपना वातावरण सेट अप करें
सुनिश्चित करें कि आपके मशीन पर Java स्थापित है और Aspose.Tasks JAR आपके प्रोजेक्ट के क्लासपाथ में जोड़ा गया है। यह चरण कोड को बिना त्रुटियों के कंपाइल करने के लिए महत्वपूर्ण है।

## चरण 2: एक Project इंस्टेंस बनाएं
एक नया `Project` ऑब्जेक्ट बनाएं जो टास्क और लिंक को रखेगा:

```java
Project project = new Project();
```

## चरण 3: एक Summary Task जोड़ें
एक summary task उन टास्क्स के लिए कंटेनर के रूप में कार्य करता है जिन्हें आप लिंक करेंगे। यह प्रोजेक्ट को बाद में देखने पर संरचना को स्पष्ट बनाता है:

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

## चरण 4: External Task जोड़ें
अब एक external task जोड़ें जो किसी अन्य प्रोजेक्ट फ़ाइल में टास्क की ओर इशारा करता है। यह क्रॉस‑प्रोजेक्ट लिंक का “source” पक्ष है:

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

## चरण 5: Local Task जोड़ें
एक local task बनाएं जिसे external task से लिंक किया जाएगा। यह संबंध का “target” पक्ष है:

```java
Task t = summary.getChildren().add("Task");
```

## चरण 6: टास्क लिंक बनाएं
external task और local task के बीच लिंक स्थापित करें। `CrossProject` को `true` सेट करने से Aspose.Tasks को पता चलता है कि लिंक दो अलग-अलग प्रोजेक्ट फ़ाइलों को जोड़ता है:

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

## चरण 7: परिणाम दिखाएँ
अंत में, एक सरल पुष्टि आउटपुट करें ताकि आप जान सकें कि प्रक्रिया बिना अपवादों के पूरी हुई:

```java
System.out.println("Process completed Successfully");
```

## प्रोजेक्ट्स के बीच टास्क लिंक क्यों करें?
प्रोजेक्ट्स के बीच टास्क लिंक करने से आप:
- निर्भर कार्य आइटम्स को मैन्युअल अपडेट्स के बिना समकालिक रखें।  
- जब एक ही टास्क कई योजनाओं में दिखाई देता है तो प्रयास की दोहराव को कम करें।  
- टीमों के बीच माइलस्टोन ट्रैकिंग के लिए एकल सत्य स्रोत प्रदान करें।  

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| External task नहीं मिला | सुनिश्चित करें कि `EXTERNAL_TASK_PROJECT` पाथ और `EXTERNAL_ID` सही हैं। |
| Link प्रकार मेल नहीं खाता | सुनिश्चित करें कि `TaskLinkType` वांछित डिपेंडेंसी (जैसे Finish‑to‑Start) से मेल खाता है। |
| License अपवाद | Project इंस्टेंस बनाने से पहले एक वैध Aspose.Tasks लाइसेंस इंस्टॉल करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं एक ही summary task में कई external projects से टास्क लिंक कर सकता हूँ?**  
A: हाँ, आप समान summary task के भीतर विभिन्न external projects से टास्क लिंक कर सकते हैं, समान प्रक्रिया का पालन करते हुए।

**Q: यदि लिंक किए गए प्रोजेक्ट में external task में बदलाव किया जाता है तो क्या होता है?**  
A: external task में किए गए किसी भी बदलाव को आपके वर्तमान प्रोजेक्ट में लिंक किए गए टास्क में प्रतिबिंबित किया जाएगा।

**Q: क्या विभिन्न फ़ाइल फ़ॉर्मेट्स में टास्क के बीच लिंक बनाना संभव है?**  
A: हाँ, Aspose.Tasks for Java विभिन्न फ़ाइल फ़ॉर्मेट्स में प्रोजेक्ट्स के बीच टास्क लिंक करने का समर्थन करता है।

**Q: क्या मैं प्रोजेक्ट्स के बीच लिंक गए टास्क को अनलिंक कर सकता हूँ?**  
A: हाँ, आप उपयुक्त Aspose.Tasks मेथड्स का उपयोग करके टास्क लिंक हटाकर टास्क को अनलिंक कर सकते हैं।

**Q: क्या प्रोजेक्ट्स के बीच लिंक किए जा सकने वाले टास्क की संख्या पर कोई सीमा है?**  
A: लिंक किए जा सकने वाले टास्क की संख्या आपके Aspose.Tasks लाइसेंस की क्षमताओं और सीमाओं पर निर्भर करती है।

## निष्कर्ष
अब आप Aspose.Tasks for Java का उपयोग करके **प्रोजेक्ट्स को लिंक करने** और **प्रोजेक्ट्स के बीच टास्क लिंक करने** के बारे में जानते हैं। क्रॉस‑प्रोजेक्ट टास्क लिंक बनाकर आप सुगम सहयोग को सक्षम करते हैं, मैन्युअल समन्वयन प्रयास को कम करते हैं, और अपने प्रोजेक्ट योजनाओं को संरेखित रखते हैं। विभिन्न लिंक प्रकारों के साथ प्रयोग करने और अपने प्रोजेक्ट‑मैनेजमेंट वर्कफ़्लो को और बेहतर बनाने के लिए अतिरिक्त Aspose.Tasks सुविधाओं को एक्सप्लोर करने में संकोच न करें।

---

**अंतिम अपडेट:** 2026-01-20  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.12 (नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}