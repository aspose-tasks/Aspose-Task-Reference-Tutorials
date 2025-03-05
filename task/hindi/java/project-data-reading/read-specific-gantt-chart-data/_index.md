---
title: Aspose.Tasks में विशिष्ट गैंट चार्ट डेटा पढ़ें
linktitle: Aspose.Tasks में विशिष्ट गैंट चार्ट डेटा पढ़ें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके विशिष्ट गैंट चार्ट डेटा निकालना सीखें। आपके जावा अनुप्रयोगों में निर्बाध एकीकरण के लिए चरण-दर-चरण ट्यूटोरियल।
type: docs
weight: 16
url: /hi/java/project-data-reading/read-specific-gantt-chart-data/
---
## परिचय
गैंट चार्ट परियोजना प्रबंधन के लिए अमूल्य उपकरण हैं, जो उपयोगकर्ताओं को कार्यों, समयसीमा और निर्भरता की कल्पना करने की अनुमति देते हैं। जावा के लिए Aspose.Tasks के साथ, डेवलपर्स अपने अनुप्रयोगों में एकीकृत करने के लिए गैंट चार्ट से विशिष्ट डेटा को कुशलतापूर्वक निकाल सकते हैं। इस ट्यूटोरियल में, हम आपको चरण दर चरण विशिष्ट गैंट चार्ट डेटा पढ़ने की प्रक्रिया में मार्गदर्शन करेंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1.  जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जावा स्थापित है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  जावा लाइब्रेरी के लिए Aspose.Tasks: जावा लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/java/).
3. एकीकृत विकास पर्यावरण (आईडीई): अपनी पसंद का एक आईडीई चुनें। लोकप्रिय विकल्पों में IntelliJ IDEA, Eclipse, या NetBeans शामिल हैं।

## पैकेज आयात करें
सबसे पहले, Aspose.Tasks कार्यात्मकताओं तक पहुंचने के लिए अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.DateLabel;
import com.aspose.tasks.DayType;
import com.aspose.tasks.Field;
import com.aspose.tasks.FontStyles;
import com.aspose.tasks.GanttBarEndShape;
import com.aspose.tasks.GanttBarMiddleShape;
import com.aspose.tasks.GanttBarShowFor;
import com.aspose.tasks.GanttBarSize;
import com.aspose.tasks.GanttBarStyle;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.Gridlines;
import com.aspose.tasks.Interval;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Project;
import com.aspose.tasks.TextStyle;
import com.aspose.tasks.TimescaleUnit;
```
## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
गैंट चार्ट डेटा वाली प्रोजेक्ट फ़ाइल लोड करके प्रारंभ करें। अपनी डेटा निर्देशिका के लिए पथ प्रदान करें और फ़ाइल नाम निर्दिष्ट करें।
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```
## चरण 2: गैंट चार्ट दृश्य तक पहुंचें
प्रोजेक्ट से गैंट चार्ट दृश्य पुनः प्राप्त करें। हम मान लेंगे कि यह सूची में पहला दृश्य है।
```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```
## चरण 3: दृश्य गुण निकालें
अब, आइए गैंट चार्ट दृश्य के विभिन्न गुणों को निकालें और निरीक्षण के लिए उन्हें प्रिंट करें।
```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// अन्य संपत्तियों के लिए जारी रखें...
```
## चरण 4: बार शैलियाँ निकालें
गैंट चार्ट दृश्य में बार शैलियों के माध्यम से पुनरावृति करें और उनका विवरण प्रिंट करें।
```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // प्रिंट बार शैली विवरण...
}
```
## चरण 5: ग्रिडलाइन्स निकालें
गैंट चार्ट दृश्य में ग्रिडलाइन्स के बारे में जानकारी प्राप्त करें और प्रिंट करें।
```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// ग्रिडलाइन विवरण प्रिंट करें...
```
## चरण 6: टेक्स्ट शैलियाँ निकालें
गैंट चार्ट दृश्य में प्रयुक्त पाठ शैलियों को पुनः प्राप्त करें और प्रिंट करें।
```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // पाठ शैली विवरण प्रिंट करें...
}
```
## चरण 7: प्रगति रेखाएँ निकालें
गैंट चार्ट दृश्य में प्रगति रेखाओं के गुणों तक पहुंचें और प्रिंट करें।
```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// अन्य प्रगति पंक्ति विवरण प्रिंट करें...
```
## चरण 8: टाइमस्केल टियर निकालें
गैंट चार्ट दृश्य में टाइमस्केल स्तरों के बारे में जानकारी प्राप्त करें और प्रिंट करें।
```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// अन्य टाइमस्केल स्तरों का विवरण प्रिंट करें...
```

## निष्कर्ष
बधाई हो! आपने जावा के लिए Aspose.Tasks का उपयोग करके विशिष्ट गैंट चार्ट डेटा को पढ़ना सफलतापूर्वक सीख लिया है। इन चरणों का पालन करके, आप अपने जावा अनुप्रयोगों के भीतर गैंट चार्ट जानकारी को कुशलतापूर्वक निकाल और हेरफेर कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं अन्य जावा लाइब्रेरीज़ के साथ जावा के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: हां, जावा के लिए Aspose.Tasks को अन्य जावा लाइब्रेरी और फ्रेमवर्क के साथ सहजता से एकीकृत करने के लिए डिज़ाइन किया गया है।
### प्रश्न: क्या Aspose.Tasks बड़े पैमाने की उद्यम परियोजनाओं के लिए उपयुक्त है?
उत्तर: बिल्कुल. Aspose.Tasks मजबूत सुविधाएँ और उत्कृष्ट प्रदर्शन प्रदान करता है, जो इसे किसी भी पैमाने की परियोजनाओं के लिए उपयुक्त बनाता है।
### प्रश्न: क्या Aspose.Tasks एकाधिक प्रोजेक्ट फ़ाइल स्वरूपों का समर्थन करता है?
उत्तर: हाँ, Aspose.Tasks MPP, XML और MPX सहित विभिन्न प्रोजेक्ट फ़ाइल स्वरूपों का समर्थन करता है।
### प्रश्न: क्या मैं Aspose.Tasks के साथ गैंट चार्ट के स्वरूप को अनुकूलित कर सकता हूँ?
ए: निश्चित रूप से. Aspose.Tasks आपकी आवश्यकताओं के अनुसार गैंट चार्ट उपस्थिति को अनुकूलित करने के लिए व्यापक एपीआई प्रदान करता है।
### प्रश्न: क्या Aspose.Tasks उपयोगकर्ताओं के लिए तकनीकी सहायता उपलब्ध है?
उत्तर: हां, Aspose.Tasks अपने फोरम और समर्पित समर्थन चैनलों के माध्यम से व्यापक तकनीकी सहायता प्रदान करता है।