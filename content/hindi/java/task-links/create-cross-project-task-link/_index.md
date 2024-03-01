---
title: Aspose.Tasks में क्रॉस-प्रोजेक्ट टास्क लिंक बनाएं
linktitle: Aspose.Tasks में क्रॉस-प्रोजेक्ट टास्क लिंक बनाएं
second_title: Aspose.Tasks जावा एपीआई
description: Java के लिए Aspose.Tasks के साथ प्रोजेक्ट सहयोग बढ़ाएँ। चरण दर चरण क्रॉस-प्रोजेक्ट कार्य लिंक बनाना सीखें। अब दक्षता बढ़ाएँ!
type: docs
weight: 10
url: /hi/java/task-links/create-cross-project-task-link/
---
## परिचय
परियोजना प्रबंधन की गतिशील दुनिया में दक्षता और सहयोग सर्वोपरि हैं। जावा के लिए Aspose.Tasks आपकी परियोजना प्रबंधन क्षमताओं को बढ़ाने के लिए एक मजबूत समाधान प्रदान करता है। इस ट्यूटोरियल में, हम Java के लिए Aspose.Tasks का उपयोग करके क्रॉस-प्रोजेक्ट कार्य लिंक बनाने की प्रक्रिया के बारे में विस्तार से जानेंगे। यह चरण-दर-चरण मार्गदर्शिका आपको विभिन्न परियोजनाओं में कार्यों को निर्बाध रूप से जोड़ने, बेहतर समन्वय और सुव्यवस्थित वर्कफ़्लो को बढ़ावा देने के कौशल से लैस करेगी।
## आवश्यक शर्तें
इससे पहले कि हम इस ट्यूटोरियल को शुरू करें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- जावा प्रोग्रामिंग का कार्यसाधक ज्ञान।
-  जावा के लिए Aspose.Tasks स्थापित। आप इसे यहां से डाउनलोड कर सकते हैं[जावा रिलीज पेज के लिए Aspose.Tasks](https://releases.aspose.com/tasks/java/).
- परियोजना प्रबंधन और कार्य निर्भरता की बुनियादी समझ।
## पैकेज आयात करें
प्रक्रिया को शुरू करने के लिए, आइए आपके जावा वातावरण में आवश्यक पैकेज आयात करें। यह सुनिश्चित करता है कि आपके पास जावा कार्यात्मकताओं के लिए Aspose.Tasks तक पहुंच है। निम्नलिखित कोड स्निपेट का उपयोग करें:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```
अब, आइए उपरोक्त कोड को समझने योग्य चरणों में तोड़ें:
## चरण 1: अपना वातावरण स्थापित करें
कोड में गोता लगाने से पहले, सुनिश्चित करें कि आपने जावा स्थापित किया है, और जावा लाइब्रेरी के लिए Aspose.Tasks आपके प्रोजेक्ट में सही ढंग से जोड़ा गया है।
## चरण 2: एक प्रोजेक्ट इंस्टेंस बनाएं
Aspose.Tasks लाइब्रेरी का उपयोग करके एक नया प्रोजेक्ट प्रारंभ करें:
```java
Project project = new Project();
```
## चरण 3: एक सारांश कार्य जोड़ें
लिंक किए गए कार्यों को व्यवस्थित और प्रबंधित करने के लिए एक सारांश कार्य बनाएं:
```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```
## चरण 4: बाहरी कार्य जोड़ें
किसी अन्य प्रोजेक्ट से किसी कार्य का लिंक बनाने के लिए, सारांश कार्य में एक बाहरी कार्य जोड़ें:
```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```
## चरण 5: स्थानीय कार्य जोड़ें
सारांश कार्य में एक स्थानीय कार्य जोड़ें। यह बाहरी कार्य से जुड़ा कार्य होगा:
```java
Task t = summary.getChildren().add("Task");
```
## चरण 6: कार्य लिंक बनाएं
बाहरी कार्य और स्थानीय कार्य के बीच कार्य लिंक स्थापित करें:
```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```
## चरण 7: परिणाम प्रदर्शित करें
अंत में, रूपांतरण का परिणाम प्रदर्शित करें:
```java
System.out.println("Process completed Successfully");
```
## निष्कर्ष
बधाई हो! आपने जावा के लिए Aspose.Tasks का उपयोग करके क्रॉस-प्रोजेक्ट कार्य लिंक बनाने का तरीका सफलतापूर्वक सीख लिया है। यह कार्यक्षमता परियोजना प्रबंधन में सहयोग और समन्वय को बढ़ाती है, जिससे विभिन्न परियोजनाओं में कार्यों के बीच निर्बाध एकीकरण सुनिश्चित होता है।
## पूछे जाने वाले प्रश्न
### क्या मैं एक ही सारांश कार्य में एकाधिक बाहरी परियोजनाओं के कार्यों को लिंक कर सकता हूँ?
हां, आप एक समान प्रक्रिया का पालन करते हुए, एक ही सारांश कार्य के भीतर विभिन्न बाहरी परियोजनाओं के कार्यों को लिंक कर सकते हैं।
### यदि लिंक किए गए प्रोजेक्ट में बाहरी कार्य को संशोधित किया जाए तो क्या होगा?
बाहरी कार्य में कोई भी संशोधन आपके वर्तमान प्रोजेक्ट में लिंक किए गए कार्य में दिखाई देगा।
### क्या विभिन्न फ़ाइल स्वरूपों में कार्यों के बीच लिंक बनाना संभव है?
हां, जावा के लिए Aspose.Tasks विभिन्न फ़ाइल स्वरूपों में परियोजनाओं के बीच कार्यों को जोड़ने का समर्थन करता है।
### क्या मैं परियोजनाओं से लिंक हो जाने के बाद कार्यों को अनलिंक कर सकता हूँ?
हाँ, आप उपयुक्त Aspose.Tasks विधियों का उपयोग करके कार्य लिंक को हटाकर कार्यों को अनलिंक कर सकते हैं।
### क्या उन कार्यों की संख्या पर कोई सीमाएँ हैं जिन्हें परियोजनाओं से जोड़ा जा सकता है?
लिंक किए जा सकने वाले कार्यों की संख्या आपके Aspose.Tasks लाइसेंस की क्षमताओं और सीमाओं के अधीन है।