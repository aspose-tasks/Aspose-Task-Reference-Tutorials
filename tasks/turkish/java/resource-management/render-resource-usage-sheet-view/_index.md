---
date: 2026-01-15
description: Aspose.Tasks for Java kullanarak projeyi PDF olarak kaydetmeyi ve MS
  Project Kaynak Kullanımı ile Sayfa görünümlerini render etmeyi öğrenin. Projeyi
  PDF'ye zahmetsizce dışa aktarmak için adım adım rehberimizi izleyin.
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projeyi PDF Olarak Kaydet – Aspose.Tasks'te Kaynak Kullanımı ve Sayfa Görünümünü
  Oluştur
url: /tr/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projeyi PDF Olarak Kaydet – Aspose.Tasks'te Kaynak Kullanımı ve Sayfa Görünümünü Oluşturma

## Giriş
Bu öğreticide **projeyi PDF olarak kaydet** özelliğini, bir Microsoft Project dosyasının Kaynak Kullanımı ve Sayfa görünümlerini oluştururken nasıl kullanacağınızı keşfedeceksiniz. Paydaşlar için yazdırılabilir bir rapor oluşturmanız ya da MPP dosyalarını evrensel olarak görüntülenebilir bir formata dönüştürmeniz gerektiğinde, Aspose.Tasks for Java süreci basitleştirir—Microsoft Project kurulumu gerektirmez.

## Hızlı Yanıtlar
- **“projeyi PDF olarak kaydet” ne yapar?** Bir Project dosyasını (MPP) seçilen görünümü koruyarak bir PDF belgesine dönüştürür.  
- **Hangi görünüm dışa aktarılabilir?** Resource Usage, Sheet, Gantt, Task Usage ve daha fazlası.  
- **PDF'de zaman ölçeğini değiştirebilir miyim?** Evet—seçenekler Days, ThirdsOfMonths ve Months içerir.  
- **Microsoft Project yüklü olması gerekiyor mu?** Hayır, Aspose.Tasks bağımsız çalışır.  
- **Üretim için lisans gerekli mi?** Evet, deneme dışı kullanım için ticari bir lisans gereklidir.

## “projeyi PDF olarak kaydet” nedir?
Projeyi PDF olarak kaydetmek, seçilen bir Project görünümünün statik, yüksek çözünürlüklü bir temsilini oluşturur. Bu, müşterilerle paylaşmak, arşivlemek veya temel proje dosyasını ortaya çıkarmadan yazdırmak için idealdir.

## Projeyi PDF olarak dışa aktarmak için neden Aspose.Tasks kullanmalı?
- **Harici bağımlılık yok** – Java destekleyen herhangi bir platformda çalışır.  
- **İnce ayarlı kontrol** – görünümü, zaman ölçeğini ve düzeni seçebilirsiniz.  
- **Yüksek doğruluk** – PDF, orijinal Project görünümünün görünümünü yansıtır.  
- **Otomasyona hazır** – CI boru hatlarına, raporlama hizmetlerine veya toplu dönüştürücülere entegre edebilirsiniz.

## Önkoşullar
Öncelikle aşağıdakilere sahip olduğunuzdan emin olun:

1. **Java Development Kit (JDK)** – en son sürüm önerilir.  
2. **Aspose.Tasks for Java** – [download page](https://releases.aspose.com/tasks/java/) adresinden indirin.  

## Paketleri İçe Aktarma
İlk olarak, Java projenize gerekli sınıfları içe aktarın:

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Adım Adım Kılavuz

### Adım 1: Kaynak Projeyi Oku
Dönüştürmek istediğiniz MPP dosyasını yükleyin.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Adım 2: Gerekli Zaman Ölçeği ile SaveOptions Tanımla (Projeyi PDF Olarak Dışa Aktar)
PDF dışa aktarma seçeneklerini yapılandırın ve istediğiniz zaman ölçeğini ayarlayın.  
*Burada örnek olarak **Days** kullanıyoruz.*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Adım 3: Sunum Formatını ResourceUsage Olarak Ayarla
Oluşturmak istediğiniz görünümü seçin. Bu örnekte **Resource Usage** görünümü kullanılmaktadır.

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Adım 4: Projeyi Kaydet (MPP'yi PDF'ye Dönüştür)
Dönüştürmeyi çalıştırın ve PDF dosyasını oluşturun.

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### Adım 5: Diğer Zaman Ölçeği Ayarları İçin Görünümleri Oluştur (Zaman Ölçeğini Değiştir PDF)
**ThirdsOfMonths** ve **Months** gibi farklı zaman ölçekleriyle PDF'ler üretmek için önceki adımları tekrarlayın.

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## Yaygın Sorunlar ve Çözümleri
- **Dosya bulunamadı hataları** – `dataDir`'in doğru klasöre işaret ettiğini ve MPP dosya adının tam olarak eşleştiğini doğrulayın.  
- **Boş PDF çıktısı** – `PresentationFormat`'un veri içeren bir görünüme (ör. ResourceUsage) eşleştiğinden emin olun.  
- **Yanlış zaman ölçeği** – `options.setTimescale()`'un her `project.save()` öncesinde çağrıldığını iki kez kontrol edin.

## Sık Sorulan Sorular

### Aspose.Tasks, Resource Usage ve Sheet dışındaki diğer görünümleri oluşturabilir mi?
Aspose.Tasks, Gantt Chart, Task Usage ve Calendar görünümleri gibi çeşitli görünümleri oluşturmayı destekler.

### Aspose.Tasks farklı Microsoft Project dosya sürümleriyle uyumlu mu?
Evet, Aspose.Tasks MPP, MPT ve XML formatları dahil olmak üzere geniş bir Microsoft Project dosya formatı yelpazesini destekler.

### Aspose.Tasks kullanarak oluşturulan görünümlerin görünümünü özelleştirebilir miyim?
Kesinlikle! Aspose.Tasks, oluşturulan görünümlerin görünümünü ve düzenini belirli gereksinimlerinize göre özelleştirmenize olanak tanıyan kapsamlı seçenekler sunar.

### Aspose.Tasks sistemde Microsoft Project'in yüklü olmasını gerektiriyor mu?
Hayır, Aspose.Tasks bağımsız bir kütüphanedir ve çalışması için Microsoft Project'in yüklü olmasını gerektirmez.

### Aspose.Tasks kullanıcıları için teknik destek mevcut mu?
Evet, Aspose.Tasks kullanıcıları teknik desteği [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) üzerinden alabilirler.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-01-15  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose