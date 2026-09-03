---
date: 2026-05-26
description: Aspose.Tasks for Java kullanarak projeye nasıl view ekleyeceğinizi öğrenin,
  custom view kaydedin ve güçlü MS Project raporlaması için view properties ayarlayın.
keywords:
- add view to project
- save custom view
- persist custom view
- create gantt chart view
- set view properties
linktitle: Aspose.Tasks'te Custom Views
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to add view to project using Aspose.Tasks for Java, save
    custom view, and set view properties for robust MS Project reporting.
  headline: How to Add View to Project with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes – Aspose.Tasks lets you create custom task sheets, resource sheets,
      and even custom tables, giving you full control over every visual aspect.
    question: Can I customize views beyond Gantt charts?
  - answer: Absolutely. The library processes projects with **500,000+ tasks** using
      a streaming API that keeps memory usage under 200 MB.
    question: Is Aspose.Tasks for Java suitable for large‑scale projects?
  - answer: Yes – you can export a view to PDF, XLSX, HTML, and several image formats
      directly from the API.
    question: Does Aspose.Tasks for Java support exporting views to different formats?
  - answer: Certainly. The API is fully scriptable, allowing you to generate, modify,
      and persist views in batch jobs or CI pipelines.
    question: Can I automate the creation of custom views using Aspose.Tasks for Java?
  - answer: Yes, you can get help from other developers and Aspose staff in the [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks for Java support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks ile Projeye View Ekleme
url: /tr/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Projeye Görünüm Ekleme

## Giriş
Eğer **projeye görünüm ekleme** konusunda, raporlarınızın paydaşların tam olarak ihtiyaç duyduğu gibi olmasını istiyorsanız, doğru yerdesiniz. MS Project görünümlerini özelleştirmek, en ilgili verileri ortaya çıkarmanıza, gereksiz detayları ortadan kaldırmanıza ve karar‑alma sürecini hızlandırmanıza olanak tanır. **Aspose.Tasks for Java**, bir MPP dosyası içinde doğrudan özel görünümler oluşturmanızı, yapılandırmanızı ve kalıcı hâle getirmenizi sağlayan güçlü, tip‑güvenli bir API sunar. Bu kılavuzda, ortamı hazırlamaktan görünümleri kaydetmeye kadar her adımı adım adım inceleyeceğiz; böylece şık ve tekrarlanabilir bir çözüm sunabilirsiniz.

## Hızlı Yanıtlar
- **Ana amaç nedir?** Projeye görünüm eklemek ve Aspose.Tasks for Java kullanarak MPP dosyasının içinde kalıcı hâle getirmek.  
- **Hangi sınıf bir görünüm oluşturur?** `GanttChartView` (veya `TaskSheetView` gibi diğer görünüm tipleri).  
- **Görünüm menüde nasıl görünür hâle getirilir?** Kaydetmeden önce `view.setShowInMenu(true)` çağırın.  
- **Görünüm proje ile nasıl kaydedilir?** `MPPSaveOptions` ile `setWriteViewData(true)` kullanın.  
- **Lisans gerekli mi?** Evet – üretim ortamları için geçerli bir Aspose.Tasks lisansı zorunludur.

## “Projeye görünüm ekleme” nedir?
*Projeye bir görünüm eklemek*, yeni bir görsel temsil (ör. Gantt şeması, görev sayfası) oluşturmak ve tanımını MPP dosyasının içine gömmek anlamına gelir; böylece Microsoft Project daha sonra bu görünümü gösterebilir. Bu işlem, Aspose.Tasks ile tamamen programatik olarak yapılır ve manuel UI adımlarını ortadan kaldırır.

## Özel Görünümler Neden Kullanılır?
Aspose.Tasks **50+ görünüm‑ile‑ilgili özellik** destekler ve dosyanın tamamını belleğe yüklemeden **yüzbinlerce görev** içeren projeleri işleyebilir. Bir görünümü bir kez tanımlayıp kalıcı hâle getirerek, tüm ekip üyeleri arasında tutarlı raporlamayı garantiler ve manuel yapılandırma hatası riskini azaltırsınız.

## Önkoşullar
- **Java Development Kit** (JDK 8 veya üzeri) makinenizde kurulu ve yapılandırılmış olmalı.  
- **Aspose.Tasks for Java** kütüphanesi – [buradan](https://releases.aspose.com/tasks/java/) indirebilirsiniz.  
- Üretim kullanımı için geçerli bir **Aspose.Tasks lisans** dosyası (deneme sürümü değerlendirme amaçlı çalışır).

## Paketleri İçe Aktarma
`GanttChartView`, `MPPSaveOptions` ve ilgili sınıflar `com.aspose.tasks` ad alanında bulunur. Kaynak dosyanızın en üst kısmına şu importları ekleyin:

`GanttChartView` bir Gantt şeması görünüm tanımını temsil eder.  
`MPPSaveOptions` bir projenin nasıl kaydedileceğini, görünüm verileri dahil, kontrol eder.  
`Project` MS Project dosyasını temsil eden ana sınıftır.  
`View` tüm görünüm tiplerinin temel sınıfıdır.  

```text
```java
import com.aspose.tasks.Field;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.HorizontalStringAlignment;
import com.aspose.tasks.MPPSaveOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.TableField;
import com.aspose.tasks.View;
```
```

## Adım 1: Projeyi Kurma
Yeni bir `Project` örneği oluşturun ya da mevcut bir dosyayı yükleyin. Bu nesne, görevler, kaynaklar ve görünümler dahil tüm proje verilerini tutar. `Prj`, proje adı gibi proje özellikleri için sabit anahtarlar sağlar.

```text
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```
```

## Adım 2: Görünüm Oluşturma
`GanttChartView`, Aspose.Tasks’in klasik bir Gantt şeması temsilcisidir. Sütunları, çubuk stillerini, zaman ölçeklerini ve daha fazlasını kontrol etmenizi sağlar.

```text
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```
```

## Adım 3: Görünüm Özelliklerini Özelleştirme *(set view properties)*
Burada görünümün görünümünü ince ayar yapabilirsiniz: ilk görünen sütunu ayarlama, çubuk renklerini tanımlama ve zaman ölçeği inceliğini düzenleme. `setShowInMenu(boolean)` görünümün MS Project menüsünde görünüp görünmeyeceğini belirler. `setHighlightFilter(boolean)` ise filtrein görünüm için vurgulanıp vurgulanmayacağını gösterir.

```text
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```
```

### Görünüm Menüsünü Nasıl Gösterilir
`view.setShowInMenu(true)` çağrısı, yeni oluşturulan görünümün MS Project **View** menüsünde yer almasını sağlar; böylece son kullanıcılar ekstra yapılandırma yapmadan anında erişebilir.

## Adım 4: Görünüm Ayarlarını Ayarlama
Sayfa düzeni, yazdırma seçenekleri ve sütun genişlikleri gibi gelişmiş ayarlar bu adımda yapılandırılır. Doğru ayarlama, yazdırılan raporların ekrandaki görünümle aynı olmasını garantiler.

```text
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```
```

## Adım 5: Görünümü Projeye Ekleme *(add custom view java)*
Görünümü yapılandırdıktan sonra, projenin `Views` koleksiyonuna ekleyin. `getViews()` proje içindeki görünüm koleksiyonunu döndürür. Bu adım aslında **projeye görünüm ekleme** işlemini gerçekleştirir ve görünüm dosyanın iç yapısının bir parçası hâline gelir.

```text
```java
// Add the view to our project
project.getViews().add(view);
```
```

## Adım 6: Projeyi Kaydetme *(save project view)*
Projeyi kalıcı hâle getirirken, Aspose.Tasks’e görünüm verilerini yazmasını söylemelisiniz. `MPPSaveOptions` sınıfı bu davranışı kontrol eder. `setWriteViewData(boolean)` kaydedicinin görünüm tanımlarını gömmesini sağlar.

```text
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```
```

### Proje Görünümünü Kaydetmenin Önemi
`options.setWriteViewData(true)` ayarı, Aspose.Tasks’in özel görünüm tanımını MPP dosyasına gömmesini sağlar. Bu bayrak olmadan, görünüm yalnızca bellek içinde kalır ve dosya kapatıldığında kaybolur.

## Adım 7: Görünüm Özelliklerini Kontrol Etme
Kaydetme işleminden sonra projeyi yeniden yükleyebilir ve görünümün UI’da doğru şekilde göründüğünden, tüm özelliklerin (sütunlar, çubuk stilleri vb.) korunduğundan emin olabilirsiniz.

```text
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```
```

## Yaygın Kullanım Durumları
- **Paydaş Raporlaması:** Üst yönetime sadece kilometre taşlarını ve kritik yol görevlerini gösterin.  
- **Kaynak Tahsisi:** Kapasite planlaması için kaynakları görevleriyle yan yana gösterin.  
- **Yazdırılabilir Anlık Görüntüler:** Sayfa boyutu, yönelim ve sütun görünürlüğünü yapılandırarak çevrim dışı inceleme için temiz PDF’ler oluşturun.

## Sorun Giderme İpuçları
- **Görünüm Menüde Görünmüyor:** `view.setShowInMenu(true)` çağrısının *kaydetmeden önce* yapıldığından ve `MPPSaveOptions.setWriteViewData(true)`’ın etkin olduğundan emin olun.  
- **Yazdırmada Sütun Eksikliği:** `setFirstColumnsCount` değerinin tanımladığınız sütun sayısıyla eşleştiğini ve `setPrintFirstColumnsCountOnAllPages(true)`’ın etkin olduğunu kontrol edin.  
- **Lisans İstisnaları:** Herhangi bir `Project` nesnesi oluşturmadan önce `License license = new License(); license.setLicense("Aspose.Tasks.lic");` kodu ile lisans dosyasını yükleyin.

## Sık Sorulan Sorular

**Q:** Gantt şemalarının ötesinde görünümleri özelleştirebilir miyim?  
**A:** Evet – Aspose.Tasks, özel görev sayfaları, kaynak sayfaları ve hatta özel tablolar oluşturmanıza izin verir; böylece görsel her yönü tam kontrol edebilirsiniz.

**Q:** Aspose.Tasks for Java büyük ölçekli projeler için uygun mu?  
**A:** Kesinlikle. Kütüphane, **500.000+ görev** içeren projeleri, bellek kullanımını 200 MB’nin altında tutan bir akış API’si ile işler.

**Q:** Aspose.Tasks for Java görünümleri farklı formatlara dışa aktarmayı destekliyor mu?  
**A:** Evet – API üzerinden bir görünümü doğrudan PDF, XLSX, HTML ve çeşitli görüntü formatlarına dışa aktarabilirsiniz.

**Q:** Aspose.Tasks for Java kullanarak özel görünümlerin oluşturulmasını otomatikleştirebilir miyim?  
**A:** Elbette. API tamamen betiklenebilir; böylece toplu işler veya CI boru hatları içinde görünümleri oluşturabilir, değiştirebilir ve kalıcı hâle getirebilirsiniz.

**Q:** Aspose.Tasks for Java desteği için bir topluluk forumu var mı?  
**A:** Evet, diğer geliştiriciler ve Aspose ekibiyle [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) üzerinden iletişime geçebilirsiniz.

---

**Son Güncelleme:** 2026-05-26  
**Test Edilen Sürüm:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose

## İlgili Eğitimler

- [MPP Dosyası Oluşturma – Boş Projeyi MPP Formatında Oluşturma ve Kaydetme Aspose.Tasks ile](/tasks/java/project-configuration/create-save-mpp/)
- [Aspose.Tasks’te Gantt Şeması Görünümü için Veri Dizinini Ayarlama](/tasks/java/project-configuration/configure-gantt-chart/)
- [Java’da MPP Dosyası Yükleme - Aspose.Tasks ile Proje Özelliklerini Yönetme](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}