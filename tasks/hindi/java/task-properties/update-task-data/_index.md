---
date: 2026-03-03
description: Aspose Tasks Java का उपयोग करके टास्क डेटा को MPP फ़ॉर्मेट में अपडेट
  करना सीखें। कुशल प्रोजेक्ट प्रबंधन के लिए हमारी चरण‑दर‑चरण मार्गदर्शिका का पालन
  करें।
linktitle: Update Task Data to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – MPP फ़ॉर्मेट में टास्क डेटा को अपडेट करें
url: /hi/java/task-properties/update-task-data/
weight: 35
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में MPP फ़ॉर्मेट में टास्क डेटा अपडेट करें

## Introduction
हमारे चरण‑दर‑चरण गाइड **Aspose.Tasks for Java का उपयोग करके MPP फ़ॉर्मेट में टास्क डेटा अपडेट करने** के लिए आपका स्वागत है। इस ट्यूटोरियल में आप *aspose tasks java* के साथ प्रोग्रामेटिकली प्रोजेक्ट फ़ाइलों को कैसे मैनीपुलेट करें, सीखेंगे—सारांश टास्क बनाने से लेकर XML प्रोजेक्ट को MPP फ़ाइल में कनवर्ट करने तक। अंत तक आप प्रोजेक्ट टास्क को प्रभावी ढंग से मैनेज कर सकेंगे और इस समाधान को अपने Java एप्लिकेशन में इंटीग्रेट कर सकेंगे।

## Quick Answers
- **इस ट्यूटोरियल में क्या कवर किया गया है?** Aspose.Tasks for Java के साथ टास्क डेटा अपडेट करना और प्रोजेक्ट को MPP के रूप में सेव करना।  
- **क्या मुझे लाइसेंस चाहिए?** प्रोडक्शन उपयोग के लिए एक टेम्पररी या फुल लाइसेंस आवश्यक है; एक फ्री ट्रायल उपलब्ध है।  
- **कौन सा IDE सबसे अच्छा है?** कोई भी Java IDE (IntelliJ IDEA, Eclipse, VS Code) काम करेगा।  
- **क्या मैं XML को MPP में कनवर्ट कर सकता हूँ?** हाँ – उदाहरण एक XML प्रोजेक्ट को लोड करता है और उसे MPP के रूप में सेव करता है।  
- **कितने टास्क बनाए जाते हैं?** इस सैंपल में एक मुख्य टास्क, एक सारांश टास्क, और दस अतिरिक्त टास्क बनते हैं।

## What is Aspose.Tasks for Java?
Aspose.Tasks for Java एक शक्तिशाली API है जो डेवलपर्स को Microsoft Project फ़ाइलें (MPP, XML, आदि) को पढ़ने, लिखने और मॉडिफ़ाई करने की अनुमति देता है, बिना Microsoft Project इंस्टॉल किए। यह पूर्ण प्रोजेक्ट‑लेवल मैनीपुलेशन को सपोर्ट करता है, जिसमें टास्क निर्माण, कॉन्स्ट्रेंट हैंडलिंग, और फ़ाइल फ़ॉर्मेट कनवर्ज़न शामिल हैं।

## Why use Aspose.Tasks Java for project management?
- **Full control** टास्क प्रॉपर्टीज़ जैसे स्टार्ट डेट, ड्यूरेशन, और कॉन्स्ट्रेंट्स पर।  
- **Seamless conversion** XML और MPP के बीच, जिससे मौजूदा प्रोजेक्ट डेटा पाइपलाइन के साथ इंटीग्रेशन आसान हो जाता है।  
- **No COM interop** – शुद्ध Java, क्रॉस‑प्लेटफ़ॉर्म एनवायरनमेंट के लिए आदर्श।  
- **High performance** बड़े प्रोजेक्ट फ़ाइलों के लिए, जिससे एंटरप्राइज़‑स्केल सॉल्यूशंस के लिए उपयुक्त बनता है।

