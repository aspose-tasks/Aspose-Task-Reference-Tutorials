---
date: 2026-02-26
description: Aspose.Tasks for Java में कार्य को पुनः प्रारम्भ करने और रोकने के तरीके
  सीखें, साथ ही सटीक प्रोजेक्ट नियंत्रण के लिए तिथि के आधार पर कार्यों को फ़िल्टर
  करना भी सीखें।
linktitle: How to Resume Task and Stop Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में कार्य को पुनः प्रारंभ करने और कार्य को रोकने का तरीका
url: /hi/java/task-properties/stop-resume-task/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में टास्क को पुनः शुरू करने और रोकने का तरीका

## परिचय
यदि आप Java‑आधारित प्रोजेक्ट मैनेजमेंट समाधान बना रहे हैं, तो आपको अक्सर किसी टास्क को अस्थायी रूप से **pause** करना और बाद में **continue** करना पड़ता है। Aspose.Tasks for Java इन कार्यों को रोकने और पुनः शुरू करने के लिए निर्मित प्रॉपर्टीज़ के साथ इसे आसान बनाता है। इस ट्यूटोरियल में आप प्रोग्रामेटिक रूप से **how to resume task** और **how to stop task** सीखेंगे, और साथ ही **filter tasks by date** का उपयोग करके केवल संबंधित आइटम्स के साथ काम करना भी देखेंगे।

## त्वरित उत्तर
- **टास्क के लिए “stop” का क्या अर्थ है?** यह एक stop date सेट करता है, जिससे उस बिंदु के बाद कार्य रोक दिया जाता है।  
- **रोके गए टास्क को कैसे पुनः शुरू करूँ?** stop date से बाद की एक resume date असाइन करके।  
- **क्या मैं ऑपरेशन को एक डेट रेंज तक सीमित कर सकता हूँ?** हाँ – टास्क फ़िल्टर करने के लिए न्यूनतम तिथि का उपयोग करें।  
- **कौन सा लाइब्रेरी संस्करण आवश्यक है?** कोई भी नवीनतम Aspose.Tasks for Java रिलीज़ (API स्थिर रहता है)।  
- **क्या विकास के लिए लाइसेंस चाहिए?** परीक्षण के लिए फ्री ट्रायल काम करता है; उत्पादन के लिए लाइसेंस आवश्यक है।

## Aspose.Tasks में “how to resume task” क्या है?
टास्क को पुनः शुरू करना बस इसका मतलब है कि `Task` ऑब्जेक्ट पर **RESUME** तिथि प्रदान करना। जब प्रोजेक्ट इंजन शेड्यूल को प्रोसेस करता है, तो कार्य उस तिथि से आगे जारी रहेगा। यह संसाधन की अनुपलब्धता या बाहरी निर्भरताओं जैसी बाधाओं को संभालने में विशेष रूप से उपयोगी है।

## stop/resume फीचर क्यों उपयोग करें?
- **समय‑रेखा पर नियंत्रण:** टास्क को हटाए बिना कार्य को रोकें।  
- **सटीक रिपोर्टिंग:** गैंट चार्ट में वास्तविक प्रारंभ/समाप्ति तिथियाँ दिखाएँ।  
- **आसान ऑटोमेशन:** कई टास्क को एक साथ अपडेट करने के लिए डेट फ़िल्टर के साथ संयोजित करें।

