---
title: Aspose.Tasks के साथ विभिन्न इकाइयों में कार्य की अवधि
linktitle: Aspose.Tasks के साथ विभिन्न इकाइयों में कार्य की अवधि
second_title: Aspose.Tasks जावा एपीआई
description: Aspose.Tasks के साथ जावा परियोजनाओं में कार्य अवधि प्रबंधन का अन्वेषण करें। मिनट, दिन, घंटे, सप्ताह और महीनों में अवधि की सटीक गणना करें और परिवर्तित करें।
type: docs
weight: 32
url: /hi/java/task-properties/task-duration-different-units/
---
## परिचय
परियोजना प्रबंधन के क्षेत्र में, कार्य अवधि को समझना और प्रबंधित करना एक महत्वपूर्ण पहलू है। जावा के लिए Aspose.Tasks इसे कुशलतापूर्वक संभालने के लिए एक शक्तिशाली टूलसेट प्रदान करता है। इस ट्यूटोरियल में, हम Aspose.Tasks का उपयोग करके विभिन्न इकाइयों में कार्य अवधि पुनर्प्राप्त करने में आपका मार्गदर्शन करेंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- जावा डेवलपमेंट किट (जेडीके) स्थापित किया गया
-  जावा लाइब्रेरी के लिए Aspose.Tasks। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/)
- जावा प्रोग्रामिंग की बुनियादी समझ
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में, Aspose.Tasks लाइब्रेरी शामिल करें। अपने कोड की शुरुआत में निम्नलिखित आयात विवरण जोड़ें:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
अपने पसंदीदा एकीकृत विकास परिवेश (आईडीई) में एक नया जावा प्रोजेक्ट बनाकर शुरुआत करें। अपने प्रोजेक्ट की निर्भरता में Aspose.Tasks लाइब्रेरी को शामिल करना सुनिश्चित करें।
## चरण 2: प्रोजेक्ट टेम्पलेट पढ़ें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// एमएस प्रोजेक्ट टेम्पलेट फ़ाइल पढ़ें
String fileName = dataDir + "project.xml";
// इनपुट फ़ाइल को प्रोजेक्ट के रूप में पढ़ें
Project project = new Project(fileName);
```
 प्रतिस्थापित करना सुनिश्चित करें`"Your Document Directory"` आपकी प्रोजेक्ट फ़ाइलों के वास्तविक पथ के साथ।
## चरण 3: एक कार्य पुनः प्राप्त करें
```java
// विभिन्न प्रारूपों में इसकी अवधि की गणना करने के लिए एक कार्य प्राप्त करें
Task task = project.getRootTask().getChildren().getById(1);
```
 यहां, हम प्रोजेक्ट से एक कार्य प्राप्त कर रहे हैं। समायोजित करना`getById(1)` आपके प्रोजेक्ट की कार्य आईडी के आधार पर।
## चरण 4: अवधि मिनटों में
```java
// अवधि मिनटों में प्राप्त करें
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```
यह चरण मिनटों में कार्य अवधि की गणना करता है।
## चरण 5: अवधि दिनों में
```java
// दिनों में अवधि प्राप्त करें
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```
यह चरण दिनों में कार्य अवधि की गणना करता है।
## चरण 6: अवधि घंटों में
```java
// घंटों में अवधि प्राप्त करें
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```
यह चरण कार्य अवधि की गणना घंटों में करता है।
## चरण 7: अवधि सप्ताहों में
```java
// सप्ताहों में अवधि प्राप्त करें
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```
यह चरण सप्ताहों में कार्य अवधि की गणना करता है।
## चरण 8: अवधि महीनों में
```java
// महीनों में अवधि प्राप्त करें
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```
यह चरण महीनों में कार्य अवधि की गणना करता है।
## निष्कर्ष
जावा के लिए Aspose.Tasks के साथ कार्य अवधि का प्रबंधन करना सरल बना दिया गया है। यह ट्यूटोरियल आपको समय की विभिन्न इकाइयों पर स्पष्टता प्रदान करते हुए चरण दर चरण प्रक्रिया से परिचित कराता है।
## अक्सर पूछे जाने वाले प्रश्नों
### प्रश्न: क्या मैं किसी भी जावा आईडीई के साथ जावा के लिए Aspose.Tasks का उपयोग कर सकता हूं?
हां, जावा के लिए Aspose.Tasks किसी भी जावा इंटीग्रेटेड डेवलपमेंट एनवायरनमेंट (आईडीई) के साथ संगत है।
### प्रश्न: मैं माइक्रोसॉफ्ट प्रोजेक्ट फ़ाइल में किसी कार्य की आईडी कैसे प्राप्त कर सकता हूं?
आप प्रोजेक्ट फ़ाइल का निरीक्षण कर सकते हैं या कार्य आईडी को प्रोग्रामेटिक रूप से पुनर्प्राप्त करने के लिए Aspose.Tasks API का उपयोग कर सकते हैं।
### प्रश्न: क्या Aspose.Tasks बड़े पैमाने की परियोजनाओं को संभालने के लिए उपयुक्त है?
बिल्कुल। Aspose.Tasks को विभिन्न आकारों की परियोजनाओं को कुशलतापूर्वक संभालने के लिए डिज़ाइन किया गया है।
### प्रश्न: मुझे और दस्तावेज़ कहां मिल सकते हैं?
 दौरा करना[प्रलेखन](https://reference.aspose.com/tasks/java/)व्यापक संसाधनों के लिए.
### प्रश्न: क्या मैं खरीदने से पहले जावा के लिए Aspose.Tasks आज़मा सकता हूँ?
 हाँ, आप अन्वेषण कर सकते हैं[मुफ्त परीक्षण](https://releases.aspose.com/) इसकी क्षमताओं का मूल्यांकन करने के लिए।