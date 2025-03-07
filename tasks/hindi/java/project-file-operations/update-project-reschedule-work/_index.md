---
title: Aspose.Tasks में MS प्रोजेक्ट को अद्यतन और पुनर्निर्धारित करें
linktitle: प्रोजेक्ट को अपडेट करें और Aspose.Tasks में अधूरे काम को दोबारा शेड्यूल करें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइलों को प्रोग्रामेटिक रूप से अद्यतन और पुनर्निर्धारित करना सीखें।
weight: 23
url: /hi/java/project-file-operations/update-project-reschedule-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में MS प्रोजेक्ट को अद्यतन और पुनर्निर्धारित करें

## परिचय
माइक्रोसॉफ्ट प्रोजेक्ट एक व्यापक रूप से उपयोग किया जाने वाला प्रोजेक्ट प्रबंधन सॉफ्टवेयर है जो उपयोगकर्ताओं को कार्यों, संसाधनों और समयसीमा को कुशलतापूर्वक प्रबंधित करने की अनुमति देता है। जावा के लिए Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों को प्रोग्रामेटिक रूप से हेरफेर करने के लिए एपीआई का एक शक्तिशाली सेट प्रदान करता है। इस ट्यूटोरियल में, हम सीखेंगे कि एमएस प्रोजेक्ट फ़ाइलों को कैसे अपडेट करें और जावा के लिए Aspose.Tasks का उपयोग करके अधूरे काम को कैसे पुनर्निर्धारित करें।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
2.  जावा लाइब्रेरी के लिए Aspose.Tasks। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
3. जावा प्रोग्रामिंग भाषा की बुनियादी समझ।

## पैकेज आयात करें
सबसे पहले, अपने जावा कोड में आवश्यक पैकेज आयात करें:
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
## चरण 1: प्रोजेक्ट सेट करें
एक नए प्रोजेक्ट ऑब्जेक्ट को आरंभ करें और उसके भीतर कार्यों को उनकी अवधि और निर्भरता के साथ परिभाषित करें।
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// कार्यों और उनकी अवधि को परिभाषित करें
// ...
// कार्य निर्भरता को परिभाषित करें
// ...
// प्रारंभिक प्रोजेक्ट स्थिति सहेजें
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## चरण 2: प्रोजेक्ट कार्य अद्यतन करें
प्रोजेक्ट कार्य को एक निश्चित तिथि तक पूर्ण के रूप में चिह्नित करने के लिए उसे अद्यतन करें।
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// अद्यतन प्रोजेक्ट सहेजें
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## चरण 3: अपूर्ण कार्य को पुनर्निर्धारित करें
किसी भी अधूरे काम को एक निर्दिष्ट तिथि के बाद शुरू करने के लिए पुनर्निर्धारित करें।
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// पुनर्निर्धारित प्रोजेक्ट सहेजें
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि एमएस प्रोजेक्ट फ़ाइलों को कैसे अपडेट किया जाए और जावा के लिए Aspose.Tasks का उपयोग करके अधूरे काम को कैसे पुनर्निर्धारित किया जाए। यह उन परिदृश्यों में विशेष रूप से उपयोगी हो सकता है जहां परियोजना की समयसीमा को प्रगति या बदलती प्राथमिकताओं के आधार पर समायोजन की आवश्यकता होती है।

## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या जावा के लिए Aspose.Tasks जटिल परियोजना संरचनाओं को संभाल सकता है?
उत्तर: हां, जावा के लिए Aspose.Tasks कार्यों, निर्भरताओं, संसाधनों और अन्य परियोजना तत्वों को कुशलतापूर्वक प्रबंधित करने के लिए मजबूत एपीआई प्रदान करता है।
### प्रश्न: क्या जावा के लिए Aspose.Tasks का कोई परीक्षण संस्करण उपलब्ध है?
 उत्तर: हाँ, आप नि:शुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मैं जावा के लिए Aspose.Tasks के लिए समर्थन कैसे प्राप्त कर सकता हूं?
 उत्तर: आप यहां जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) किसी भी सहायता या प्रश्न के लिए।
### प्रश्न: क्या मैं जावा के लिए Aspose.Tasks के लिए एक अस्थायी लाइसेंस खरीद सकता हूँ?
 उत्तर: हां, अस्थायी लाइसेंस खरीद के लिए उपलब्ध हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### प्रश्न: मैं जावा के लिए Aspose.Tasks के लिए विस्तृत दस्तावेज़ कहां पा सकता हूं?
 उत्तर: आप दस्तावेज़ का संदर्भ ले सकते हैं[यहाँ](https://reference.aspose.com/tasks/java/) व्यापक गाइड और एपीआई संदर्भों के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
