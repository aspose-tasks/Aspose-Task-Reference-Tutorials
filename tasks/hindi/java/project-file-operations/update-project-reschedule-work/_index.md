---
date: 2026-03-29
description: Aspose.Tasks for Java का उपयोग करके अधूरा कार्य पुनर्निर्धारित करना,
  प्रोजेक्ट कार्य को अपडेट करना, और MS Project फ़ाइलों को XML के रूप में सहेजना सीखें।
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: अपूर्ण कार्य को पुनर्निर्धारित करें और Aspose.Tasks के साथ MS Project फ़ाइलों
  को अपडेट करें
url: /hi/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# अपूर्ण कार्य को पुनर्निर्धारित करें और Aspose.Tasks के साथ MS Project फ़ाइलों को अपडेट करें

## परिचय
Microsoft Project एक व्यापक रूप से उपयोग किया जाने वाला प्रोजेक्ट मैनेजमेंट टूल है जो टीमों को कार्यों की योजना बनाने, संसाधनों को आवंटित करने, और समयसीमा को ट्रैक करने में मदद करता है। Aspose.Tasks for Java डेवलपर्स को Microsoft Project फ़ाइलों को प्रोग्रामेटिक रूप से हेरफेर करने के लिए एक समृद्ध API प्रदान करता है। इस ट्यूटोरियल में, आप सीखेंगे कि कैसे **प्रोजेक्ट कार्य को अपडेट करें**, **अपूर्ण कार्य को पुनर्निर्धारित करें**, और **Aspose.Tasks for Java** का उपयोग करके XML फ़ॉर्मेट में **MS Project फ़ाइल को सहेजें**।

## त्वरित उत्तर
- **“अपूर्ण कार्य को पुनर्निर्धारित करना” क्या मतलब है?** यह शेष कार्य को चुनी गई तिथि के बाद शुरू होने के लिए ले जाता है, जबकि पूर्ण भाग अपरिवर्तित रहता है।  
- **कौन सा मेथड कार्य को पूर्ण के रूप में चिह्नित करता है?** `project.updateProjectWorkAsComplete(date, false)`।  
- **मैं परिवर्तन कैसे सहेजूँ?** `project.save(<path>, SaveFileFormat.Xml)` का उपयोग करें।  
- **क्या उत्पादन के लिए लाइसेंस चाहिए?** हाँ, व्यावसायिक उपयोग के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण समर्थित है?** Java 8 और उसके बाद के संस्करण पूरी तरह समर्थित हैं।

## “अपूर्ण कार्य को पुनर्निर्धारित करना” क्या है?
अपूर्ण कार्य को पुनर्निर्धारित करने से सभी उन कार्यों की प्रारंभ तिथियों को समायोजित किया जाता है जो अभी तक समाप्त नहीं हुए हैं, उन्हें निर्दिष्ट कटऑफ़ तिथि के बाद शुरू करने के लिए धकेला जाता है। यह तब उपयोगी होता है जब प्रोजेक्ट की समयसीमा में देरी या स्कोप परिवर्तन के कारण बदलाव आता है।

