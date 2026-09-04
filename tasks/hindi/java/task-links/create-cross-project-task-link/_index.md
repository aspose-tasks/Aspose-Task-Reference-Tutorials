---
date: 2026-07-05
description: Aspose.Tasks for Java के साथ प्रोजेक्ट्स के बीच टास्क लिंक करना सीखें।
  चरण‑दर‑चरण गाइड, आवश्यकताएँ, और सहज क्रॉस‑प्रोजेक्ट टास्क लिंकिंग के लिए सर्वोत्तम
  प्रथाएँ।
keywords:
- link tasks across projects
- Aspose.Tasks Java
- cross‑project task link
linktitle: Aspose.Tasks में क्रॉस‑प्रोजेक्ट टास्क लिंक बनाएं
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  headline: Link Tasks Across Projects Using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  name: Link Tasks Across Projects Using Aspose.Tasks for Java
  steps:
  - name: Set Up Your Environment
    text: 'Ensure the Aspose.Tasks JAR is on the classpath and the license file is
      loaded at runtime: `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`
      **License** loads your Aspose.Tasks license file to enable full functionality
      and remove evaluation watermarks.'
  - name: Create a Project Instance
    text: 'Instantiate a new `Project` object for the target project where you want
      the link to live: `Project targetProject = new Project();` The `Project` class
      is Aspose.Tasks'' top‑level object that represents a single project file in
      memory.'
  - name: Add a Summary Task
    text: 'A summary task groups related tasks. Create one to hold both the external
      and local tasks: `Task summary = targetProject.getRootTask().getChildren().add("Integration
      Summary");`'
  - name: Add External Task
    text: 'Insert an external task that points to a task in another project file:
      `Task external = summary.getChildren().addExternalTask("ExternalProject.mpp",
      5);` The **addExternalTask** method creates a placeholder task that references
      an external project file, using the provided file name and task ID.'
  - name: Add Local Task
    text: 'Create the task that will be linked to the external one: `Task local =
      summary.getChildren().add("Local Task");`'
  - name: Create Task Link
    text: 'Establish a dependency between the external and local tasks. The most common
      link type is Finish‑to‑Start: `TaskLink link = targetProject.getTaskLinks().add(external,
      local, TaskLinkType.FinishToStart);` **TaskLink** records the relationship;
      you can later modify its lag, lead, or type as needed.'
  - name: Save and Verify
    text: 'Persist the project to a file and optionally open it in Microsoft Project
      to verify the link: `targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`
      **SaveFileFormat** specifies the file format for saving a project. When you
      open *LinkedProject.mpp*, you’ll see the external task displayed wi'
  type: HowTo
- questions:
  - answer: Yes, you can add several external tasks under one summary task and create
      individual links for each, using the same `addExternalTask` method.
    question: Can I link tasks from multiple external projects in the same summary
      task?
  - answer: Any change to the external task’s schedule, duration, or constraints is
      automatically reflected in the dependent local task when the target project
      is refreshed.
    question: What happens if the external task in the linked project is modified?
  - answer: Absolutely. Aspose.Tasks supports linking between MPP, XML, and Primavera
      formats, allowing heterogeneous project ecosystems to stay synchronized.
    question: Is it possible to create links between tasks in different file formats?
  - answer: Yes, remove the link by calling `project.getTaskLinks().remove(link)`
      or by deleting the external task placeholder.
    question: Can I unlink tasks once they are linked across projects?
  - answer: The library can handle **10,000+ linked tasks** per project, limited only
      by available system memory and the underlying file format specifications.
    question: Are there any limitations on the number of tasks that can be linked
      across projects?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट्स के बीच टास्क लिंक करें
url: /hi/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट्स के बीच कार्यों को लिंक करना

## परिचय
प्रोजेक्ट्स के बीच कार्यों को लिंक करना एक मुख्य क्षमता है जो आपको कार्यों को समन्वयित करने, दोहराव से बचने, और परस्पर‑निर्भर गतिविधियों के लिए एक ही सत्य स्रोत बनाए रखने की अनुमति देती है। इस ट्यूटोरियल में आप Aspose.Tasks for Java के साथ **प्रोजेक्ट्स के बीच कार्यों को लिंक** करना चरण‑दर‑चरण सीखेंगे। अंत तक आपके पास एक पूरी तरह कार्यात्मक क्रॉस‑प्रोजेक्ट लिंक होगा जो किसी भी पक्ष में परिवर्तन होने पर स्वचालित रूप से अपडेट हो जाता है, जिससे आपको मैन्युअल कॉपी‑पेस्ट के बिना रीयल‑टाइम समन्वय मिलता है।

## त्वरित उत्तर
- **प्रोजेक्ट बनाने के लिए मुख्य क्लास कौन सी है?** `Project` – यह मेमोरी में पूरे MS‑Project फ़ाइल का प्रतिनिधित्व करता है।  
- **बाहरी कार्य जोड़ने वाला मेथड कौन सा है?** `project.getRootTask().getChildren().addExternalTask(...)`.  
- **क्या मैं लिंक प्रकार सेट कर सकता हूँ?** हाँ – `TaskLinkType.FinishToStart`, `StartToStart` आदि का उपयोग करें।  
- **क्या लिंकिंग के लिए लाइसेंस आवश्यक है?** उत्पादन उपयोग के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है; मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है।  
- **लिंक्ड टास्क पर कोई सीमा है?** Aspose.Tasks प्रति प्रोजेक्ट 10,000+ लिंक्ड टास्क को बिना प्रदर्शन गिरावट के संभाल सकता है।

## प्रोजेक्ट्स के बीच कार्यों को लिंक करना क्या है?
प्रोजेक्ट्स के बीच कार्यों को लिंक करना एक प्रोजेक्ट फ़ाइल में एक कार्य और दूसरे प्रोजेक्ट फ़ाइल में एक कार्य के बीच निर्भरतात्मक संबंध बनाता है, जिससे स्रोत कार्य (अवधि, प्रारंभ तिथि, प्रतिबंध) में परिवर्तन स्वचालित रूप से निर्भर कार्य तक पहुँचता है। यह तंत्र शेड्यूल को संरेखित रखता है, मैन्युअल अपडेट को कम करता है, और सुनिश्चित करता है कि स्रोत प्रोजेक्ट में कोई भी संशोधन तुरंत सभी लिंक्ड प्रोजेक्ट्स में परिलक्षित हो, जिससे पोर्टफ़ोलियो में निरंतरता बनी रहती है।

## क्रॉस‑प्रोजेक्ट लिंकिंग के लिए Aspose.Tasks का उपयोग क्यों करें?
Aspose.Tasks **50+ इनपुट और आउटपुट फ़ॉर्मेट** का समर्थन करता है और **सैकड़ों‑पृष्ठों वाले प्रोजेक्ट्स** को 200 MB से कम मेमोरी में प्रोसेस कर सकता है। इसका API सर्वर‑साइड पर लिंकिंग करता है, जिससे Microsoft Project की स्थापना की आवश्यकता नहीं रहती और बड़े उद्यमों के लिए स्वचालित पाइपलाइन सक्षम होते हैं।

## पूर्वापेक्षाएँ
- Java 17 (या बाद का) आपके IDE में स्थापित और कॉन्फ़िगर किया हुआ।  
- एक वैध Aspose.Tasks for Java लाइसेंस फ़ाइल (`Aspose.Tasks.Java.lic`)।  
- Aspose.Tasks for Java लाइब्रेरी को अपने प्रोजेक्ट में जोड़ें। आप इसे [Aspose.Tasks for Java रिलीज़ पेज](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।  
- MS‑Project की अवधारणाओं जैसे कार्य, सारांश कार्य, और निर्भरताओं की बुनियादी समझ।

## पैकेज आयात करें
`Project`, `Task`, `TaskLink`, और संबंधित enums `com.aspose.tasks` नेमस्पेस में स्थित हैं। इन्हें अपनी Java फ़ाइल के शीर्ष पर आयात करें:

`import com.aspose.tasks.*;`

**Project** मेमोरी में प्रोजेक्ट फ़ाइल का प्रतिनिधित्व करने वाली मुख्य क्लास है। **Task** प्रोजेक्ट के भीतर एक व्यक्तिगत कार्य आइटम को दर्शाता है। **TaskLink** दो कार्यों के बीच निर्भरतात्मक संबंध को परिभाषित करता है। ये आयात आपको प्रोजेक्ट मैनिपुलेशन की पूरी सूट तक पहुँच देते हैं, जिसमें क्रॉस‑प्रोजेक्ट लिंकिंग भी शामिल है।

## प्रोजेक्ट्स के बीच कार्यों को कैसे लिंक करें?
दो प्रोजेक्ट फ़ाइलें लोड करें, एक बाहरी कार्य प्लेसहोल्डर जोड़ें, एक स्थानीय कार्य बनाएं, और फिर उन्हें `TaskLink` के साथ कनेक्ट करें। API ID मैपिंग और अपडेट को स्वचालित रूप से संभालता है, जिससे बाहरी कार्य में कोई भी परिवर्तन अतिरिक्त कोड के बिना लिंक्ड स्थानीय कार्य में प्रसारित हो जाता है। यह दृष्टिकोण मल्टी‑प्रोजेक्ट समन्वय को सरल बनाता है और शेड्यूल ड्रिफ्ट के जोखिम को कम करता है।

### चरण 1: अपना वातावरण सेट करें
Aspose.Tasks JAR को क्लासपाथ पर रखें और रनटाइम पर लाइसेंस फ़ाइल लोड करें:

`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`

**License** आपके Aspose.Tasks लाइसेंस फ़ाइल को लोड करता है ताकि पूरी कार्यक्षमता सक्षम हो और मूल्यांकन वॉटरमार्क हट जाएँ।

### चरण 2: एक प्रोजेक्ट इंस्टेंस बनाएं
लिंक जहाँ रहना चाहिए, उस लक्ष्य प्रोजेक्ट के लिए नया `Project` ऑब्जेक्ट बनाएं:

`Project targetProject = new Project();`

`Project` क्लास Aspose.Tasks की टॉप‑लेवल ऑब्जेक्ट है जो मेमोरी में एकल प्रोजेक्ट फ़ाइल का प्रतिनिधित्व करती है।

### चरण 3: एक सारांश कार्य जोड़ें
सारांश कार्य संबंधित कार्यों को समूहित करता है। बाहरी और स्थानीय दोनों कार्यों को रखने के लिए एक बनाएं:

`Task summary = targetProject.getRootTask().getChildren().add("Integration Summary");`

### चरण 4: बाहरी कार्य जोड़ें
एक बाहरी कार्य डालें जो दूसरे प्रोजेक्ट फ़ाइल में किसी कार्य की ओर संकेत करता है:

`Task external = summary.getChildren().addExternalTask("ExternalProject.mpp", 5);`

**addExternalTask** मेथड एक प्लेसहोल्डर कार्य बनाता है जो प्रदान किए गए फ़ाइल नाम और कार्य ID के साथ बाहरी प्रोजेक्ट फ़ाइल को संदर्भित करता है।

### चरण 5: स्थानीय कार्य जोड़ें
उस कार्य को बनाएं जो बाहरी कार्य से लिंक किया जाएगा:

`Task local = summary.getChildren().add("Local Task");`

### चरण 6: टास्क लिंक बनाएं
बाहरी और स्थानीय कार्यों के बीच निर्भरतात्मक संबंध स्थापित करें। सबसे सामान्य लिंक प्रकार Finish‑to‑Start है:

`TaskLink link = targetProject.getTaskLinks().add(external, local, TaskLinkType.FinishToStart);`

**TaskLink** संबंध को रिकॉर्ड करता है; आप बाद में इसकी लैग, लीड या प्रकार को आवश्यकतानुसार संशोधित कर सकते हैं।

### चरण 7: सहेजें और सत्यापित करें
प्रोजेक्ट को फ़ाइल में सहेजें और वैकल्पिक रूप से Microsoft Project में खोलकर लिंक की जाँच करें:

`targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`

**SaveFileFormat** प्रोजेक्ट को सहेजने के फ़ॉर्मेट को निर्दिष्ट करता है। जब आप *LinkedProject.mpp* खोलेंगे, तो आपको बाहरी कार्य एक विशेष आइकन के साथ दिखेगा और निर्भरतात्मक रेखा स्थानीय कार्य की ओर संकेत करेगी।

## सामान्य समस्याएँ और समाधान
- **बाहरी फ़ाइल नहीं मिली** – सुनिश्चित करें कि पथ चल रहे प्रोसेस के सापेक्ष है या एक पूर्ण पथ प्रदान करें।  
- **टास्क ID मेल नहीं खाती** – सत्यापित करें कि `addExternalTask` के दूसरे आर्ग्यूमेंट में दिया गया बाहरी टास्क ID स्रोत प्रोजेक्ट से मेल खाता है।  
- **लाइसेंस लोड नहीं हुआ** – गायब या गलत लाइसेंस फ़ाइल `LicenseException` उत्पन्न करती है। किसी भी Aspose.Tasks कॉल से पहले इसे लोड करें।  
- **बड़े प्रोजेक्ट्स पर प्रदर्शन** – जब आपको केवल बाहरी कार्य पढ़ने की आवश्यकता हो तो `Project.setReadOnly(true)` का उपयोग करें; इससे मेमोरी ओवरहेड कम हो जाता है।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं एक ही सारांश कार्य में कई बाहरी प्रोजेक्ट्स के कार्यों को लिंक कर सकता हूँ?**  
A: हाँ, आप एक सारांश कार्य के तहत कई बाहरी कार्य जोड़ सकते हैं और प्रत्येक के लिए अलग‑अलग लिंक बना सकते हैं, वही `addExternalTask` मेथड उपयोग करके।

**Q: यदि लिंक्ड प्रोजेक्ट में बाहरी कार्य संशोधित किया जाता है तो क्या होता है?**  
A: बाहरी कार्य के शेड्यूल, अवधि या प्रतिबंध में कोई भी परिवर्तन लक्ष्य प्रोजेक्ट को रिफ्रेश करने पर स्वचालित रूप से निर्भर स्थानीय कार्य में परिलक्षित हो जाता है।

**Q: क्या विभिन्न फ़ाइल फ़ॉर्मेट्स के बीच कार्यों को लिंक करना संभव है?**  
A: बिल्कुल। Aspose.Tasks MPP, XML, और Primavera फ़ॉर्मेट्स के बीच लिंकिंग का समर्थन करता है, जिससे मिश्रित प्रोजेक्ट इकोसिस्टम सिंक्रनाइज़ रह सकते हैं।

**Q: क्या एक बार लिंक बन जाने के बाद कार्यों को अनलिंक किया जा सकता है?**  
A: हाँ, `project.getTaskLinks().remove(link)` कॉल करके या बाहरी कार्य प्लेसहोल्डर को हटाकर लिंक को हटा सकते हैं।

**Q: प्रोजेक्ट्स के बीच लिंक किए जा सकने वाले कार्यों की संख्या पर कोई सीमा है?**  
A: लाइब्रेरी प्रति प्रोजेक्ट **10,000+ लिंक्ड टास्क** को संभाल सकती है, जो केवल उपलब्ध सिस्टम मेमोरी और अंतर्निहित फ़ाइल फ़ॉर्मेट स्पेसिफिकेशन पर निर्भर करता है।

## निष्कर्ष
आपके पास अब Aspose.Tasks for Java का उपयोग करके **प्रोजेक्ट्स के बीच कार्यों को लिंक** करने की एक पूर्ण, उत्पादन‑तैयार विधि है। यह क्षमता मल्टी‑प्रोजेक्ट समन्वय को सरल बनाती है, मैन्युअल प्रयास को कम करती है, और सुनिश्चित करती है कि शेड्यूल परिवर्तन तुरंत आपके पूरे पोर्टफ़ोलियो में प्रसारित हों। कस्टम लैग टाइम, विभिन्न लिंक प्रकार, और बल्क लिंकिंग जैसी अतिरिक्त सुविधाओं का अन्वेषण करें ताकि जटिल प्रोजेक्ट संरचनाओं को और अधिक स्वचालित किया जा सके।

---

**अंतिम अपडेट:** 2026-07-05  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

```java
Project project = new Project();
```

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

```java
Task t = summary.getChildren().add("Task");
```

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

```java
System.out.println("Process completed Successfully");
```

## संबंधित ट्यूटोरियल

- [Aspose.Tasks में टास्क लिंक बनाएं](/tasks/java/task-links/create-task-link/)
- [Aspose Java में टास्क बनाएं – टास्क प्रॉपर्टीज़](/tasks/java/task-properties/)
- [Aspose.Tasks में खाली MS Project फ़ाइल बनाएं](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}