---
date: 2025-12-23
description: Aspose.Tasks for Java का उपयोग करके MS Project फ़ाइलों को अपडेट करना
  और अधूरे कार्य को पुनः निर्धारित करना सीखें। साथ ही देखें कि MS Project XML को कैसे
  सहेजा जाए।
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks के साथ MS Project को अपडेट करें और कार्य को पुनर्निर्धारित करें
url: /hi/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ MS Project को अपडेट करें और कार्य को पुनः‑निर्धारित करें

## परिचय
Microsoft Project एक व्यापक रूप से उपयोग किया जाने वाला प्रोजेक्ट‑मैनेजमेंट टूल है जो टीमों को कार्यों की योजना बनाने, ट्रैक करने और समय पर डिलीवर करने में मदद करता है। जब शेड्यूल बदलते हैं, तो अक्सर आपको **update MS Project** फ़ाइलों को प्रोग्रामेटिक रूप से अपडेट करने की आवश्यकता होती है—कार्य को पूर्ण के रूप में चिह्नित करना, शेष कार्यों को आगे बढ़ाना, और प्रोजेक्ट बेसलाइन को सटीक रखना। Aspose.Tasks for Java आपको बिना GUI खोले यह सब करने के लिए एक साफ़, टाइप‑सेफ़ API प्रदान करता है। इस ट्यूटोरियल में आप देखेंगे कि प्रोजेक्ट को कैसे अपडेट किया जाए, किसी विशिष्ट तिथि तक कार्य को समाप्त कैसे चिह्नित किया जाए, और फिर **how to reschedule MS Project** कार्य को कैसे पुनः‑निर्धारित किया जाए।

## त्वरित उत्तर
- **“update MS Project” का क्या अर्थ है?** यह निर्दिष्ट तिथि तक कार्यों को पूर्ण के रूप में चिह्नित करता है और परिवर्तन को फ़ाइल में लिख देता है।  
- **क्या मैं शेष कार्य को स्वचालित रूप से पुनः‑निर्धारित कर सकता हूँ?** हाँ—`rescheduleUncompletedWorkToStartAfter` का उपयोग करके अधूरे कार्यों को आगे धकेला जा सकता है।  
- **कौन सा फ़ाइल फ़ॉर्मेट सहेजा जाता है?** उदाहरण प्रोजेक्ट को XML (`SaveFileFormat.Xml`) के रूप में सहेजते हैं।  
- **कोड चलाने के लिए क्या लाइसेंस चाहिए?** विकास के लिए मुफ्त ट्रायल काम करता है; उत्पादन के लिए व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण आवश्यक है?** JDK 8 या उससे ऊपर।

## कोड में “update MS Project” क्या है?
प्रोजेक्ट को अपडेट करना मतलब प्रोग्रामेटिक रूप से टास्क की तिथियों, अवधि या पूर्णता प्रतिशत को बदलना और उन परिवर्तनों को स्थायी बनाना। Aspose.Tasks `updateProjectWorkAsComplete` जैसी मेथड्स प्रदान करता है जो आप द्वारा प्रदान की गई रेफ़रेंस `Date` के आधार पर परिवर्तन लागू करता है।

## Aspose.Tasks for Java का उपयोग करके MS Project को अपडेट क्यों करें?
- **UI निर्भरता नहीं** – कई फ़ाइलों में बड़े पैमाने पर बदलाव को स्वचालित करें।  
- **उच्च सटीकता** – लाइब्रेरी सभी मूल Project डेटा (रिसोर्सेज, कैलेंडर, कस्टम फ़ील्ड) को संरक्षित रखती है।  
- **क्रॉस‑प्लेटफ़ॉर्म** – वही कोड Windows, Linux या macOS पर चलाएँ।  
- **MS Project XML सहेजें** – आप अपडेटेड प्रोजेक्ट को व्यापक रूप से समर्थित XML फ़ॉर्मेट में निर्यात कर सकते हैं।

