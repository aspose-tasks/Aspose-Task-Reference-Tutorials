---
title: Aspose.Tasks में कार्यों के लिए प्रतिशत पूर्ण गणना
linktitle: Aspose.Tasks में कार्यों के लिए प्रतिशत पूर्ण गणना
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का अन्वेषण करें और प्रोजेक्ट प्रगति ट्रैकिंग को सुव्यवस्थित करें। कुशल परियोजना प्रबंधन के लिए कार्य प्रतिशत की सहजता से गणना करें।
type: docs
weight: 25
url: /hi/java/task-properties/percentage-complete-calculations/
---
## परिचय
जावा के लिए Aspose.Tasks का उपयोग करके कार्य प्रतिशत गणना में महारत हासिल करने पर हमारी गहन मार्गदर्शिका में आपका स्वागत है। Aspose.Tasks एक शक्तिशाली जावा लाइब्रेरी है जिसे Microsoft प्रोजेक्ट फ़ाइलों के साथ काम करने के लिए डिज़ाइन किया गया है, जो प्रोजेक्ट प्रबंधन के लिए सुविधाओं का एक मजबूत सेट पेश करता है। इस ट्यूटोरियल में, हम प्रतिशत पूर्ण गणना पर ध्यान केंद्रित करेंगे, जो आपको परियोजना की प्रगति की प्रभावी ढंग से निगरानी और विश्लेषण करने का ज्ञान प्रदान करेगा।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- जावा विकास पर्यावरण: सुनिश्चित करें कि आपके सिस्टम पर जावा स्थापित है।
-  Aspose.Tasks लाइब्रेरी: जावा के लिए Aspose.Tasks लाइब्रेरी डाउनलोड करें[इस लिंक](https://releases.aspose.com/tasks/java/).
## पैकेज आयात करें
आइए आपके Aspose.Tasks for Java प्रोजेक्ट के लिए आवश्यक पैकेज आयात करके शुरुआत करें। अपने प्रोजेक्ट में निम्नलिखित कोड स्निपेट शामिल करें:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```
अब, आइए विस्तृत स्पष्टीकरण के साथ प्रत्येक चरण का विश्लेषण करें।
## चरण 1: पैकेज आयात करना
पहले चरण में, हम अपने Aspose.Tasks प्रोजेक्ट को सेट करने के लिए आवश्यक पैकेज आयात करते हैं।
## चरण 2: दस्तावेज़ निर्देशिका सेट करना
 का उपयोग करके अपनी दस्तावेज़ निर्देशिका का पथ परिभाषित करें`dataDir`चर। सुनिश्चित करें कि आपकी Microsoft प्रोजेक्ट फ़ाइल, जैसे "सॉफ़्टवेयर डेवलपमेंट.mpp," इस निर्देशिका में है।
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
```
## चरण 3: प्रोजेक्ट लोड हो रहा है
 एक नया प्रारंभ करें`Project` ऑब्जेक्ट करें और अपनी Microsoft प्रोजेक्ट फ़ाइल को प्रोजेक्ट इंस्टेंस में लोड करें।
```java
Project project = new Project(dataDir + "Software Development.mpp");
```
## चरण 4: कार्य संग्रह पुनः प्राप्त करना
 प्रोजेक्ट का मूल कार्य प्राप्त करें और उसके बच्चों को संग्रह के रूप में पुनः प्राप्त करें`getRootTask().getChildren()`.
```java
TaskCollection alTasks = project.getRootTask().getChildren();
```
## चरण 5: मुद्रण प्रतिशत पूर्ण
संग्रह में प्रत्येक कार्य को लूप करें और प्रतिशत पूर्ण, प्रतिशत कार्य पूर्ण और भौतिक प्रतिशत पूर्ण प्रिंट करें।
```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```
प्रत्येक कार्य की प्रगति के बारे में जानकारी प्राप्त करने के लिए अपने प्रोजेक्ट में प्रत्येक कार्य के लिए इन चरणों को दोहराएं।
## निष्कर्ष
बधाई हो! आपने जावा के लिए Aspose.Tasks का उपयोग करके कार्य प्रतिशत गणना में सफलतापूर्वक महारत हासिल कर ली है। यह शक्तिशाली लाइब्रेरी डेवलपर्स को परियोजना की प्रगति को कुशलतापूर्वक प्रबंधित और विश्लेषण करने का अधिकार देती है।
## पूछे जाने वाले प्रश्न
### प्रश्न: मुझे Aspose.Tasks दस्तावेज़ कहाँ मिल सकता है?
 दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/tasks/java/).
### प्रश्न: मैं जावा के लिए Aspose.Tasks लाइब्रेरी कैसे डाउनलोड कर सकता हूं?
 आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
### प्रश्न: क्या कोई निःशुल्क परीक्षण उपलब्ध है?
हाँ, आप निःशुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मुझे Aspose.Tasks के लिए सहायता कहाँ से मिल सकती है?
 सहायता फ़ोरम पर जाएँ[यहाँ](https://forum.aspose.com/c/tasks/15).
### प्रश्न: मैं अस्थायी लाइसेंस कैसे प्राप्त करूं?
 आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).