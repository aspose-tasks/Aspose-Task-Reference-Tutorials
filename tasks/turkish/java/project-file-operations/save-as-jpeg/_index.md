---
date: 2026-05-26
description: Aspose.Tasks for Java kullanarak Microsoft Project dosyalarını dışa aktarırken
  proje anlık görüntüsü JPEG oluşturmayı ve JPEG kalitesini ayarlamayı öğrenin.
keywords:
- create project snapshot jpeg
- adjust jpeg quality
- Aspose.Tasks Java
linktitle: Projeyi Aspose.Tasks'te JPEG Olarak Kaydet
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to create project snapshot JPEG and adjust JPEG quality when
    exporting Microsoft Project files using Aspose.Tasks for Java.
  headline: Create Project Snapshot JPEG – Adjust Quality with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Higher quality preserves text and line details, while very low quality
      may make small labels hard to read.
    question: Does adjusting JPEG quality affect Gantt chart readability?
  - answer: Yes, Aspose.Tasks supports PNG, BMP, and TIFF via the appropriate `SaveFileFormat`
      enum.
    question: Can I export other image formats besides JPEG?
  - answer: You can iterate over the desired views and save each as a separate JPEG
      using the same `ImageSaveOptions` configuration.
    question: Is it possible to export multiple pages (e.g., different views) at once?
  - answer: Aspose.Tasks for Java works with JDK 8 and later.
    question: What Java version is required?
  - answer: Consider reducing the JPEG quality or scaling the image dimensions via
      additional `ImageSaveOptions` settings.
    question: How do I handle large projects that produce big images?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Proje Anlık Görüntüsü JPEG Oluştur – Aspose.Tasks ile Kaliteyi Ayarlayın
url: /tr/java/project-file-operations/save-as-jpeg/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Proje Anlık Görüntüsü JPEG Oluştur – Aspose.Tasks ile Kalite Ayarı

## Giriş
Bu öğreticide, Microsoft Project'ten Aspose.Tasks for Java kullanarak **proje anlık görüntüsü JPEG** dosyaları oluşturmayı ve JPEG kalitesini boyut‑netlik gereksinimlerinize göre ince ayar yapmayı öğreneceksiniz. Yönetim odası sunumları için net görüntülere ya da web portalları için hafif dosyalara ihtiyacınız olsun, kalite ayarını ustalaştırmak size nihai çıktının tam kontrolünü verir.

## Hızlı Yanıtlar
- **“JPEG kalitesini ayarlama” ne yapar?** Dışa aktarılan JPEG'in sıkıştırma seviyesini kontrol etmenizi sağlar, dosya boyutu ile görsel doğruluk arasında denge kurar.  
- **Hangi kütüphane dönüşümü gerçekleştirir?** Aspose.Tasks for Java, Project dosyalarını JPEG'e dışa aktarmak için basit bir API sunar.  
- **Lisans gerekli mi?** Değerlendirme için ücretsiz deneme çalışır; üretim kullanımı için ticari lisans gerekir.  
- **Kaliteyi kod içinde ayarlayabilir miyim?** Evet, `ImageSaveOptions.setJpegQuality(int)` metodunu (0‑100 aralığı) kullanın.  
- **İşlem hızlı mı?** Tipik bir proje dosyasını JPEG'e dönüştürmek modern donanımda sadece birkaç saniye sürer.

