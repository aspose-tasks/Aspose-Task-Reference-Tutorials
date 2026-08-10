---
date: 2026-06-15
description: Aspose.Tasks for Java kullanarak mpp'yi pdf'ye dönüştürmeyi ve Resource
  Usage ve Sheet görünümlerini oluşturmayı öğrenin. Timescale ayarlamak ve ayrıntılı
  pdf raporları sorunsuz bir şekilde oluşturmak için adım adım rehberimizi izleyin.
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: MPP'yi PDF'ye Dönüştür ve Resource Usage Görünümünü Oluştur – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: MPP'yi PDF'ye Dönüştür ve Resource Usage Görünümünü Oluştur – Aspose.Tasks
url: /tr/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MPP'yi PDF'ye Dönüştürme ve Kaynak Kullanım Görünümünü Oluşturma – Aspose.Tasks

Bu öğreticide, Microsoft Project dosyasının Kaynak Kullanım ve Sayfa görünümlerini oluştururken **mpp'yi pdf'ye nasıl dönüştüreceğinizi** öğreneceksiniz. Aspose.Tasks for Java kullanmak, sunucuda Microsoft Project'e olan ihtiyacı ortadan kaldırır ve MPP dosyalarından PDF raporları oluşturmanın hızlı ve güvenilir bir yolunu sunar. Ayrıca çıktının raporlama gereksinimlerinize uyması için **zaman ölçeğini nasıl ayarlayacağınızı** göstereceğiz.

## Hızlı Yanıtlar
- **Aspose.Tasks ne yapar?** Microsoft Project (MPP) dosyalarını MS Project yüklü olmadan okur, değiştirir ve dönüştürür.  
- **Bir satır kodla MPP'yi PDF'ye dönüştürebilir miyim?** Evet – Projeyi yükleyin, SaveOptions ayarlayın ve `save` metodunu çağırın.  
- **Hangi zaman ölçekleri desteklenir?** Days, ThirdsOfMonths ve Months.  
- **Üretim için lisansa ihtiyacım var mı?** Deneme dışı dağıtımlar için ticari bir lisans gereklidir.  
- **Kütüphane Java 8+ ile uyumlu mu?** Kesinlikle – Java 8 ve sonraki sürümleri destekler.

## Convert mpp to pdf nedir?
*Convert mpp to pdf*, bir Microsoft Project (.mpp) dosyasını alıp projenin tablolarını, takvimlerini, grafiklerini ve kaynak tahsislerini eksiksiz bir şekilde yeniden üreten Portable Document Format (PDF) sürümünü oluşturma sürecine denir. Ortaya çıkan PDF, alıcı makinede Microsoft Project yüklü olmadan kolayca paylaşılabilir, yazdırılabilir ve arşivlenebilir.

## Aspose.Tasks ile Projeyi PDF'ye Neden Dönüştürmeliyiz?
Aspose.Tasks **50+ giriş ve çıkış formatını** destekler ve tüm dosyayı belleğe yüklemeden çok sayfalı projeleri işleyebilir, RAM kullanımını %70'e kadar azaltır. PDF çıktısı tabloları, grafikleri ve kaynak tahsislerini korur, bu da paydaş dağıtımı ve arşivleme için idealdir.