## Prerequisites
ट्यूटोरियल शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित प्री‑रिक्विज़िट्स मौजूद हैं:
- Aspose.Tasks for Java: सुनिश्चित करें कि आपके पास Aspose.Tasks लाइब्रेरी इंस्टॉल है। आप इसे [release page](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।  
- Java Development Kit (JDK): सुनिश्चित करें कि आपके सिस्टम पर Java इंस्टॉल है।  
- Integrated Development Environment (IDE): Java विकास के लिए अपनी पसंद का कोई भी IDE उपयोग करें।

## Import Packages
अपने Java प्रोजेक्ट में आवश्यक पैकेज इम्पोर्ट करके शुरू करें। नीचे दिया गया स्निपेट पैकेज इम्पोर्ट करने का तरीका दर्शाता है:

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

## How to Create a Summary Task
एक सारांश टास्क संबंधित सब‑टास्क को समूहित करता है, जिससे आपको वर्क पैकेज का हाई‑लेवल व्यू मिलता है। नीचे दिए गए कोड में हम एक सारांश टास्क बनाते हैं और पहले टास्क को उसके चाइल्ड के रूप में अटैच करते हैं।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Continue with the rest of the code)
```

## How to Set Start Date for a Task
स्टार्ट डेट सेट करना सटीक शेड्यूलिंग के लिए आवश्यक है। उदाहरण `Calendar` इंस्टेंस का उपयोग करके प्रोजेक्ट स्टार्ट को परिभाषित करता है और उसे टास्क को असाइन करता है।

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Continue with the rest of the code)
```

## How to Convert XML to MPP
API एक XML प्रोजेक्ट फ़ाइल को पढ़ सकता है और सीधे उसे MPP फ़ाइल के रूप में सेव कर सकता है, जिससे लेगेसी फ़ॉर्मेट से आसान माइग्रेशन संभव होता है।

```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Continue with the rest of the code)
```

## How to Set Deadline and Add Task Notes
डेडलाइन टास्क को ट्रैक पर रखने में मदद करती है, जबकि नोट्स टीम मेंबर्स को संदर्भ प्रदान करते हैं।

```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Continue with the rest of the code)
```

## How to Configure Task Constraints and Update Task Duration
*Finish No Later Than* जैसे कॉन्स्ट्रेंट्स शेड्यूलर को मार्गदर्शन देते हैं। आप ड्यूरेशन फ़ॉर्मेट को बदलकर अनुमानित दिनों को भी दर्शा सकते हैं।

```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Continue with the rest of the code)
```

## How to Create Additional Tasks (Managing Project Tasks)
नीचे दिया गया लूप प्रोग्रामेटिकली कई टास्क जेनरेट करने का तरीका दिखाता है, जो बड़े डेटा इम्पोर्ट करने की सामान्य आवश्यकता है।

```java
// Create 10 new tasks
for (int i = 0; i < 10; i++) {
    //... (Continue with the rest of the code)
}
//... (Continue with the rest of the code)
```

## How to Save the Project (Export to MPP)
अंत में, प्रोजेक्ट को MPP फ़ाइल के रूप में सेव करके बदलावों को स्थायी बनाएं।

```java
// Save the Project
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```

इन चरणों को फॉलो करके आपने **aspose tasks java का उपयोग करके MPP फ़ॉर्मेट में टास्क डेटा अपडेट** कर लिया है। अब आपके पास प्रोजेक्ट टास्क मैनेज करने, सारांश टास्क बनाने, स्टार्ट डेट सेट करने, और XML प्रोजेक्ट को MPP में कनवर्ट करने की ठोस नींव है।

## Conclusion
बधाई हो! आपने Aspose.Tasks for Java का उपयोग करके MPP फ़ॉर्मेट में टास्क डेटा अपडेट करने पर एक व्यापक गाइड पूरा कर लिया है। यह शक्तिशाली लाइब्रेरी प्रोजेक्ट मैनेजमेंट टास्क को सरल बनाती है, जिससे Java डेवलपर्स के लिए **प्रोजेक्ट टास्क को प्रोग्रामेटिकली मैनेज** करना आसान हो जाता है।

## Frequently Asked Questions

### Q: Where can I find the Aspose.Tasks for Java documentation?
A: The documentation is available [here](https://reference.aspose.com/tasks/java/).

### Q: How can I download Aspose.Tasks for Java?
A: You can download it from the [release page](https://releases.aspose.com/tasks/java/).

### Q: Is there a free trial available?
A: Yes, you can access the free trial [here](https://releases.aspose.com/).

### Q: Where can I get support for Aspose.Tasks for Java?
A: Visit the support forum [here](https://forum.aspose.com/c/tasks/15).

### Q: Do you offer temporary licenses for testing purposes?
A: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Tasks for Java 24.11 (latest)  
**Author:** Aspose