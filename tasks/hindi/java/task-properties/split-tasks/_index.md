---
title: Aspose.Tasks में कार्यों को विभाजित करें
linktitle: Aspose.Tasks में कार्यों को विभाजित करें
second_title: Aspose.Tasks जावा एपीआई
description: Aspose.Tasks के साथ जावा में कार्य प्रबंधन में महारत हासिल करें! अनुकूलित प्रोजेक्ट समयसीमा के लिए कार्यों को कुशलतापूर्वक विभाजित करना सीखें। अब डाउनलोड करो!
weight: 29
url: /hi/java/task-properties/split-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में कार्यों को विभाजित करें

## परिचय
क्या आप अपने जावा प्रोजेक्ट में कार्य प्रबंधन से जूझ रहे हैं? जावा के लिए Aspose.Tasks परियोजना प्रबंधन क्षमताओं को बढ़ाते हुए कार्यों को कुशलतापूर्वक विभाजित करने के लिए एक शक्तिशाली समाधान प्रदान करता है। इस ट्यूटोरियल में, हम जावा के लिए Aspose.Tasks का उपयोग करके कार्यों को विभाजित करने की प्रक्रिया में आपका मार्गदर्शन करेंगे, जिससे आपको अपने प्रोजेक्ट की समयसीमा और संसाधन आवंटन को अनुकूलित करने में मदद मिलेगी।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- आपकी मशीन पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Tasks डाउनलोड किया गया और आपके प्रोजेक्ट में जोड़ा गया। आप इसे यहां से डाउनलोड कर सकते हैं[जावा दस्तावेज़ीकरण के लिए Aspose.Tasks](https://reference.aspose.com/tasks/java/).
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करके शुरुआत करें:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```
## चरण 1: एक नया प्रोजेक्ट बनाएं
Aspose.Tasks लाइब्रेरी का उपयोग करके एक नया प्रोजेक्ट बनाकर प्रारंभ करें:
```java
// एक नया प्रोजेक्ट बनाएं
Project splitTaskProject = new Project();
```
## चरण 2: प्रोजेक्ट कैलेंडर सेट करें
समयरेखा स्थापित करने के लिए प्रोजेक्ट की कैलेंडर सेटिंग सेट करें:
```java
// एक मानक कैलेंडर प्राप्त करें
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// प्रोजेक्ट की कैलेंडर सेटिंग सेट करें
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (उदाहरण के साथ जारी रखें)
```
## चरण 3: एक रूट कार्य जोड़ें
अपने प्रोजेक्ट में एक रूट कार्य जोड़ें:
```java
// मूल कार्य
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## चरण 4: स्प्लिट में एक नया कार्य जोड़ें
अपने प्रोजेक्ट में एक नया कार्य जोड़ें जिसे आप विभाजित करना चाहते हैं:
```java
// एक नया कार्य जोड़ें
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## चरण 5: एक संसाधन असाइनमेंट बनाएं
कार्य के लिए एक नया संसाधन असाइनमेंट बनाएँ:
```java
// एक नया संसाधन असाइनमेंट बनाएँ
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## चरण 6: समयबद्ध डेटा उत्पन्न करें
संसाधन असाइनमेंट समयबद्ध डेटा उत्पन्न करें:
```java
// संसाधन असाइनमेंट समयबद्ध डेटा उत्पन्न करें
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## चरण 7: कार्य को विभाजित करें
कार्य को कई भागों में विभाजित करें:
```java
// कार्य को 3 भागों में विभाजित करें
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (उदाहरण के साथ जारी रखें)
```
## निष्कर्ष
बधाई हो! आपने जावा के लिए Aspose.Tasks का उपयोग करके कार्यों को विभाजित करना सफलतापूर्वक सीख लिया है। यह शक्तिशाली लाइब्रेरी जावा परियोजनाओं में कार्य प्रबंधन को सरल बनाती है, परियोजना समयसीमा और संसाधन आवंटन के अनुकूलन के लिए कुशल समाधान प्रदान करती है।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या मैं कार्यों को विभिन्न अवधियों में विभाजित कर सकता हूँ?
हां, आप अपनी परियोजना की आवश्यकताओं के अनुसार कार्यों की अवधि समायोजित कर सकते हैं।
### क्या जावा के लिए Aspose.Tasks सभी जावा संस्करणों के साथ संगत है?
Aspose.Tasks for Java को अनुकूलता सुनिश्चित करते हुए विभिन्न जावा संस्करणों के साथ सहजता से काम करने के लिए डिज़ाइन किया गया है।
### क्या मैं जावा के लिए Aspose.Tasks का निःशुल्क उपयोग कर सकता हूँ?
जावा के लिए Aspose.Tasks एक निःशुल्क परीक्षण प्रदान करता है, जिससे आप खरीदारी करने से पहले इसकी विशेषताओं का पता लगा सकते हैं।
### मैं Java के लिए Aspose.Tasks के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
 दौरा करना[जावा समर्थन मंच के लिए Aspose.Tasks](https://forum.aspose.com/c/tasks/15) सहायता प्राप्त करने और समुदाय से जुड़ने के लिए।
### क्या मुझे Java के लिए Aspose.Tasks के लिए अस्थायी लाइसेंस की आवश्यकता है?
 आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[इस लिंक](https://purchase.aspose.com/temporary-license/) परीक्षण और मूल्यांकन उद्देश्यों के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