## Ön Koşullar
1. **Java Development Kit (JDK)** – Makinenizde Java 8 veya daha yeni bir sürüm yüklü.  
2. **Aspose.Tasks for Java** – en son JAR dosyasını [download page](https://releases.aspose.com/tasks/java/) adresinden indirin.  

## Aspose.Tasks for Java kullanarak mpp'yi pdf'ye nasıl dönüştürülür?
Kaynak MPP dosyanızı yükleyin, istediğiniz zaman ölçeğini yapılandırın, sunum formatını **ResourceUsage** olarak ayarlayın ve sonucu PDF olarak kaydedin. Bu uçtan uca akış sadece birkaç API çağrısı gerektirir ve tipik proje boyutları için bir saniyeden kısa sürede çalışır.

### Adım 1: Kaynak Projeyi Oku
`Project` sınıfı, belleğe yüklenmiş bir Microsoft Project dosyasını temsil eder ve verilerine ve yapısına erişim sağlar.  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### Adım 2: Gerekli TimeScale Ayarlarıyla SaveOptions Tanımla
`SaveOptions`, projenin nasıl kaydedileceğini yapılandırır ve zaman ölçeği gibi format‑özel ayarları belirtmenize olanak tanır.  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Adım 3: Sunum Formatını ResourceUsage Olarak Ayarla
`PresentationFormat`, çıktı belgesinde hangi Project görünümünün (ör. ResourceUsage) oluşturulacağını belirler.  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Adım 4: Projeyi PDF Olarak Kaydet
`project.save`, sağlanan `SaveOptions` kullanılarak projeyi bir dosyaya yazar ve nihai PDF'i üretir.  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Adım 5: Diğer TimeScale Ayarları İçin Görünümleri Oluştur
Önceki adımları tekrarlayın, `TimeScale` değerini değiştirerek ek zaman ölçeği görünümleri oluşturun.  
```java
// Save the Project
project.save(dataDir + days, options);
```

### Adım 6: İsteğe Bağlı – Toplu Olarak Birden Çok Projeyi Dönüştür
Birçok dosya için **project to pdf** dönüştürmeniz gerekiyorsa, yukarıdaki mantığı *.mpp* dosyalarının bulunduğu bir dizinde dönen bir döngünün içine yerleştirin. Bu yaklaşım, **ms project pdf** dosyalarını toplu olarak, minimum kod değişikliğiyle kaydeder.  
Aşağıdaki kod, bir MPP dosyasını istenen ayarlarla PDF'ye dönüştüren tam bir örneği gösterir.  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## Yaygın Sorunlar ve Çözümler
- **PDF'de eksik fontlar** – Gerekli fontların sunucuda yüklü olduğundan emin olun veya `PdfSaveOptions` aracılığıyla gömün.  
- **Büyük proje dosyaları OutOfMemoryError hatasına neden olur** – Kaynakları talep üzerine yüklemek için `LoadOptions.setLoadAllResources(false)` kullanın.  
- **Yanlış zaman ölçeği render'ı** – `options.setTimeScale(TimeScale.Days)` (veya diğer enum) istediğiniz ayrıntıya uygun olduğundan emin olun.

## Sık Sorulan Sorular

**Q: Aspose.Tasks, Resource Usage ve Sheet dışındaki diğer görünümleri render edebilir mi?**  
**A: Evet, ayrıca Gantt Chart, Task Usage, Calendar ve birçok ek görünümü destekler.**

**Q: Aspose.Tasks, Microsoft Project dosyalarının farklı sürümleriyle uyumlu mu?**  
**A: Kesinlikle – Project 2000'den Project 2021'e kadar MPP, MPT ve XML formatlarını işler.**

**Q: Render edilen görünümlerin görünümünü özelleştirebilir miyim?**  
**A: Evet, renkleri, fontları ve sütun düzenlerini `PdfSaveOptions` ve `PresentationOptions` aracılığıyla değiştirebilirsiniz.**

**Q: Aspose.Tasks, Microsoft Project'in yüklü olmasını gerektiriyor mu?**  
**A: Hayır, bağımsız bir kütüphanedir ve herhangi bir Java‑uyumlu ortamda çalışır.**

**Q: Teknik destek nereden alınabilir?**  
**A: Destek, [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/) üzerinden sağlanmaktadır.**

---

**Son Güncelleme:** 2026-06-15  
**Test Edilen:** Aspose.Tasks 24.12 for Java  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Tasks'te Kaynak Kullanım ve Sayfa Görünümünü Oluştur](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [Aspose.Tasks'te PDF'yi Dışa Aktarma – PDF Olarak Kaydet](/tasks/java/project-file-operations/save-as-pdf/)
- [Aspose.Tasks for Java ile MPP Dosyaları Oluşturma](/tasks/java/project-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}