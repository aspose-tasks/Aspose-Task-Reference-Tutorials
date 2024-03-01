---
title: Aspose.Tasks'ta Görev Listesi ile Altbilgi Arasındaki Boşluğu Azaltma
linktitle: Aspose.Tasks'ta Görev Listesi ile Altbilgi Arasındaki Boşluğu Azaltma
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak MS Project görev listeleri ve alt bilgiler arasındaki boşluğu nasıl azaltacağınızı öğrenin. Proje belgesi düzenini zahmetsizce optimize edin.
type: docs
weight: 10
url: /tr/java/project-file-operations/reduce-gap-tasks-list-footer/
---
## giriiş
Bu eğitimde, Aspose.Tasks for Java'yı kullanarak Microsoft Project dosyalarındaki görev listesi ile alt bilgi arasındaki boşluğu azaltmayı ele alacağız. Bu adımları izleyerek proje belgelerinizin düzenini zahmetsizce optimize edebileceksiniz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun.
2.  Aspose.Tasks for Java Kütüphanesi: Aspose.Tasks for Java kütüphanesini indirin ve projenize ekleyin. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/java/).

## Paketleri İçe Aktar
Kodlama kısmına geçmeden önce gerekli paketleri import edelim:
```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## 1. Adım: Veri Dizininize Giden Yolu Belirleyin
```java
String dataDir = "Your Data Directory";
```
 Değiştirdiğinizden emin olun`"Your Data Directory"` Microsoft Project dosyanızın (`HomeMovePlan.mpp` bu örnekte) bulunur.
## Adım 2: MPP Dosyasını Okuyun
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Bu kod satırı, adlı Microsoft Project dosyasını okur.`HomeMovePlan.mpp`.
## 3. Adım: ImageSaveOptions'ı ayarlayın
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
 Görüntü kaydetme seçeneklerini yapılandırma, ayarlama`ReduceFooterGap` ile`true` görev listesi ile alt bilgi arasındaki boşluğu azaltmak için.
## 4. Adım: Resim Olarak Kaydet
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Projeyi yapılandırılan seçeneklerle görüntü olarak kaydedin.
## Adım 5: PdfSaveOptions'ı ayarlayın
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
 PDF kaydetme seçeneklerini tanımlayın, ayarlanmasını sağlayın`ReduceFooterGap` ile`true`.
## Adım 6: PDF olarak kaydedin
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Projeyi yapılandırılmış seçeneklerle PDF olarak kaydedin.
## Adım 7: HtmlSaveOptions'ı ayarlayın
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // doğru olarak ayarla
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
 HTML kaydetme seçeneklerini belirtin, ayar`ReduceFooterGap` ile`true`.
## 8. Adım: HTML olarak kaydedin
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Projeyi yapılandırılmış seçeneklerle bir HTML dosyası olarak kaydedin.

## Çözüm
Sonuç olarak, Aspose.Tasks for Java ile Microsoft Project dosyalarındaki görev listesi ile alt bilgi arasındaki boşluğu azaltmak basit bir işlemdir. Bu eğitimde özetlenen adımları izleyerek proje belgelerinizin düzenini verimli bir şekilde optimize edebilirsiniz.

## SSS'ler

### S: Aspose.Tasks Microsoft Project'in tüm sürümleriyle uyumlu mu?

C: Aspose.Tasks, Microsoft Project 2003-2019 formatlarını destekleyerek çeşitli sürümler arasında uyumluluk sağlar.

### S: Proje belgelerimde altbilginin görünümünü özelleştirebilir miyim?

C: Evet, Aspose.Tasks, boşlukların azaltılması ve içerik yerleşiminin ayarlanması da dahil olmak üzere altbilgilerin görünümünü özelleştirmek için kapsamlı seçenekler sunar.

### S: Aspose.Tasks, projelerin PNG, PDF ve HTML dışındaki formatlarda kaydedilmesini destekliyor mu?

C: Evet, Aspose.Tasks, diğerlerinin yanı sıra XLSX, XML ve MPP dahil çok çeşitli formatları destekler.

### S: Aspose.Tasks'ın deneme sürümü mevcut mu?

 C: Evet, Aspose.Tasks'ın ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/).

### S: Aspose.Tasks'ı kullanırken herhangi bir sorunla karşılaşırsam nereden destek alabilirim?

 C: Aspose.Tasks topluluk forumundan yardım alabilirsiniz.[Burada](https://forum.aspose.com/c/tasks/15).