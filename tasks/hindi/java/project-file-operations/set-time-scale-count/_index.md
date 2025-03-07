---
title: Aspose.Tasks में एमएस प्रोजेक्ट टाइम स्केल गणना में महारत हासिल करना
linktitle: Aspose.Tasks में टाइम स्केल गणना सेट करें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके एमएस प्रोजेक्ट में टाइम स्केल गणना को प्रभावी ढंग से प्रबंधित करना सीखें। प्रोजेक्ट विज़ुअलाइज़ेशन और प्रबंधन को सहजता से अनुकूलित करें।
weight: 22
url: /hi/java/project-file-operations/set-time-scale-count/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में एमएस प्रोजेक्ट टाइम स्केल गणना में महारत हासिल करना

## परिचय
एमएस प्रोजेक्ट में टाइम स्केल गणना का प्रबंधन प्रोजेक्ट विज़ुअलाइज़ेशन और प्रबंधन को महत्वपूर्ण रूप से प्रभावित कर सकता है। जावा के लिए Aspose.Tasks के साथ, प्रोजेक्ट प्रबंधन कार्यों को प्रोग्रामेटिक रूप से संभालने के लिए एक शक्तिशाली एपीआई, आप अपनी विशिष्ट आवश्यकताओं के अनुसार प्रोजेक्ट दृश्यों को तैयार करने के लिए समय पैमाने की गणना में कुशलतापूर्वक हेरफेर कर सकते हैं।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित स्थान हैं:
1. जावा विकास पर्यावरण: सुनिश्चित करें कि आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
2.  जावा लाइब्रेरी के लिए Aspose.Tasks: जावा लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें। आप इसे यहां से प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
3. जावा प्रोग्रामिंग का बुनियादी ज्ञान: जावा प्रोग्रामिंग भाषा से परिचित होना फायदेमंद होगा।

## पैकेज आयात करें
अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## चरण 1: डेटा निर्देशिका सेट करें
डेटा निर्देशिका का पथ परिभाषित करें जहां आपकी प्रोजेक्ट फ़ाइलें संग्रहीत की जाएंगी:
```java
String dataDir = "Your Data Directory";
```
 प्रतिस्थापित करें`"Your Data Directory"` आपकी डेटा निर्देशिका के पथ के साथ।
## चरण 2: प्रोजेक्ट इंस्टेंस बनाएं
 एक नया त्वरित करें`Project` वस्तु:
```java
Project project = new Project();
```
यह एक नया प्रोजेक्ट ऑब्जेक्ट बनाता है।
## चरण 3: गैंट चार्ट दृश्य कॉन्फ़िगर करें
 एक बनाने के`GanttChartView` गैंट चार्ट दृश्य को कॉन्फ़िगर करने के लिए ऑब्जेक्ट:
```java
GanttChartView view = new GanttChartView();
```
## चरण 4: निचले स्तर के लिए समय स्केल गणना निर्धारित करें
निचले टाइमस्केल स्तर के लिए गिनती और टिक दृश्यता सेट करें:
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
यह अंतरालों की गिनती निर्दिष्ट करता है और निचले स्तर के लिए टिक प्रदर्शित करना है या नहीं।
## चरण 5: मध्य स्तर के लिए समयमान गणना निर्धारित करें
इसी प्रकार, मध्य टाइमस्केल स्तर को कॉन्फ़िगर करें:
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## चरण 6: प्रोजेक्ट में दृश्य जोड़ें
प्रोजेक्ट में कॉन्फ़िगर किया गया दृश्य जोड़ें:
```java
project.getViews().add(view);
```
यह प्रोजेक्ट में अनुकूलित दृश्य जोड़ता है।
## चरण 7: प्रोजेक्ट में परीक्षण डेटा जोड़ें
प्रदर्शन के लिए प्रोजेक्ट में कुछ परीक्षण डेटा जोड़ें:
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
यह निर्दिष्ट अवधि के साथ दो कार्य बनाता है।
## चरण 8: प्रोजेक्ट को पीडीएफ के रूप में सहेजें
प्रोजेक्ट को पीडीएफ फाइल के रूप में सहेजें:
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
यह प्रोजेक्ट को लागू कॉन्फ़िगरेशन के साथ एक पीडीएफ फ़ाइल में सहेजता है।

## निष्कर्ष
जावा के लिए Aspose.Tasks का उपयोग करके एमएस प्रोजेक्ट में टाइम स्केल गणना को प्रभावी ढंग से प्रबंधित करना आपको बेहतर विज़ुअलाइज़ेशन और प्रबंधन के लिए प्रोजेक्ट दृश्यों को अनुकूलित करने का अधिकार देता है।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या जावा के लिए Aspose.Tasks बड़े पैमाने पर प्रोजेक्ट फ़ाइलों को संभाल सकता है?
उत्तर: हां, जावा के लिए Aspose.Tasks बड़े पैमाने पर प्रोजेक्ट फ़ाइलों को कुशलतापूर्वक संभालने में सक्षम है।
### प्रश्न: क्या जावा के लिए Aspose.Tasks विभिन्न जावा आईडीई के साथ संगत है?
उत्तर: हां, जावा के लिए Aspose.Tasks लोकप्रिय जावा इंटीग्रेटेड डेवलपमेंट एनवायरमेंट (आईडीई) जैसे कि एक्लिप्स और इंटेलीजे आईडीईए के साथ निर्बाध रूप से काम करता है।
### प्रश्न: क्या मैं जावा के लिए Aspose.Tasks का उपयोग करके गैंट चार्ट की उपस्थिति को अनुकूलित कर सकता हूँ?
उत्तर: बिल्कुल, जावा के लिए Aspose.Tasks आपकी आवश्यकताओं के अनुसार गैंट चार्ट की उपस्थिति को अनुकूलित करने के लिए व्यापक क्षमताएं प्रदान करता है।
### प्रश्न: क्या जावा के लिए Aspose.Tasks का कोई परीक्षण संस्करण उपलब्ध है?
 उत्तर: हाँ, आप नि:शुल्क परीक्षण संस्करण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: जावा के लिए Aspose.Tasks के लिए मुझे समर्थन कहां से मिल सकता है?
 उत्तर: आप Aspose.Tasks फोरम पर समर्थन और सहायता पा सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
