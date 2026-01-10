---
date: 2026-01-10
description: Aspose.Tasks for Java का उपयोग करके संसाधन असाइनमेंट के लिए कंटूर बदलना
  और टाइम‑फ़ेज़्ड डेटा उत्पन्न करना सीखें, जिससे प्रोजेक्ट प्रबंधन की दक्षता बढ़ेगी।
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में टाइमफ़ेज़्ड डेटा के लिए कंटूर कैसे बदलें
url: /hi/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में टाइमफ़ेज़्ड डेटा के लिए कंटूर कैसे बदलें

## परिचय
इस ट्यूटोरियल में, आप **कंटूर कैसे बदलें** को एक रिसोर्स असाइनमेंट के लिए खोजेंगे और Aspose.Tasks for Java का उपयोग करके टाइमफ़ेज़्ड डेटा जेनरेट करेंगे। टाइमफ़ेज़्ड डेटा प्रोजेक्ट टाइमलाइन पर कार्य के वितरण को दर्शाता है, जिससे आप शेड्यूल को फाइन‑ट्यून कर सकते हैं, वर्कलोड को बैलेंस कर सकते हैं, और डेटा‑ड्रिवेन निर्णय ले सकते हैं।

## त्वरित उत्तर
- **कंटूर क्या है?** वर्क कंटूर यह निर्धारित करता है कि कार्य का प्रयास कार्य की अवधि में कैसे वितरित होता है (जैसे, Flat, Turtle, Bell)।  
- **कंटूर क्यों बदलें?** वास्तविक कार्य पैटर्न जैसे फ्रंट‑लोडिंग या बैक‑लोडिंग प्रयास को दर्शाने के लिए।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Tasks for Java (कोई भी नवीनतम संस्करण)।  
- **क्या मुझे लाइसेंस चाहिए?** हाँ, उत्पादन उपयोग के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है।  
- **क्या मैं परिणाम कंसोल में देख सकता हूँ?** उदाहरण प्रत्येक टाइमफ़ेज़्ड सेगमेंट के लिए प्रारंभ तिथियां और मान प्रिंट करता है।

## “कंटूर कैसे बदलें” क्या है?
कंटूर बदलने का मतलब है `ResourceAssignment` की `WORK_CONTOUR` प्रॉपर्टी को अपडेट करना। Aspose.Tasks कई पूर्वनिर्धारित कंटूर (Flat, Turtle, Bell, आदि) का समर्थन करता है जो समय के साथ कार्य के आवंटन को प्रभावित करते हैं।

## टाइमफ़ेज़्ड डेटा उत्पन्न करने के लिए Aspose.Tasks का उपयोग क्यों करें?
- **सटीक रिपोर्टिंग:** रिपोर्टिंग टूल्स के लिए सटीक कार्य वितरण निर्यात करें।  
- **परिदृश्य योजना:** मूल शेड्यूल को बदले बिना विभिन्न कंटूर का परीक्षण करें।  
- **ऑटोमेशन:** CI पाइपलाइनों में एकीकृत करके प्रोजेक्ट स्वास्थ्य को स्वचालित रूप से सत्यापित करें।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
1. Java Development Kit (JDK): सुनिश्चित करें कि आपके सिस्टम पर JDK स्थापित है। आप इसे [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) से डाउनलोड और इंस्टॉल कर सकते हैं।
2. Aspose.Tasks for Java लाइब्रेरी: आपको Aspose.Tasks for Java लाइब्रेरी चाहिए। आप इसे [website](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।

## पैकेज इम्पोर्ट करें
पहले, Aspose.Tasks के साथ काम करने के लिए आवश्यक पैकेज इम्पोर्ट करें:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## चरण 1: स्रोत MPP फ़ाइल पढ़ें
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## चरण 2: टास्क और रिसोर्स असाइनमेंट प्राप्त करें
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## कंटूर कैसे बदलें – Flat (डिफ़ॉल्ट)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## कंटूर कैसे बदलें – Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## कंटूर कैसे बदलें – BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## कंटूर कैसे बदलें – FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## कंटूर कैसे बदलें – Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## कंटूर कैसे बदलें – EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## कंटूर कैसे बदलें – LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## कंटूर कैसे बदलें – DoublePeak
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## सामान्य समस्याएँ और टिप्स
- **कंटूर अपडेट नहीं हो रहा है?** सुनिश्चित करें कि आप `firstRA.set(Asn.WORK_CONTOUR, …)` *समयफ़ेज़्ड डेटा प्राप्त करने से पहले* कॉल करें।
- **अप्रत्याशित मान?** जांचें कि टास्क की प्रारंभ और समाप्ति तिथियां स्रोत MPP में सही सेट हैं।
- **परफॉर्मेंस टिप:** कई कंटूर पर इटरेट करते समय अनावश्यक फ़ाइल I/O से बचने के लिए वही `Project` इंस्टेंस पुन: उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Tasks को अन्य Java लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?
हाँ, Aspose.Tasks को अन्य Java लाइब्रेरीज़ के साथ एकीकृत किया जा सकता है ताकि प्रोजेक्ट मैनेजमेंट क्षमताओं को बढ़ाया जा सके।

### क्या Aspose.Tasks बड़े‑पैमाने के एंटरप्राइज़ प्रोजेक्ट्स के लिए उपयुक्त है?
बिल्कुल, Aspose.Tasks को सभी आकार के प्रोजेक्ट्स, जिसमें बड़े‑पैमाने के एंटरप्राइज़ पहल शामिल हैं, को संभालने के लिए डिज़ाइन किया गया है।

### क्या Aspose.Tasks विभिन्न प्रोजेक्ट फ़ाइल फ़ॉर्मेट्स के लिए समर्थन प्रदान करता है?
हाँ, Aspose.Tasks कई फ़ॉर्मेट्स का समर्थन करता है, जैसे MPP, XML, और MPX।

### क्या मैं अपने प्रोजेक्ट आवश्यकताओं के अनुसार वर्क कंटूर को कस्टमाइज़ कर सकता हूँ?
हाँ, आप विशिष्ट शेड्यूलिंग जरूरतों के अनुरूप कस्टम वर्क कंटूर परिभाषित कर सकते हैं।

### क्या कोई कम्युनिटी फ़ोरम है जहाँ मैं Aspose.Tasks के साथ सहायता प्राप्त कर सकता हूँ?
हाँ, आप समर्थन और चर्चा के लिए [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर जा सकते हैं।

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}