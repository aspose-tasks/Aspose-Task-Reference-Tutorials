---
title: Aspose.Tasks'ta Sayfaları Ayrı Görüntüye Yazdır
linktitle: Aspose.Tasks'ta Sayfaları Ayrı Görüntüye Yazdır
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'da görüntüleri ayırmak için sayfaları nasıl yazdıracağınızı öğrenin. Bu adım adım kılavuzla proje görselleştirmesini iyileştirin.
weight: 22
url: /tr/java/project-management/print-pages/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Sayfaları Ayrı Görüntüye Yazdır

## giriiş
Bu eğitimde, Aspose.Tasks for Java'yı kullanarak görüntüleri ayırmak için sayfaları yazdırma sürecinde size rehberlik edeceğiz. Bu işlevsellik, proje düzenlerini veya kritik görevleri ayrı ayrı görselleştirmeniz gerektiğinde özellikle yararlı olabilir.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks for Java Kütüphanesi: Aspose.Tasks for Java kütüphanesini indirin ve projenize ekleyin. Şu adresten alabilirsiniz:[Burada](https://releases.aspose.com/tasks/java/).

## Paketleri İçe Aktar
Java dosyanızın başında gerekli paketleri içe aktardığınızdan emin olun:
```java
import com.aspose.tasks.Gridline;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.awt.*;
import java.util.ArrayList;
```
## 1. Adım: Proje Verilerini Yükleyin
Öncelikle proje verilerini MPP dosyanızdan yükleyin:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```
## 2. Adım: Görüntü Kaydetme Seçeneklerini Ayarlayın
Başlangıç tarihi, bitiş tarihi, kritik görevler, açıklamalar ve kılavuz çizgileri dahil olmak üzere görüntüyü kaydetme seçeneklerini tanımlayın:
```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFileFormat.Png);
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.setTime(project.get(Prj.START_DATE));
cal.add(java.util.Calendar.DATE, -3);
saveOptions.setStartDate(cal.getTime());
saveOptions.setEndDate(project.get(Prj.FINISH_DATE));
saveOptions.setMarkCriticalTasks(true);
saveOptions.setLegendOnEachPage(false);
```
## 3. Adım: Kılavuz Çizgilerini Özelleştirin
Tür, renk ve deseni belirterek görüntünün kılavuz çizgilerini özelleştirin:
```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```
## 4. Adım: Görüntüleri Kaydedin
Proje düzenini hem tek bir dosya hem de ayrı dosyalar olarak görüntüler olarak kaydedin:
```java
project.save(dataDir + "CustomerFeedback.png", saveOptions);
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

## Çözüm
Bu eğitimde Aspose.Tasks for Java kullanarak görselleri ayıracak sayfaların nasıl yazdırılacağını gösterdik. Yukarıda özetlenen adımları takip ederek proje düzenlerini ve kritik görevleri gereksinimlerinize göre verimli bir şekilde görselleştirebilirsiniz.
## SSS'ler
### S: Proje düzenlerini kaydederken görüntü formatını özelleştirebilir miyim?
 C: Evet, Aspose.Tasks for Java PNG, JPEG, BMP vb. gibi çeşitli görüntü formatlarını destekler. İstediğiniz formatı`ImageSaveOptions` sınıf.
### S: Aspose.Tasks for Java farklı Java geliştirme ortamlarıyla uyumlu mudur?
C: Evet, Aspose.Tasks for Java, Eclipse, IntelliJ IDEA ve NetBeans dahil çoğu Java geliştirme ortamıyla uyumludur.
### S: Aspose.Tasks for Java'yı Maven veya Gradle projeme entegre edebilir miyim?
C: Evet, Aspose.Tasks for Java'yı Maven veya Gradle projenize uygun bağımlılığı ekleyerek kolayca entegre edebilirsiniz.`pom.xml` veya`build.gradle` dosya.
### S: Aspose.Tasks for Java, proje verilerinin görüntülerin yanı sıra diğer formatlara aktarılmasını da destekliyor mu?
C: Evet, Aspose.Tasks for Java, proje verilerinin PDF, HTML, XLSX vb. gibi çeşitli formatlara aktarılmasını destekleyerek veri görselleştirme ve raporlamada esneklik sağlar.
### S: Aspose.Tasks for Java için topluluk desteği mevcut mu?
 C: Evet, topluluk desteği bulabilir, sorular sorabilir ve diğer kullanıcılarla iletişim kurabilirsiniz.[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