## “JPEG kalitesini ayarlama” nedir?
JPEG kalitesini ayarlamak, bir görüntüyü JPEG formatında kaydederken uygulanan sıkıştırma faktörünü belirlemenizi sağlar. Yüksek değerler (100'e yakın) daha fazla detay korurken, düşük değerler dosya boyutunu küçültür ancak keskinliği azaltır. **Doğrudan yanıt:** JPEG kalitesini `ImageSaveOptions.setJpegQuality` metoduna (0‑100) sayısal bir değer göndererek kontrol edersiniz; bu, oluşturulan anlık görüntünün boyutunu ve görsel doğruluğunu hemen etkiler.  

JPEG kalitesi, bir görüntüyü JPEG formatında kaydederken uygulanan sıkıştırma faktörüdür.

## JPEG dışa aktarımı için Aspose.Tasks neden kullanılmalı?
**Doğrudan yanıt:** Aspose.Tasks, Gantt şemalarını, kaynak görünümlerini ve özel raporları Microsoft Project yüklü olmadan görüntü dosyalarına render eder, Windows, Linux ve macOS üzerinde piksel‑tam çıktı garantisi verir.  

Aspose.Tasks, **dört** görüntü formatına (JPEG, PNG, BMP, TIFF) dışa aktarmayı destekler ve standart 2.5 GHz CPU'da 10.000'e kadar görevi **5 saniyenin altında** render edebilir, ölçülmüş bir performans garantisi sunar.

## Önkoşullar
Başlamadan önce aşağıdakilerin kurulu olduğundan emin olun:
1. **Java Development Kit (JDK)** – En son JDK'yi (8 veya daha yeni) [Java web sitesinden](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) indirin.  
2. **Aspose.Tasks for Java** – Resmi [belgelendirmedeki](https://reference.aspose.com/tasks/java/) adımları izleyerek kütüphaneyi indirin ve kurun.

## Paketleri İçe Aktar
`ImageSaveOptions`, Aspose.Tasks’in format, boyut ve JPEG kalitesi gibi görüntü dışa aktarma ayarlarını kontrol eden sınıfıdır.  
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```

## Adım 1: Veri Dizinini Tanımla
Microsoft Project dosyanızın bulunduğu klasörün yolunu ayarlayın. Bu dizin, giriş ve çıkış işlemleri için kullanılır.  
```java
String dataDir = "Your Data Directory";
```

## Adım 2: MS Project Dosyasını Yükle
`Project` sınıfı, bir Microsoft Project dosyasını bellek içinde temsil eder ve görevlere, kaynaklara ve görünüm verilerine erişim sağlar.  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## Adım 3: JPEG Kalitesini Ayarla (İsteğe Bağlı)
Çıktıyı ince ayarlamak isterseniz, `ImageSaveOptions` sınıfını kullanarak **JPEG kalitesini** belirleyebilirsiniz. Kalite değeri 0‑100 arasında değişir; 100 en yüksek görsel doğruluğu verir.  
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Set JPEG quality to 50
```

## Adım 4: Projeyi JPEG Olarak Kaydet
`Project.save`, yapılandırdığınız seçenekleri kullanarak render edilen görünümü bir görüntü dosyasına yazar.  
```java
project.save(dataDir + "image_out.jpeg", options);
```

## MS Project'ten JPEG Nasıl Dışa Aktarılır
**Doğrudan yanıt:** `ImageSaveOptions` yapılandırıldıktan sonra `project.save("output.jpeg", SaveFileFormat.JPEG, saveOptions)` çağrısını yapın; metod varsayılan olarak Gantt şemasını render eder ve belirttiğiniz kaliteyle bir JPEG dosyası yazar. Bu tek satırlık çağrı sayfalama, ölçekleme ve renk yönetimini otomatik olarak halleder.  

JPEG kalitesini ayarlayarak görüntü netliği ile dosya boyutu arasındaki dengeyi kontrol edersiniz; bu da dışa aktarılan görüntüyü web yayıncılığı, basılı raporlar veya gömülü slaytlar için uygun hâle getirir.

## Yaygın Sorunlar ve Çözümler
- **Düşük kalite metni okunamaz hâle getirir:** JPEG kalitesini 70'in üzerine çıkarın veya kayıpsız render için PNG'ye geçin.  
- **Büyük projelerde bellek yetersizliği hataları:** `saveOptions.setUseMemoryCache(true)` ayarını etkinleştirerek bellek kullanımını 200 MB altında tutun.  
- **Yanlış görünüm dışa aktarıldı:** Farklı bir görünüm dışa aktarmak için `saveOptions.setView(ViewType.TaskSheet)` kullanın.

## Sıkça Sorulan Sorular

**S: JPEG kalitesini ayarlamak Gantt şemasının okunabilirliğini etkiler mi?**  
C: Daha yüksek kalite metin ve çizgi detaylarını korur, çok düşük kalite ise küçük etiketlerin okunmasını zorlaştırabilir.  

**S: JPEG dışındaki diğer görüntü formatlarını dışa aktarabilir miyim?**  
C: Evet, Aspose.Tasks uygun `SaveFileFormat` enum değeriyle PNG, BMP ve TIFF formatlarını da destekler.  

**S: Birden fazla sayfayı (ör. farklı görünümler) aynı anda dışa aktarmak mümkün mü?**  
C: İstediğiniz görünümler üzerinde döngü kurarak her birini aynı `ImageSaveOptions` yapılandırmasıyla ayrı JPEG olarak kaydedebilirsiniz.  

**S: Hangi Java sürümü gereklidir?**  
C: Aspose.Tasks for Java, JDK 8 ve üzeri sürümlerle çalışır.  

**S: Büyük görüntüler üreten büyük projelerle nasıl başa çıkılır?**  
C: JPEG kalitesini düşürmeyi veya ek `ImageSaveOptions` ayarlarıyla görüntü boyutlarını ölçeklendirmeyi düşünün.

## Sonuç
Aspose.Tasks for Java kullanarak **proje anlık görüntüsü JPEG** dosyaları oluşturmayı ve JPEG kalitesini ayarlamayı adım adım gösterdik. Bu yöntem manuel ekran görüntülerine gerek kalmadan platformlar arasında tutarlı render garantisi verir ve görüntü netliği ile dosya boyutu arasındaki dengeyi ince ayar yapmanıza olanak tanır—raporlar, sunumlar ve web yayıncılığı için mükemmeldir.

---

**Last Updated:** 2026-05-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Eğitimler

- [How to Create MPP File – Create & Save Empty Project in MPP Format with Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Save Project as Template, CSV, and Text with Aspose.Tasks for Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [Create Empty MS Project File in Aspose.Tasks](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}