## पूर्वापेक्षाएँ
1. Java Development Kit (JDK) स्थापित हो।  
2. Aspose.Tasks for Java लाइब्रेरी – इसे [यहाँ](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. Java सिंटैक्स और ऑब्जेक्ट‑ओरिएंटेड अवधारणाओं की बुनियादी समझ।

## पैकेज आयात करें
सबसे पहले, आवश्यक Aspose.Tasks क्लासेज़ और Java यूटिलिटीज़ को इम्पोर्ट करें:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## चरण 1: प्रोजेक्ट सेट अप करें
एक नया `Project` इंस्टेंस बनाएँ, कुछ नमूना टास्क परिभाषित करें, उनकी अवधि सेट करें, और निर्भरताएँ स्थापित करें। फिर प्रारंभिक स्थिति को सहेजें ताकि आप पहले‑और‑बाद प्रभाव देख सकें।

```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## चरण 2: प्रोजेक्ट कार्य को अपडेट करें
किसी विशिष्ट कट‑ऑफ़ तिथि तक कार्य को पूर्ण के रूप में चिह्नित करें। यही **update MS Project** का मूल है—API स्वचालित रूप से टास्क प्रोग्रेस और तिथियों को समायोजित करेगा।

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## चरण 3: अपूर्ण कार्य को पुनः‑निर्धारित करें
पूर्ण कार्य को चिह्नित करने के बाद, अक्सर शेष टास्क को आगे धकेलना पड़ता है। नीचे दिया गया कॉल किसी भी अधूरे कार्य को उसी कट‑ऑफ़ तिथि के बाद शुरू होने के लिए ले जाता है, जिससे **how to reschedule MS Project** संभव होता है।

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|--------|-----|
| टास्क अपडेटेड तिथियाँ नहीं दिखाते | प्रोजेक्ट अलग फ़ॉर्मेट (जैसे `.mpp`) में सहेजा गया | XML संरचना बनाए रखने के लिए `SaveFileFormat.Xml` उपयोग करें। |
| `updateProjectWorkAsComplete` कुछ नहीं करता | रेफ़रेंस तिथि प्रोजेक्ट शुरू होने से पहले है | सुनिश्चित करें कि `Calendar` तिथि प्रोजेक्ट टाइमलाइन के भीतर हो। |
| पुनः‑निर्धारित टास्क ओवरलैप करते हैं | कोई कैलेंडर या रिसोर्स लेवलिंग लागू नहीं हुई | पुनः‑निर्धारण के बाद `Project` कैलेंडर लागू करें या `Task.setStart` मैन्युअली सेट करें। |

## अक्सर पूछे जाने वाले प्रश्न (विस्तारित)

**प्रश्न: क्या Aspose.Tasks for Java जटिल प्रोजेक्ट संरचनाओं को संभाल सकता है?**  
**उत्तर:** हाँ, Aspose.Tasks for Java टास्क, निर्भरताएँ, रिसोर्सेज और अन्य प्रोजेक्ट तत्वों को प्रभावी रूप से प्रबंधित करने के लिए मजबूत API प्रदान करता है।

**प्रश्न: क्या Aspose.Tasks for Java के लिए ट्रायल संस्करण उपलब्ध है?**  
**उत्तर:** हाँ, आप इसे [यहाँ](https://releases.aspose.com/) से मुफ्त ट्रायल के रूप में प्राप्त कर सकते हैं।

**प्रश्न: Aspose.Tasks for Java के लिए समर्थन कैसे प्राप्त करें?**  
**उत्तर:** आप किसी भी सहायता या प्रश्न के लिए [Aspose.Tasks फ़ोरम](https://forum.aspose.com/c/tasks/15) पर जा सकते हैं।

**प्रश्न: क्या मैं Aspose.Tasks for Java के लिए अस्थायी लाइसेंस खरीद सकता हूँ?**  
**उत्तर:** हाँ, अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) उपलब्ध हैं।

**प्रश्न: Aspose.Tasks for Java की विस्तृत दस्तावेज़ीकरण कहाँ मिल सकती है?**  
**उत्तर:** आप व्यापक गाइड और API रेफ़रेंस के लिए दस्तावेज़ीकरण [यहाँ](https://reference.aspose.com/tasks/java/) देख सकते हैं।

## निष्कर्ष
इस ट्यूटोरियल में हमने **update MS Project** फ़ाइलों को अपडेट करने, कार्य को पूर्ण चिह्नित करने, और फिर **how to reschedule MS Project** के लिए शेष कार्यों को पुनः‑निर्धारित करने की पूरी प्रक्रिया देखी। प्रोजेक्ट को XML के रूप में सहेजने से आप अन्य टूल्स के साथ संगतता बनाए रखते हैं और परिवर्तन का स्पष्ट ऑडिट ट्रेल रख सकते हैं। इन पैटर्न का उपयोग करके बड़े पोर्टफ़ोलियो में शेड्यूल समायोजन को स्वचालित करें, CI पाइपलाइन के साथ एकीकृत करें, या कस्टम रिपोर्टिंग डैशबोर्ड बनाएं।

---

**अंतिम अपडेट:** 2025-12-23  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}