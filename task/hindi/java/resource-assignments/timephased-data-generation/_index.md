---
title: Aspose.Tasks में समयबद्ध डेटा जेनरेट करें
linktitle: Aspose.Tasks में संसाधन असाइनमेंट के लिए समयबद्ध डेटा जेनरेट करें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके संसाधन असाइनमेंट के लिए समयबद्ध डेटा उत्पन्न करना सीखें। इस व्यापक मार्गदर्शिका के साथ परियोजना प्रबंधन दक्षता में सुधार करें।
type: docs
weight: 24
url: /hi/java/resource-assignments/timephased-data-generation/
---
## परिचय
इस ट्यूटोरियल में, हम जावा के लिए Aspose.Tasks का उपयोग करके संसाधन असाइनमेंट के लिए समयबद्ध डेटा उत्पन्न करने की प्रक्रिया के बारे में जानेंगे। समयबद्ध डेटा एक परियोजना के भीतर समय के साथ संसाधनों को कैसे आवंटित किया जाता है, इस बारे में मूल्यवान अंतर्दृष्टि प्रदान करता है, जिससे परियोजना प्रबंधकों को सूचित निर्णय लेने में मदद मिलती है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1.  जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जेडीके स्थापित है। आप यहां से जेडीके डाउनलोड और इंस्टॉल कर सकते हैं[यहाँ](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  जावा लाइब्रेरी के लिए Aspose.Tasks: जावा लाइब्रेरी के लिए आपके पास Aspose.Tasks होना आवश्यक है। आप इसे यहां से डाउनलोड कर सकते हैं[वेबसाइट](https://releases.aspose.com/tasks/java/).

## पैकेज आयात करें
सबसे पहले, आइए Aspose.Tasks के साथ काम करने के लिए आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## चरण 1: स्रोत एमपीपी फ़ाइल पढ़ें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Data Directory";
// स्रोत एमपीपी फ़ाइल पढ़ें
Project project = new Project(dataDir + "project.mpp");
```
## चरण 2: कार्य और संसाधन असाइनमेंट प्राप्त करें
```java
// प्रोजेक्ट का पहला कार्य प्राप्त करें
Task task = project.getRootTask().getChildren().getById(1);
// प्रोजेक्ट का पहला संसाधन असाइनमेंट प्राप्त करें
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## चरण 3: फ़्लैट कंटूर के साथ टाइमफ़ेज़्ड डेटा जेनरेट करें
```java
// समतल समोच्च डिफ़ॉल्ट समोच्च है
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## चरण 4: कंटूर को कछुए में बदलें
```java
// रूपरेखा को कछुए में बदलें
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## चरण 5: कंटूर को बैकलोडेड में बदलें
```java
// रूपरेखा को बैकलोडेड में बदलें
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## चरण 6: कंटूर को फ्रंटलोडेड में बदलें
```java
// कंटूर को फ्रंटलोडेड में बदलें
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## चरण 7: कंटूर को बेल में बदलें
```java
// रूपरेखा को बेल में बदलें
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## चरण 8: कंटूर को अर्लीपीक में बदलें
```java
// रूपरेखा को अर्लीपीक में बदलें
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## चरण 9: कंटूर को लेटपीक में बदलें
```java
// कंटूर को लेटपीक में बदलें
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## चरण 10: कंटूर को डबलपीक में बदलें
```java
// रूपरेखा को डबलपीक में बदलें
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने जावा के लिए Aspose.Tasks का उपयोग करके संसाधन असाइनमेंट के लिए समयबद्ध डेटा उत्पन्न करने का तरीका बताया है। विभिन्न कार्य रूपरेखाओं को समझने से परियोजना प्रबंधकों को अपनी परियोजनाओं में संसाधन आवंटन और शेड्यूलिंग को प्रभावी ढंग से प्रबंधित करने में मदद मिल सकती है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं अन्य जावा लाइब्रेरीज़ के साथ Aspose.Tasks का उपयोग कर सकता हूँ?
हां, प्रोजेक्ट प्रबंधन क्षमताओं को बढ़ाने के लिए Aspose.Tasks को अन्य जावा लाइब्रेरी के साथ एकीकृत किया जा सकता है।
### क्या Aspose.Tasks बड़े पैमाने की उद्यम परियोजनाओं के लिए उपयुक्त है?
बिल्कुल, Aspose.Tasks को बड़े पैमाने की उद्यम परियोजनाओं सहित सभी आकारों की परियोजनाओं को संभालने के लिए डिज़ाइन किया गया है।
### क्या Aspose.Tasks विभिन्न प्रोजेक्ट फ़ाइल स्वरूपों के लिए समर्थन प्रदान करता है?
हाँ, Aspose.Tasks MPP, XML और MPX सहित विभिन्न प्रोजेक्ट फ़ाइल स्वरूपों का समर्थन करता है।
### क्या मैं अपनी परियोजना आवश्यकताओं के अनुसार कार्य रूपरेखा को अनुकूलित कर सकता हूँ?
हाँ, Aspose.Tasks उपयोगकर्ताओं को उनकी विशिष्ट परियोजना आवश्यकताओं के अनुरूप कस्टम कार्य रूपरेखा परिभाषित करने की अनुमति देता है।
### क्या कोई सामुदायिक मंच है जहां मुझे Aspose.Tasks में सहायता मिल सकती है?
 हां, आप यहां जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) समर्थन और चर्चा के लिए.