## पूर्वापेक्षाएँ
- Java मूलभूत ज्ञान का ठोस समझ।  
- अपने मशीन पर JDK स्थापित होना चाहिए।  
- अपने प्रोजेक्ट में Aspose.Tasks for Java लाइब्रेरी जोड़ें (इसे [here](https://releases.aspose.com/tasks/java/) से डाउनलोड करें)。

## इम्पोर्ट पैकेजेज
पहले, आवश्यक क्लासेज़ को स्कोप में लाएँ ताकि आप प्रोजेक्ट्स और टास्क्स के साथ काम कर सकें।

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```

## चरण 1: प्रोजेक्ट और कलेक्टर को इनिशियलाइज़ करें
अपने MPP फ़ाइल की ओर इशारा करने वाला एक `Project` इंस्टेंस बनाएँ और एक `ChildTasksCollector` सेट अप करें ताकि पदानुक्रम में हर टास्क को इकट्ठा किया जा सके।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

## चरण 2: फ़िल्टरिंग के लिए न्यूनतम तिथि निर्धारित करें
यदि आप केवल उन टास्क्स के साथ काम करना चाहते हैं जिनकी अर्थपूर्ण stop या resume तिथियाँ हैं, तो **न्यूनतम तिथि** निर्धारित करें। यह *filter tasks by date* तकनीक का मूल है।

```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```

## चरण 3: इटरेट करें, जाँचें, और Stop/Resume मान प्रदर्शित करें
अब एकत्रित टास्क्स के माध्यम से लूप करें, **how to stop task** लॉजिक लागू करें, और तिथियों को प्रिंट करें। कोड **how to resume task** को भी `RESUME` प्रॉपर्टी पढ़कर दर्शाता है।

```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```

> **Pro tip:** `System.out.println` कॉल्स को अपनी लॉजिक से बदलें (जैसे, तिथियों को अपडेट करना, फ़ाइल में लॉग करना, या टास्क ऑब्जेक्ट्स को संशोधित करना) ताकि आवश्यकतानुसार टास्क को *stop* या *resume* किया जा सके।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|-------|-----|
| `tsk.get(Tsk.STOP)` पर `NullPointerException` | टास्क में कोई stop date सेट नहीं है। | `.before(minDate)` कॉल करने से पहले `null` की जाँच करें। |
| सेट करने के बाद भी तिथियाँ `NA` दिख रही हैं | न्यूनतम तिथि बहुत हाल की है। | एक पहले की `minDate` उपयोग करें या फ़िल्टर हटाएँ। |
| सहेजे गए MPP में परिवर्तन प्रतिबिंबित नहीं हो रहे हैं | परिवर्तनों के बाद प्रोजेक्ट सहेजा नहीं गया। | टास्क अपडेट करने के बाद `project.save("output.mpp");` कॉल करें। |

## अक्सर पूछे जाने वाले प्रश्न

### क्या Aspose.Tasks for Java बड़े‑स्तर के प्रोजेक्ट्स के लिए उपयुक्त है?
बिल्कुल! Aspose.Tasks for Java विभिन्न आकार के प्रोजेक्ट्स को संभालने के लिए डिज़ाइन किया गया है, जिससे दक्षता और विश्वसनीयता सुनिश्चित होती है।

### क्या मैं टास्क को रोकने और पुनः शुरू करने की तिथि को कस्टमाइज़ कर सकता हूँ?
हाँ, दिया गया उदाहरण आपके प्रोजेक्ट की आवश्यकताओं के अनुसार न्यूनतम तिथि सेट करने में लचीलापन प्रदान करता है।

### Aspose.Tasks for Java के लिए अतिरिक्त समर्थन कहाँ मिल सकता है?
समुदाय समर्थन और चर्चा के लिए [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) पर जाएँ।

### क्या Aspose.Tasks for Java के लिए फ्री ट्रायल उपलब्ध है?
हाँ, आप खरीदारी से पहले फीचर्स को एक्सप्लोर करने के लिए [free trial](https://releases.aspose.com/) का उपयोग कर सकते हैं।

### मैं Aspose.Tasks for Java के लिए टेम्पररी लाइसेंस कैसे प्राप्त कर सकता हूँ?
आप परीक्षण के लिए टेम्पररी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

**Additional Q&A**

**Q: मैं टास्क के लिए नई stop date कैसे सेट करूँ?**  
A: `tsk.set(Tsk.STOP, new Date(...));` का उपयोग करें और फिर प्रोजेक्ट को सहेजें।

**Q: क्या मैं केवल न्यूनतम तिथि के बजाय एक विशिष्ट रेंज द्वारा टास्क फ़िल्टर कर सकता हूँ?**  
A: हाँ—अपने प्रारंभ और समाप्ति तिथियों के विरुद्ध `before` और `after` दोनों की तुलना करें।

**Q: क्या stop/resume तिथियों को बदलने के बाद API स्वचालित रूप से शेड्यूल को पुनः गणना करता है?**  
A: तिथियों को बदलने के बाद, शेड्यूल को रीफ़्रेश करने के लिए `project.calculateCriticalPath();` कॉल करें।

## निष्कर्ष
इस गाइड में हमने Aspose.Tasks for Java का उपयोग करके **how to resume task** और **how to stop task** को कवर किया, साथ ही **filter tasks by date** की व्यावहारिक विधि भी प्रस्तुत की। इन स्निपेट्स को अपने एप्लिकेशन में एकीकृत करके आप प्रोजेक्ट टाइमलाइन पर सूक्ष्म नियंत्रण प्राप्त कर सकते हैं और शेड्यूल समायोजन को आत्मविश्वास के साथ ऑटोमेट कर सकते हैं।

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}