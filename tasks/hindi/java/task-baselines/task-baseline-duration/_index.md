---
title: Aspose.Tasks में कार्य बेसलाइन अवधि प्रबंधन
linktitle: Aspose.Tasks में कार्य बेसलाइन अवधि प्रबंधन
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके एमएस प्रोजेक्ट में कार्य बेसलाइन को कुशलतापूर्वक प्रबंधित करना सीखें। यह ट्यूटोरियल आपको प्रक्रिया के माध्यम से चरण-दर-चरण मार्गदर्शन करता है।
weight: 12
url: /hi/java/task-baselines/task-baseline-duration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में कार्य बेसलाइन अवधि प्रबंधन

## परिचय
एमएस प्रोजेक्ट में कार्य बेसलाइन प्रबंधित करना परियोजना योजना और ट्रैकिंग के लिए महत्वपूर्ण है। इस ट्यूटोरियल में, हम यह पता लगाएंगे कि Java के लिए Aspose.Tasks का उपयोग करके कार्य बेसलाइन अवधि को प्रभावी ढंग से कैसे प्रबंधित किया जाए।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. जावा विकास पर्यावरण: सुनिश्चित करें कि आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
2.  Aspose.Tasks लाइब्रेरी: जावा लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/java/).

## पैकेज आयात करें
सबसे पहले, अपने जावा प्रोजेक्ट के लिए आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## चरण 1: एक प्रोजेक्ट इंस्टेंस बनाएं
निम्नलिखित कोड का उपयोग करके एक नया प्रोजेक्ट इंस्टेंस प्रारंभ करें:
```java
Project project = new Project();
```
## चरण 2: एक कार्य आधार रेखा बनाएं
एक नया कार्य बनाएं और निम्नलिखित कोड का उपयोग करके उसकी आधार रेखा निर्धारित करें:
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## चरण 3: कार्य आधारभूत जानकारी प्रदर्शित करें
कार्य की आधारभूत जानकारी जैसे अवधि, प्रारंभ तिथि, समाप्ति तिथि और अधिक प्राप्त करें और प्रदर्शित करें:
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## चरण 4: अंतरिम आधार रेखा और निश्चित लागत की जाँच करें
जाँचें कि क्या आधार रेखा एक अंतरिम आधार रेखा है और इससे जुड़ी कोई भी निश्चित लागत पुनः प्राप्त करें:
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## चरण 5: समयबद्ध डेटा प्रिंट करें
कार्य आधार रेखा से संबद्ध समयबद्ध डेटा प्रिंट करें:
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
इन चरणों का पालन करके, आप जावा के लिए Aspose.Tasks का उपयोग करके एमएस प्रोजेक्ट में कार्य बेसलाइन अवधि को प्रभावी ढंग से प्रबंधित कर सकते हैं।

## निष्कर्ष
परियोजना प्रबंधन के लिए कार्य आधार रेखाओं का प्रबंधन करना आवश्यक है, जिससे आप नियोजित कार्यक्रम से विचलन को ट्रैक कर सकते हैं। जावा के लिए Aspose.Tasks के साथ, यह प्रक्रिया सुव्यवस्थित और कुशल हो जाती है, जिससे बेहतर प्रोजेक्ट नियंत्रण और वितरण सक्षम हो जाता है।
## अक्सर पूछे जाने वाले प्रश्न
### एमएस प्रोजेक्ट में कार्य आधार रेखा क्या है?
एमएस प्रोजेक्ट में कार्य बेसलाइन किसी कार्य के लिए प्रारंभिक नियोजित शेड्यूल का एक स्नैपशॉट है, जिसमें इसकी प्रारंभ तिथि, समाप्ति तिथि और अवधि शामिल है।
### कार्य आधार रेखाएँ प्रबंधित करना क्यों महत्वपूर्ण है?
कार्य आधार रेखाओं को प्रबंधित करने से परियोजना की वास्तविक प्रगति के साथ नियोजित कार्यक्रम की तुलना करने में मदद मिलती है, जिससे बेहतर ट्रैकिंग और निर्णय लेने में सुविधा होती है।
### क्या मैं किसी कार्य की आधार रेखा निर्धारित होने के बाद उसे संशोधित कर सकता हूँ?
हां, आप प्रोजेक्ट योजना में बदलावों को प्रतिबिंबित करने के लिए एमएस प्रोजेक्ट में कार्य बेसलाइन को संशोधित कर सकते हैं। हालाँकि, मूल आधार रेखा से किसी भी विचलन का दस्तावेजीकरण करना आवश्यक है।
### क्या Aspose.Tasks अन्य परियोजना प्रबंधन कार्यात्मकताओं का समर्थन करता है?
हाँ, Aspose.Tasks परियोजना प्रबंधन के लिए कार्य शेड्यूलिंग, संसाधन आवंटन और गैंट चार्ट निर्माण सहित सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है।
### मुझे Aspose.Tasks के लिए समर्थन कहां मिल सकता है?
 आप Aspose.Tasks के लिए समर्थन पा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15), जहां आप प्रश्न पूछ सकते हैं और अन्य उपयोगकर्ताओं के साथ बातचीत कर सकते हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
