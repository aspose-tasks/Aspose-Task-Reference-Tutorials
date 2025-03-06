---
title: Aspose.Tasks में कार्य रोकें और फिर से शुरू करें
linktitle: Aspose.Tasks में कार्य रोकें और फिर से शुरू करें
second_title: Aspose.Tasks जावा एपीआई
description: कार्यों को रोकने और फिर से शुरू करने पर हमारी चरण-दर-चरण मार्गदर्शिका के साथ जावा के लिए Aspose.Tasks की शक्ति का अन्वेषण करें। परियोजना प्रबंधन को निर्बाध रूप से बढ़ाएँ!
weight: 30
url: /hi/java/task-properties/stop-resume-task/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में कार्य रोकें और फिर से शुरू करें

## परिचय
जावा विकास के क्षेत्र में, कार्यों को कुशलतापूर्वक प्रबंधित करना परियोजना निष्पादन का एक महत्वपूर्ण पहलू है। जावा के लिए Aspose.Tasks अपनी शक्तिशाली विशेषताओं के साथ कार्यों को संभालने के लिए एक मजबूत समाधान प्रदान करता है। इस ट्यूटोरियल में, हम एक विशिष्ट कार्यक्षमता - कार्यों को रोकना और फिर से शुरू करना - पर विस्तार से चर्चा करेंगे। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप इस सुविधा को अपने जावा प्रोजेक्ट्स में निर्बाध रूप से एकीकृत करने में सक्षम होंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- जावा प्रोग्रामिंग की बुनियादी समझ.
- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित किया गया।
- जावा लाइब्रेरी के लिए Aspose.Tasks डाउनलोड किया गया और आपके प्रोजेक्ट में जोड़ा गया। आप इसे यहां से प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
## पैकेज आयात करें
प्रक्रिया शुरू करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करना सुनिश्चित करें:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```
## चरण 1: आरंभीकरण
 अपना प्रोजेक्ट प्रारंभ करके और एक बनाकर प्रारंभ करें`ChildTasksCollector` सभी कार्यों को एकत्रित करने के लिए उदाहरण।
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## चरण 2: न्यूनतम तिथि निर्धारित करें
उन कार्यों को फ़िल्टर करने के लिए न्यूनतम तिथि निर्धारित करें जिन्हें रोकने या फिर से शुरू करने की आवश्यकता है।
```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```
## चरण 3: कार्य रोकें और फिर से शुरू करें
कार्यों के माध्यम से पुनरावृत्ति करें, स्टॉप और बायोडाटा की तारीखों की जाँच करें और प्रिंट करें।
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
जावा के लिए Aspose.Tasks का उपयोग करके स्टॉप और रिज्यूम कार्यक्षमता को सहजता से एकीकृत करने के लिए अपने जावा प्रोजेक्ट में इन चरणों को दोहराएं।
## निष्कर्ष
इस ट्यूटोरियल में, हमने जावा के लिए Aspose.Tasks का उपयोग करके कार्यों को रोकने और फिर से शुरू करने की प्रक्रिया का पता लगाया। ऊपर बताए गए चरणों का पालन करके, आप अपनी परियोजना प्रबंधन क्षमताओं को बढ़ा सकते हैं और कार्य निष्पादन को सुव्यवस्थित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या जावा के लिए Aspose.Tasks बड़े पैमाने की परियोजनाओं के लिए उपयुक्त है?
बिल्कुल! जावा के लिए Aspose.Tasks को दक्षता और विश्वसनीयता सुनिश्चित करते हुए विभिन्न आकारों की परियोजनाओं को संभालने के लिए डिज़ाइन किया गया है।
### क्या मैं कार्यों को रोकने और फिर से शुरू करने की तारीख को अनुकूलित कर सकता हूँ?
हां, प्रदान किया गया उदाहरण आपकी परियोजना आवश्यकताओं के अनुसार न्यूनतम तिथि निर्धारित करने में लचीलेपन की अनुमति देता है।
### जावा के लिए Aspose.Tasks के लिए मुझे अतिरिक्त सहायता कहां मिल सकती है?
 दौरा करना[Aspose.कार्य फोरम](https://forum.aspose.com/c/tasks/15) सामुदायिक समर्थन और चर्चा के लिए।
### क्या जावा के लिए Aspose.Tasks के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप पहुंच सकते हैं[मुफ्त परीक्षण](https://releases.aspose.com/) खरीदारी करने से पहले सुविधाओं का पता लगाएं।
### मैं जावा के लिए Aspose.Tasks के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/) परीक्षण प्रयोजनों के लिए.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
