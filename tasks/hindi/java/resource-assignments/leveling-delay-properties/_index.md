---
title: Aspose.Tasks में लेवलिंग विलंब गुणों को संभालें
linktitle: Aspose.Tasks में संसाधन असाइनमेंट के लिए लेवलिंग विलंब गुणों को संभालें
second_title: Aspose.Tasks जावा एपीआई
description: इस व्यापक ट्यूटोरियल के साथ सीखें कि जावा के लिए Aspose.Tasks में संसाधन असाइनमेंट के लिए लेवलिंग विलंब गुणों को कैसे संभालें।
type: docs
weight: 17
url: /hi/java/resource-assignments/leveling-delay-properties/
---
## परिचय
इस ट्यूटोरियल में, हम जावा के लिए Aspose.Tasks में संसाधन असाइनमेंट के लिए लेवलिंग विलंब गुणों को संभालने की प्रक्रिया से गुजरेंगे। Aspose.Tasks एक शक्तिशाली जावा लाइब्रेरी है जो आपको आपके सिस्टम पर Microsoft प्रोजेक्ट इंस्टॉल किए बिना Microsoft प्रोजेक्ट फ़ाइलों के साथ काम करने की अनुमति देती है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1.  जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जावा जेडीके स्थापित है। आप इसे यहां से डाउनलोड और इंस्टॉल कर सकते हैं[वेबसाइट](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  जावा लाइब्रेरी के लिए Aspose.Tasks: जावा लाइब्रेरी के लिए Aspose.Tasks को यहां से डाउनलोड करें[डाउनलोड पेज](https://releases.aspose.com/tasks/java/).

## पैकेज आयात करें
सबसे पहले, Aspose.Tasks कार्यात्मकताओं का उपयोग करने के लिए अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## चरण 1: एक प्रोजेक्ट ऑब्जेक्ट बनाएं
 त्वरित करें ए`Project` वस्तु:
```java
Project prj = new Project();
```
## चरण 2: एक कार्य बनाएं
प्रोजेक्ट में कोई कार्य जोड़ें:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## चरण 3: कार्य प्रारंभ तिथि और अवधि निर्धारित करें
कार्य के लिए आरंभ तिथि और अवधि निर्धारित करें:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## चरण 4: एक संसाधन जोड़ें
प्रोजेक्ट में संसाधन जोड़ें:
```java
Resource resource = prj.getResources().add("Resource 1");
```
## चरण 5: एक संसाधन असाइनमेंट बनाएं
कार्य और संसाधन के लिए संसाधन असाइनमेंट बनाएं:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## चरण 6: लेवलिंग विलंब सेट करें
असाइनमेंट के लिए लेवलिंग विलंब सेट करें:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## चरण 7: परिणाम प्रदर्शित करें
लेवलिंग विलंब और अन्य प्रासंगिक जानकारी प्रिंट करें:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि जावा के लिए Aspose.Tasks में संसाधन असाइनमेंट के लिए लेवलिंग विलंब गुणों को कैसे संभालना है। इन चरणों का पालन करके, आप अपने जावा प्रोजेक्ट्स में संसाधन असाइनमेंट को कुशलतापूर्वक प्रबंधित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं अन्य जावा लाइब्रेरीज़ के साथ Aspose.Tasks का उपयोग कर सकता हूँ?

उत्तर: हां, प्रोजेक्ट प्रबंधन क्षमताओं को बढ़ाने के लिए Aspose.Tasks को अन्य जावा लाइब्रेरी के साथ एकीकृत किया जा सकता है।

### प्रश्न: क्या Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों के साथ संगत है?

उत्तर: हाँ, Aspose.Tasks विभिन्न परिवेशों में अनुकूलता सुनिश्चित करते हुए Microsoft प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों का समर्थन करता है।

### प्रश्न: मुझे Aspose.Tasks के लिए अतिरिक्त सहायता कहां मिल सकती है?

 उत्तर: आप यहां सहायता और संसाधन पा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15).

### प्रश्न: क्या मैं खरीदने से पहले Aspose.Tasks आज़मा सकता हूँ?

 उत्तर: हाँ, आप Aspose.Tasks का निःशुल्क परीक्षण प्राप्त कर सकते हैं[पृष्ठ जारी करता है](https://releases.aspose.com/).

### प्रश्न: मैं Aspose.Tasks के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 उ: आप यहां से अस्थायी लाइसेंस का अनुरोध कर सकते हैं[अस्थायी लाइसेंस पृष्ठ](https://purchase.aspose.com/temporary-license/) मूल्यांकन प्रयोजनों के लिए.