## प्रोजेक्ट कार्य को अपडेट करने और कार्यों को पुनर्निर्धारित करने के लिए Aspose.Tasks का उपयोग क्यों करें?
- **सूक्ष्म नियंत्रण:** कार्य पूर्णता प्रतिशत और तिथियों को सीधे सेट करें।  
- **कोई UI आवश्यक नहीं:** कई प्रोजेक्ट फ़ाइलों में बड़े पैमाने पर अपडेट को स्वचालित करें।  
- **क्रॉस‑प्लेटफ़ॉर्म:** किसी भी सिस्टम पर काम करता है जो Java चलाता है।  
- **डेटा अखंडता बनाए रखता है:** सभी निर्भरताएँ, प्रतिबंध, और संसाधन सुसंगत रहते हैं।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. आपके सिस्टम पर Java Development Kit (JDK) स्थापित हो।  
2. Aspose.Tasks for Java लाइब्रेरी। आप इसे [यहाँ](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।  
3. Java प्रोग्रामिंग भाषा की बुनियादी समझ।

## पैकेज आयात करें
सबसे पहले, अपने Java कोड में आवश्यक पैकेज आयात करें:
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
`Project` ऑब्जेक्ट को नई तरह से इनिशियलाइज़ करें, कार्यों को परिभाषित करें, अवधि सेट करें, और निर्भरताएँ स्थापित करें। यह बेसलाइन प्रोजेक्ट बनाता है जिसे हम बाद में अपडेट और पुनर्निर्धारित करेंगे।
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

## चरण 2: प्रोजेक्ट कार्य अपडेट करें
किसी विशिष्ट तिथि तक कार्य को पूर्ण के रूप में चिह्नित करें। यह चरण **प्रोजेक्ट कार्य को अपडेट** ऑपरेशन को दर्शाता है, जो अक्सर पुनर्निर्धारण से पहले पहला कार्य होता है।
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## चरण 3: अपूर्ण कार्य को पुनर्निर्धारित करें
अब हम शेष (अपूर्ण) कार्य को उसी कटऑफ़ तिथि के बाद शुरू होने के लिए स्थानांतरित करते हैं। यह मुख्य **अपूर्ण कार्य को पुनर्निर्धारित करने** कार्यक्षमता है।
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने बताया कि कैसे **प्रोजेक्ट कार्य को अपडेट करें**, **अपूर्ण कार्य को पुनर्निर्धारित करें**, और **Aspose.Tasks for Java** का उपयोग करके XML के रूप में **MS Project फ़ाइल को सहेजें**। ये क्षमताएँ आवश्यक हैं जब प्रोजेक्ट की समयसीमा को वास्तविक प्रगति या बदलती व्यावसायिक प्राथमिकताओं के आधार पर समायोजित करने की आवश्यकता होती है।

## अक्सर पूछे जाने वाले प्रश्न
### Q: क्या Aspose.Tasks for Java जटिल प्रोजेक्ट संरचनाओं को संभाल सकता है?
ह: हाँ, Aspose.Tasks for Java कार्यों, निर्भरताओं, संसाधनों, और अन्य प्रोजेक्ट तत्वों को कुशलतापूर्वक प्रबंधित करने के लिए मजबूत API प्रदान करता है।  
### Q: क्या Aspose.Tasks for Java के लिए ट्रायल संस्करण उपलब्ध है?
ह: हाँ, आप [यहाँ](https://releases.aspose.com/) से मुफ्त ट्रायल प्राप्त कर सकते हैं।  
### Q: मैं Aspose.Tasks for Java के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
ह: आप किसी भी सहायता या प्रश्नों के लिए [Aspose.Tasks फ़ोरम](https://forum.aspose.com/c/tasks/15) पर जा सकते हैं।  
### Q: क्या मैं Aspose.Tasks for Java के लिए अस्थायी लाइसेंस खरीद सकता हूँ?
ह: हाँ, अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) से खरीदे जा सकते हैं।  
### Q: मैं Aspose.Tasks for Java के विस्तृत दस्तावेज़ कहाँ पा सकता हूँ?
ह: आप व्यापक गाइड और API रेफ़रेंसेज़ के लिए दस्तावेज़ीकरण [यहाँ](https://reference.aspose.com/tasks/java/) देख सकते हैं।

## अतिरिक्त अक्सर पूछे जाने वाले प्रश्न

**प्र: मैं यह कैसे सुनिश्चित करूँ कि सहेजी गई फ़ाइल Microsoft Project के पुराने संस्करणों के साथ संगत हो?**  
**ह:** प्रोजेक्ट को `SaveFileFormat.Xml` का उपयोग करके सहेजें; XML विभिन्न Project संस्करणों में व्यापक रूप से समर्थित है।

**प्र: क्या मैं पूरे प्रोजेक्ट के बजाय केवल कार्यों के एक उपसमुच्चय को पुनर्निर्धारित कर सकता हूँ?**  
**ह:** हाँ, आप विशिष्ट कार्यों पर इटरेट कर सकते हैं और नई प्रारंभ तिथि की गणना के बाद `task.setStart(date)` को कॉल कर सकते हैं।

**प्र: जब मैं अपूर्ण कार्य को पुनर्निर्धारित करता हूँ तो संसाधन आवंटन क्या होता है?**  
**ह:** संसाधन असाइनमेंट स्वचालित रूप से नई कार्य प्रारंभ तिथियों के अनुसार शिफ्ट हो जाते हैं, जिससे आवंटन लॉजिक बना रहता है।

**प्र: क्या प्रोग्रामेटिक रूप से पुनर्निर्धारण ऑपरेशन को वापस करना संभव है?**  
**ह:** आप मूल प्रोजेक्ट फ़ाइल (या बैकअप) को पुनः लोड करके किसी भी परिवर्तन को वापस कर सकते हैं।

**प्र: क्या Aspose.Tasks .mpp जैसे अन्य फ़ॉर्मेट में सहेजने का समर्थन करता है?**  
**ह:** बिल्कुल। मूल Microsoft Project फ़ॉर्मेट में सहेजने के लिए `SaveFileFormat.MPP` का उपयोग करें।

---

**अंतिम अपडेट:** 2026-03-29  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}