---
title: Aspose.Tasks में संसाधन असाइनमेंट के लिए रेट स्केल पढ़ें और लिखें
linktitle: Aspose.Tasks में संसाधन असाइनमेंट के लिए रेट स्केल पढ़ें और लिखें
second_title: Aspose.Tasks जावा एपीआई
description: इस व्यापक ट्यूटोरियल के साथ जानें कि जावा के लिए Aspose.Tasks में संसाधन असाइनमेंट दर पैमाने को प्रभावी ढंग से कैसे प्रबंधित किया जाए।
type: docs
weight: 20
url: /hi/java/resource-assignments/read-write-rate-scale/
---
## परिचय
इस ट्यूटोरियल में, हम जावा के लिए Aspose.Tasks का उपयोग करके संसाधन असाइनमेंट दर पैमाने को प्रबंधित करने में गहराई से उतरेंगे, जो प्रोग्रामेटिक रूप से Microsoft प्रोजेक्ट फ़ाइलों के साथ काम करने के लिए एक मजबूत लाइब्रेरी है। इन चरणों का पालन करके, आप अपने जावा अनुप्रयोगों में संसाधन असाइनमेंट के लिए दर पैमाने सेटिंग्स में प्रभावी ढंग से हेरफेर करने में सक्षम होंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:
1. जावा विकास पर्यावरण: सुनिश्चित करें कि आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
2.  जावा लाइब्रेरी के लिए Aspose.Tasks: जावा लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/java/).

## पैकेज आयात करें
सबसे पहले, आपको Aspose.Tasks कार्यात्मकताओं के साथ काम करने के लिए आवश्यक पैकेज आयात करने की आवश्यकता है। 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
अपना जावा प्रोजेक्ट सेट करके प्रारंभ करें और अपनी निर्भरता में Aspose.Tasks लाइब्रेरी को शामिल करें।
## चरण 2: प्रोजेक्ट फ़ाइल लोड करें
जिस प्रोजेक्ट फ़ाइल पर आप काम करना चाहते हैं उसे अपने जावा एप्लिकेशन में लोड करें।
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## चरण 3: एक कार्य जोड़ें
अपने प्रोजेक्ट में एक नया कार्य जोड़ें.
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## चरण 4: संसाधनों को परिभाषित करें
भौतिक और गैर-भौतिक संसाधनों को परिभाषित करें और उनके प्रकार निर्दिष्ट करें।
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## चरण 5: कार्य को संसाधन सौंपें
पहले से परिभाषित संसाधनों को उनके दर पैमाने प्रकारों के साथ कार्य में निर्दिष्ट करें।
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## चरण 6: प्रोजेक्ट सहेजें
संशोधित संसाधन असाइनमेंट के साथ प्रोजेक्ट को सहेजें।
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## चरण 7: संसाधन असाइनमेंट पुनः प्राप्त करें
सहेजे गए प्रोजेक्ट को पुनः लोड करें और रेट स्केल सेटिंग्स को सत्यापित करने के लिए संसाधन असाइनमेंट पुनः प्राप्त करें।
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## निष्कर्ष
जावा के लिए Aspose.Tasks में संसाधन असाइनमेंट दर पैमाने का प्रबंधन प्रभावी परियोजना प्रबंधन के लिए महत्वपूर्ण है। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने जावा अनुप्रयोगों में संसाधन असाइनमेंट के लिए दर पैमाने सेटिंग्स में सहजता से हेरफेर कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### Q1: क्या मैं किसी भी जावा आईडीई के साथ जावा के लिए Aspose.Tasks का उपयोग कर सकता हूं?
उत्तर: हां, जावा के लिए Aspose.Tasks IntelliJ IDEA, Eclipse और NetBeans सहित सभी प्रमुख जावा IDE के साथ संगत है।
### Q2: क्या Aspose.Tasks MPP के अलावा अन्य फ़ाइल स्वरूपों का समर्थन करता है?
उत्तर: हाँ, Aspose.Tasks MPP, XML और HTML सहित विभिन्न फ़ाइल स्वरूपों का समर्थन करता है।
### Q3: क्या Aspose.Tasks उद्यम-स्तरीय परियोजना प्रबंधन के लिए उपयुक्त है?
उत्तर: बिल्कुल, Aspose.Tasks किसी भी पैमाने की परियोजनाओं के प्रबंधन के लिए व्यापक सुविधाएँ प्रदान करता है, जो इसे उद्यम-स्तरीय परियोजना प्रबंधन के लिए उपयुक्त बनाता है।
### Q4: क्या मैं संसाधन असाइनमेंट को दर पैमाने से आगे अनुकूलित कर सकता हूँ?
उत्तर: हां, Aspose.Tasks लागत, कार्य और अवधि समायोजन सहित संसाधन असाइनमेंट को अनुकूलित करने के लिए व्यापक क्षमताएं प्रदान करता है।
### Q5: क्या Aspose.Tasks समर्थन के लिए कोई सामुदायिक मंच है?
 उत्तर: हां, आप Aspose.Tasks फोरम पर अन्य उपयोगकर्ताओं के साथ समर्थन पा सकते हैं और उनके साथ बातचीत कर सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15).