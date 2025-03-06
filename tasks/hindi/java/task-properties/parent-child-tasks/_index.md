---
title: Aspose.Tasks में माता-पिता और बच्चे के कार्य प्रबंधित करें
linktitle: Aspose.Tasks में माता-पिता और बच्चे के कार्य प्रबंधित करें
second_title: Aspose.Tasks जावा एपीआई
description: Java के लिए Aspose.Tasks के साथ परियोजना प्रबंधन दक्षता बढ़ाएँ। माता-पिता और बच्चे के कार्यों को चरण-दर-चरण प्रबंधित करना सीखें। अब शुरू हो जाओ!
type: docs
weight: 24
url: /hi/java/task-properties/parent-child-tasks/
---
## परिचय
परियोजना प्रबंधन के क्षेत्र में, प्रभावी कार्य संगठन महत्वपूर्ण है। जावा के लिए Aspose.Tasks माता-पिता और बच्चे के कार्यों को कुशलतापूर्वक प्रबंधित करने के लिए एक मजबूत समाधान प्रदान करता है। इस ट्यूटोरियल में, हम आपके प्रोजेक्ट कार्यों को सुव्यवस्थित करने के लिए जावा के लिए Aspose.Tasks का उपयोग करने की प्रक्रिया में आपका मार्गदर्शन करेंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- जावा प्रोग्रामिंग की बुनियादी समझ.
-  जावा लाइब्रेरी के लिए Aspose.Tasks स्थापित। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
- आपके सिस्टम पर एक जावा इंटीग्रेटेड डेवलपमेंट एनवायरनमेंट (आईडीई) स्थापित किया गया है।
## पैकेज आयात करें
आरंभ करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें। ये पैकेज जावा कार्यात्मकताओं के लिए Aspose.Tasks के साथ सहज एकीकरण की सुविधा प्रदान करते हैं।
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```
## चरण 1: परियोजना प्रारंभ तिथि निर्धारित करें
प्रोजेक्ट की आरंभ तिथि और अन्य प्रासंगिक पैरामीटर सेट करके प्रारंभ करें।
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// पैकेज आयात के लिए अतिरिक्त कोड यहां जोड़ा जा सकता है
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## चरण 2: मूल कार्य जोड़ें (कार्य 1)
"कार्य 1" नामक एक मूल कार्य बनाएं और उसके गुणों को कॉन्फ़िगर करें।
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## चरण 3: अभिभावक कार्य (कार्य 2) को बाल कार्यों के साथ जोड़ें
अब, "टास्क 2" नाम का एक और मूल कार्य जोड़ें और चाइल्ड टास्क (टास्क 3 और टास्क 4) शामिल करें।
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// कार्य 2 में चाइल्ड कार्य जोड़ें
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// टास्क 3 और टास्क 4 के लिए अतिरिक्त कॉन्फ़िगरेशन यहां जोड़ा जा सकता है
```
## चरण 4: बाल कार्यों को कॉन्फ़िगर करें
कार्य 3 और कार्य 4 के लिए प्रारंभ दिनांक, अवधि और बाधाएँ निर्दिष्ट करें।
```java
// कार्य 3 कॉन्फ़िगर करें
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// कार्य 4 कॉन्फ़िगर करें
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## चरण 5: कार्य पूर्णता प्रतिशत अद्यतन करें
कार्य 3 और कार्य 4 के लिए पूर्णता प्रतिशत समायोजित करें।
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## चरण 6: प्रोजेक्ट सहेजें
अंत में, लागू परिवर्तनों के साथ प्रोजेक्ट को सहेजें।
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
यह चरण-दर-चरण मार्गदर्शिका दर्शाती है कि जावा के लिए Aspose.Tasks का उपयोग करके माता-पिता और बच्चे के कार्यों को प्रभावी ढंग से कैसे प्रबंधित किया जाए। अपने प्रोजेक्ट की आवश्यकताओं के अनुरूप विभिन्न कॉन्फ़िगरेशन के साथ प्रयोग करें।
## निष्कर्ष
अंत में, जावा के लिए Aspose.Tasks डेवलपर्स को परियोजना कार्यों को कुशलतापूर्वक संभालने, निर्बाध संगठन और ट्रैकिंग सुनिश्चित करने का अधिकार देता है। अपनी परियोजना प्रबंधन क्षमताओं को बढ़ाने के लिए उल्लिखित चरणों को लागू करें।
## पूछे जाने वाले प्रश्न
### क्या जावा के लिए Aspose.Tasks विभिन्न प्रोजेक्ट फ़ाइल स्वरूपों के साथ संगत है?
हाँ, Java के लिए Aspose.Tasks MPP और XML सहित विभिन्न प्रोजेक्ट फ़ाइल स्वरूपों का समर्थन करता है।
### क्या मैं इस ट्यूटोरियल में शामिल कार्यों से परे कार्य गुणों को अनुकूलित कर सकता हूँ?
बिल्कुल! जावा के लिए Aspose.Tasks कार्य गुणों के लिए व्यापक अनुकूलन विकल्प प्रदान करता है।
### क्या Aspose.Tasks के लिए कोई सामुदायिक मंच है जहां मैं समर्थन मांग सकता हूं?
 हां, आप यहां जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) सामुदायिक समर्थन के लिए.
### मैं जावा के लिए Aspose.Tasks के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आपको अस्थायी लाइसेंस मिल सकता है[यहाँ](https://purchase.aspose.com/temporary-license/).
### मैं जावा के लिए Aspose.Tasks के लिए व्यापक दस्तावेज़ कहाँ पा सकता हूँ?
 दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/tasks/java/).