---
title: Aspose.Tasks'ta PDF Olarak Kaydet
linktitle: Aspose.Tasks'ta PDF Olarak Kaydet
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak proje dosyalarını PDF'ye nasıl dönüştüreceğinizi öğrenin. Verimli dönüşüm için basit adımlar.
type: docs
weight: 17
url: /tr/java/project-file-operations/save-as-pdf/
---
## giriiş
Bu eğitimde, Aspose.Tasks for Java'yı kullanarak bir projeyi PDF olarak kaydetme sürecinde size rehberlik edeceğiz. Aspose.Tasks ile proje dosyalarınızı verimli bir şekilde PDF formatına dönüştürebilir, uyumluluk ve paylaşım kolaylığı sağlayabilirsiniz. Adımlara geçelim:
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun.
2.  Aspose.Tasks for Java Library: Aspose.Tasks kütüphanesini indirin ve yükleyin. İndirme linkini bulabilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
3. Proje Dosyası: PDF'ye dönüştürmek istediğiniz bir proje dosyanızı (örn. HomeMovePlan.mpp) hazır bulundurun.

## Paketleri İçe Aktar
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## Adım 1: Giriş Projesi Dosyasını Okuyun
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Değiştirdiğinizden emin olun`"Your Data Directory"` proje dosyasını içeren veri dizininizin yolu ile.
## Adım 2: Projeyi PDF olarak kaydedin
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Bu kod pasajı, projeyi "Project5.pdf" adıyla bir PDF dosyası olarak kaydeder.
## Adım 3: İçeriği Hücre Boyutuna Uydurma
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Burada, uygun içerik, zaman ölçeği ve sunum formatı da dahil olmak üzere PDF'yi kaydetme seçeneklerini ayarlıyoruz.
## Adım 4: Efsaneleri Gizleyin
```java
o.setLegendOnEachPage(false);
```
Bu adım, PDF'nin her sayfasındaki efsaneleri gizler.
## Adım 5: Projeyi Uygulanan Seçeneklerle Kaydetme
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Son olarak, bu kod projeyi uygulanan seçeneklerle birlikte bir PDF dosyasına kaydeder.

## Çözüm
Bu eğitimde Aspose.Tasks for Java'yı kullanarak bir projeyi PDF olarak kaydetmeyi öğrendik. Bu basit adımları izleyerek proje dosyalarınızı kolay paylaşım ve dağıtım için verimli bir şekilde dönüştürebilirsiniz.
## SSS'ler
### S: Aspose.Tasks Java'nın tüm sürümleriyle uyumlu mu?
C: Evet, Aspose.Tasks, JDK 6 ve üzeri Java sürümlerini destekler.
### S: PDF çıktısının görünümünü özelleştirebilir miyim?
C: Kesinlikle! Aspose.Tasks, PDF çıktısını gereksinimlerinize göre özelleştirmeniz için çeşitli seçenekler sunar.
### S: Aspose.Tasks dönüştürme için diğer dosya formatlarını destekliyor mu?
C: Evet, Aspose.Tasks, MPP, XML, XLSX ve daha fazlasını içeren çok çeşitli dosya formatlarını destekler.
### S: Aspose.Tasks'ın deneme sürümü mevcut mu?
 C: Evet, Aspose.Tasks'ın ücretsiz deneme sürümünü şu adresten edinebilirsiniz:[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks için nereden destek alabilirim?
 C: Destek ve yardım için şu adresi ziyaret edebilirsiniz:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).