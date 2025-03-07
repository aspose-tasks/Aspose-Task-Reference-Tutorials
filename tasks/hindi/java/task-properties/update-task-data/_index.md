---
title: Aspose.Tasks में टास्क डेटा को MPP फॉर्मेट में अपडेट करें
linktitle: Aspose.Tasks में टास्क डेटा को MPP फॉर्मेट में अपडेट करें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके कार्य डेटा को MPP प्रारूप में अपडेट करने का तरीका जानें। कुशल परियोजना प्रबंधन के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 35
url: /hi/java/task-properties/update-task-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में टास्क डेटा को MPP फॉर्मेट में अपडेट करें

## परिचय
जावा के लिए Aspose.Tasks का उपयोग करके कार्य डेटा को एमपीपी प्रारूप में अपडेट करने पर हमारी चरण-दर-चरण मार्गदर्शिका में आपका स्वागत है। इस ट्यूटोरियल में, हम आपको प्रक्रिया के बारे में बताएंगे, यह सुनिश्चित करते हुए कि आप प्रत्येक चरण को स्पष्टता के साथ समझें। जावा के लिए Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों के साथ काम करने के लिए एक मजबूत समाधान प्रदान करता है, और इस गाइड के अंत तक, आप एमपीपी प्रारूप में कार्य डेटा को कुशलतापूर्वक अपडेट करने में सक्षम होंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
-  जावा के लिए Aspose.Tasks: सुनिश्चित करें कि आपके पास Aspose.Tasks लाइब्रेरी स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[रिलीज पेज](https://releases.aspose.com/tasks/java/).
- जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जावा स्थापित है।
- एकीकृत विकास पर्यावरण (आईडीई): जावा विकास के लिए अपनी पसंद की आईडीई का उपयोग करें।
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करके प्रारंभ करें। निम्नलिखित स्निपेट दर्शाता है कि पैकेज कैसे आयात करें:
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. प्रारंभिक कार्य बनाएं और कॉन्फ़िगर करें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (शेष कोड के साथ जारी रखें)
```
## 2. प्रारंभ तिथि और अवधि निर्धारित करें
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (शेष कोड के साथ जारी रखें)
```
## 3. एक सारांश कार्य बनाएँ
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (शेष कोड के साथ जारी रखें)
```
## 4. समय सीमा और कार्य नोट्स निर्धारित करें
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (शेष कोड के साथ जारी रखें)
```
## 5. कार्य बाधाओं को कॉन्फ़िगर करें
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (शेष कोड के साथ जारी रखें)
```
## 6. अतिरिक्त कार्य बनाएँ
```java
//10 नए कार्य बनाएं
for (int i = 0; i < 10; i++) {
    //... (शेष कोड के साथ जारी रखें)
}
//... (शेष कोड के साथ जारी रखें)
```
## 7. प्रोजेक्ट सहेजें
```java
// प्रोजेक्ट सहेजें
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
इन चरणों का पालन करके, आपने Java के लिए Aspose.Tasks का उपयोग करके कार्य डेटा को MPP प्रारूप में सफलतापूर्वक अपडेट कर लिया है।
## निष्कर्ष
बधाई हो! आपने जावा के लिए Aspose.Tasks का उपयोग करके एमपीपी प्रारूप में कार्य डेटा को अपडेट करने पर एक व्यापक मार्गदर्शिका पूरी कर ली है। यह शक्तिशाली लाइब्रेरी परियोजना प्रबंधन कार्यों को सरल बनाती है, जिससे यह जावा डेवलपर्स के लिए एक मूल्यवान टूल बन जाती है।
## पूछे जाने वाले प्रश्न
### प्रश्न: मैं जावा दस्तावेज़ीकरण के लिए Aspose.Tasks कहां पा सकता हूं?
 उत्तर: दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/tasks/java/).
### प्रश्न: मैं जावा के लिए Aspose.Tasks कैसे डाउनलोड कर सकता हूं?
 उत्तर: आप इसे यहां से डाउनलोड कर सकते हैं[रिलीज पेज](https://releases.aspose.com/tasks/java/).
### प्रश्न: क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 उत्तर: हाँ, आप नि:शुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: जावा के लिए Aspose.Tasks के लिए मुझे समर्थन कहां से मिल सकता है?
 उत्तर: सहायता मंच पर जाएँ[यहाँ](https://forum.aspose.com/c/tasks/15).
### प्रश्न: क्या आप परीक्षण उद्देश्यों के लिए अस्थायी लाइसेंस प्रदान करते हैं?
 उत्तर: हां, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
