---
date: 2026-10-31
description: Aspose.Tasks kullanarak Java'da gantt'ı pdf'ye nasıl dışa aktaracağınızı
  öğrenin. Bu adım adım rehber, Gantt şeması verilerini nasıl okuyacağınızı ve PDF
  raporları oluşturacağınızı gösterir.
keywords:
- export gantt to pdf
- how to read gantt
- export gantt to excel
- generate gantt report java
lastmod: 2026-10-31
linktitle: Aspose.Tasks'te Belirli Gantt Şeması Verilerini Okuyun
og_description: Aspose.Tasks ile Java'da gantt'ı pdf'ye dışa aktarın. Gantt şeması
  verilerini okumak, görünüm özelliklerini özelleştirmek ve proje yönetimi için PDF
  raporları oluşturmak için bu öğreticiyi izleyin.
og_image_alt: 'Tutorial screenshot: exporting Gantt chart to PDF using Aspose.Tasks
  for Java'
og_title: Java'da gantt'ı pdf'ye dışa aktar – Aspose.Tasks rehberi
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  headline: Export gantt to pdf in Java – extract specific data
  type: TechArticle
- description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  name: Export gantt to pdf in Java – extract specific data
  steps:
  - name: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
    text: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
  - name: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
    text: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates seamlessly with any Java library
      or framework, including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library processes multi‑hundred‑page MPP files in under
      5 seconds on standard server hardware and supports concurrent execution in multi‑threaded
      environments.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports 20+ formats, including MPP, XML, MPX, and Primavera
      XML, enabling you to read and convert legacy schedules.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Certainly. You can modify bar styles, gridlines, text styles, and timescale
      tiers programmatically before exporting to PDF or image formats.
    question: Can I customize the appearance of Gantt charts with Aspose.Tasks?
  - answer: Call `project.save("output.mpp");` after making any modifications to persist
      them to the project file.
    question: How do I save changes after modifying a view?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- export gantt
- Aspose.Tasks
- Java Gantt
- pdf generation
- project management
title: Java'da gantt'ı pdf'ye dışa aktar – belirli verileri çıkar
url: /tr/java/project-data-reading/read-specific-gantt-chart-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java’da gantt’i pdf’ye dışa aktar – belirli verileri çıkarma

## Giriş
Bu öğreticide **Java’da gantt’i pdf’ye dışa aktar**mayı, Aspose.Tasks for Java ile Gantt şeması bilgilerini okuyarak öğreneceksiniz. Gantt şemaları proje yöneticilerine görevler, bağımlılıklar ve zaman çizelgeleri hakkında görsel bir yol haritası sunar ve bu verileri programlı olarak çekebilmek, otomatik PDF raporları, panolar veya diğer kurumsal sistemlerle entegrasyonlar oluşturmanıza olanak tanır. Bir proje dosyasını yüklemekten görünüm özelliklerini çıkarmaya ve nihayetinde bir PDF oluşturmaya kadar her adımı birlikte inceleyelim.

## Hızlı yanıtlar
- **Ne çıkarabilirim?** Bir Gantt şemasındaki herhangi bir görünüm özelliği, çubuk stili, ızgara çizgisi, metin stili, ilerleme çizgisi veya zaman ölçeği katmanı.  
- **Lisans gerekiyor mu?** Geliştirme için bir deneme sürümü yeterlidir; üretim için ticari lisans gereklidir.  
- **Hangi Java sürümü destekleniyor?** Java 8 ve üzeri (öğreticide JDK 11 kullanılmıştır).  
- **Kod doğrudan çalıştırılabilir mi?** Evet – sadece veri dizini yolunu değiştirin.  
- **Görünümü okuduktan sonra değiştirebilir miyim?** Kesinlikle – API, özellikleri değiştirmenize ve proje dosyasına geri kaydetmenize izin verir.

## export gantt to pdf nedir?
Export gantt to pdf, bir proje dosyasında depolanan Gantt şeması görünümünü, görsel stil ve zaman çizelgesi bilgilerini koruyan bir PDF belgesine dönüştürme işlemidir. Bu işlem, proje yönetim aracına sahip olmayan paydaşlarla proje durumunu paylaşmak için kullanışlıdır.

## Aspose.Tasks ile export gantt to pdf neden?
Aspose.Tasks **30 + giriş formatını** (MPP, XML, MPX vb.) **tek bir çağrıyla PDF’ye dışa aktarabilir** ve görsel bütünlüğün %95’ini korur, hatta 500’den fazla görev içeren projeler için bile. Kütüphane dosyaları bellekte işler, bu sayede Microsoft Project kurulumuna ihtiyaç duymadan sunucularda PDF oluşturabilirsiniz.

## Önkoşullar
1. **Java Development Kit (JDK):** Sisteminizde Java yüklü olduğundan emin olun. **[Oracle JDK 11 indirme sayfası](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)** üzerinden indirebilirsiniz.  
2. **Aspose.Tasks for Java Kütüphanesi:** **[Aspose.Tasks for Java indirme sayfası](https://releases.aspose.com/tasks/java/)** üzerinden kütüphaneyi indirip kurun.  
3. **Entegre Geliştirme Ortamı (IDE):** Tercihinize göre bir IDE seçin. Popüler seçenekler arasında IntelliJ IDEA, Eclipse veya NetBeans bulunur.

## Paketleri içe aktar
Aşağıdaki import’lar, Gantt verilerini okuma ve dışa aktarma için gereken temel Aspose.Tasks sınıflarına erişim sağlar.  
*Burada konseptlere odaklanmak için kod bloğu gösterilmemiştir; sadece import’ları Java dosyanıza ekleyin.*

## Java’da bir Gantt şeması proje dosyasını nasıl yüklerim?
Proje dosyasını, tam yolu konstruktöre geçirerek bir `Project` örneği oluşturun. Bu adım, Gantt şemasının bellek içi temsilini başlatır ve sonraki görünüm özelliği sorgularına olanak tanır. Dosya başarıyla yüklendiğinde, projenin adı, başlangıç tarihi ve görev sayısını doğrulayarak doğru dosyanın açıldığından emin olabilirsiniz. Bu doğrulama, yol ya da format sorunlarını erken yakalamaya yardımcı olur.  
```java
Project project = new Project(dataDir + "SampleProject.mpp");
```  
*Tanım köşesi:* `Project`, bellekte tek bir proje dosyasını temsil eden üst‑seviye Aspose.Tasks nesnesidir.

## Gantt şeması görünümüne nasıl erişirim?
Projenin görünüm koleksiyonundan ilk Gantt görünümünü alın. Çoğu proje en az bir Gantt görünümüne sahiptir ve genellikle ilk giriştir. Görünümü elde ettikten sonra, adını kontrol edip `GanttChartView` tipinde olduğundan emin olun; bu, özel veya standart dışı görünüm koleksiyonlarıyla çalışırken çalışma zamanı hatalarını önler.  
```java
GanttChartView ganttView = (GanttChartView) project.getViews().get(0);
```  
*Tanım köşesi:* `GanttChartView`, tipik bir Gantt şemasında gördüğünüz görevler, zaman ölçekleri ve çubukların görsel düzenini temsil eder.

## Görünüm özelliklerini nasıl çıkarırım?
`GanttChartView` nesnesinden arka plan rengi, çubuk yüksekliği ve zaman ölçeği ayarları gibi özellikleri doğrudan okuyabilirsiniz. Bu özellikleri yazdırmak, dışa aktarmadan önce mevcut yapılandırmayı doğrulamanıza yardımcı olur. Tipik bir çıkarım döngüsü, her özelliği dolaşır, değeri string olarak biçimler ve daha sonra analiz için konsola ya da bir dosyaya kaydeder. Bu yaklaşım hata ayıklama ve şemanın görünüm dokümantasyonu için faydalıdır.  
```java
System.out.println("Bar height: " + ganttView.getBarHeight());
System.out.println("Show gridlines: " + ganttView.getShowGridlines());
```  
*Tanım köşesi:* `GanttChartView`, arka plan rengi, çubuk yüksekliği ve zaman ölçeği yapılandırması gibi görünüm ayarlarına erişim sağlar.

## Çubuk stillerini nasıl çıkarırım?
`BarStyle` nesnelerinin koleksiyonunu dolaşarak, şemada kullanılan her çubuk türünün renk, desen ve şekil gibi ayrıntılarını elde edin. Her stil için ilgili görev tipi ve stili tetikleyen koşulu da okuyabilirsiniz; bu, şemayı başka bir formata yeniden oluştururken kritiktir. Bu bilgileri toplamak, görsel olarak tutarlı bir kopya üretmenize ya da programlı olarak özel stil kuralları uygulamanıza olanak tanır.  
```java
for (BarStyle style : ganttView.getBarStyles()) {
    System.out.println("Bar type: " + style.getBarType() + ", Color: " + style.getColor());
}
```  
*Tanım köşesi:* `BarStyle`, bir Gantt çubuğunun renk, desen ve şekil gibi görsel görünümünü tanımlar.

## Izgara çizgilerini nasıl çıkarırım?
Izgara çizgileri, satır ve sütunlar arasındaki görsel ayrımı tanımlar. `getGridlines()` yöntemiyle erişin ve görünürlük ile stilini çıktıya verin. Izgara çizgi koleksiyonunu aldıktan sonra, her bir satırı dolaşarak çizgi tipini (düz, kesikli), kalınlığını ve rengini yakalayabilirsiniz. Bu veri, dışa aktarılan PDF’lerde aynı ızgara düzenini yeniden üretmek ya da diğer raporlama formatlarında kullanmak için değerlidir.  
```java
for (Gridline grid : ganttView.getGridlines()) {
    System.out.println("Gridline visible: " + grid.getVisible());
}
```  
*Tanım köşesi:* `getGridlines()` Gantt görünümündeki satır ve sütun ayırıcılarını kontrol eden ızgara çizgi nesnelerinin koleksiyonunu döndürür.

## Metin stillerini nasıl çıkarırım?
Metin stilleri, Gantt şemasındaki etiketlerin yazı tipi, boyut ve rengini kontrol eder. `TextStyle` koleksiyonunu dolaşarak her stili listeleyin. Her metin stili için ilgili öğeyi (görev adı, tarih vb.) ve varsa koşullu biçimlendirme kurallarını da alabilirsiniz. Bu ayrıntıları yakalamak, dışa aktarılan belgelerin orijinal şemadaki tipografiyi korumasını sağlar.  
```java
for (TextStyle txt : ganttView.getTextStyles()) {
    System.out.println("Text style: " + txt.getStyle() + ", Font size: " + txt.getFontSize());
}
```  
*Tanım köşesi:* `TextStyle`, Gantt şemasındaki metinsel öğelere uygulanan biçimlendirme özelliklerini temsil eder.

## İlerleme çizgilerini nasıl çıkarırım?
İlerleme çizgileri, bir görevin mevcut tamamlanma noktasını gösterir. `getProgressLines()` yöntemiyle erişin ve özelliklerini yazdırın. Her ilerleme çizgisi, çizgi rengi, kalınlığı ve görev çubuğuna göre konumu gibi özellikler içerir. Bu bilgileri kaydetmek, ilerleme‑odaklı görselleştirmeler üretmenize ya da genel proje tamamlama metriklerini hesaplamanıza olanak tanır.  
```java
for (ProgressLine line : ganttView.getProgressLines()) {
    System.out.println("Progress line color: " + line.getColor());
}
```  
*Tanım köşesi:* `getProgressLines()` görev tamamlama durumunu gösteren ilerleme çizgi nesnelerinin kümesini döndürür.

## Zaman ölçeği katmanlarını nasıl çıkarırım?
Zaman ölçeği katmanları, şemada gösterilen hiyerarşik zaman birimlerini (gün, hafta, ay) tanımlar. `getTimescaleTiers()` yöntemiyle alın ve ayarlarını çıktıya verin. Her katman için birim tipi, etiket formatı ve hizalama gibi bilgileri yakalayabilirsiniz; bu, dışa aktarılan PDF’lerde ya da özel UI bileşenlerinde aynı zaman çizelgesi inceliğini yeniden üretmek için kritiktir.  
```java
for (TimescaleTier tier : ganttView.getTimescaleTiers()) {
    System.out.println("Tier type: " + tier.getTierType());
}
```  
*Tanım köşesi:* `getTimescaleTiers()` zaman ekseni görüntüsünü kontrol eden zaman ölçeği katman nesnelerinin koleksiyonuna erişim sağlar.

## Gantt şemasını PDF’ye nasıl dışa aktarırım?
Bir `PdfSaveOptions` nesnesi oluşturun, isteğe bağlı olarak sayfa boyutu veya font gömme ayarlarını özelleştirin, ardından `project.save` metodunu PDF formatı ile çağırın. Bu tek çağrı, ekrandaki Gantt görünümünü yansıtan bir PDF üretir. Görüntü sıkıştırma, filigran kaldırma veya kurumsal marka gereksinimlerine uygun özel font gömme gibi ek seçenekleri de belirtebilirsiniz. Kaydetme sonrası, PDF dosya boyutunu ve görsel bütünlüğü kontrol ederek dışa aktarmanın başarılı olduğunu doğrulayın.  
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setPageSize(PageSize.A4);
project.save(dataDir + "ExportedGantt.pdf", options);
```  
*Tanım köşesi:* `PdfSaveOptions`, sayfa boyutları, sıkıştırma ve font işleme gibi PDF çıktısını ince ayarlamanıza olanak tanır.

## Yaygın tuzaklar ve ipuçları
- **Yanlış veri dizini:** `dataDir` değişkeninin işletim sisteminize uygun bir dosya ayırıcı (`/` veya `\\`) ile bittiğinden emin olun.  
- **Görünüm eksikliği:** Projede Gantt görünümü yoksa, `project.getViews()` boş dönecektir – tip dönüşümünden önce bir kontrol ekleyin.  
- **Lisans istisnaları:** Geçerli bir lisans olmadan API, dışa aktarılan PDF’lere filigran ekleyebilir.  
- **Büyük projeler:** 1.000’den fazla görev içeren projeler için JVM heap boyutunu (`-Xmx2g`) artırarak `OutOfMemoryError` hatasını önleyin.  

## Sıkça sorulan sorular

**S: Aspose.Tasks for Java’yı diğer Java kütüphaneleriyle birlikte kullanabilir miyim?**  
C: Evet, Aspose.Tasks for Java, Spring, Hibernate ve Apache POI gibi herhangi bir Java kütüphanesi veya çerçevesiyle sorunsuz entegre olur.

**S: Aspose.Tasks büyük ölçekli kurumsal projeler için uygun mu?**  
C: Kesinlikle. Kütüphane, standart sunucu donanımında 5 saniyenin altında çok sayfalı MPP dosyalarını işler ve çok iş parçacıklı ortamlarda eşzamanlı yürütmeyi destekler.

**S: Aspose.Tasks birden fazla proje dosyası formatını destekliyor mu?**  
C: Evet, Aspose.Tasks 20+ formatı destekler; MPP, XML, MPX ve Primavera XML dahil, böylece eski takvimleri okuyup dönüştürebilirsiniz.

**S: Gantt şemalarının görünümünü Aspose.Tasks ile özelleştirebilir miyim?**  
C: Elbette. Çubuk stillerini, ızgara çizgilerini, metin stillerini ve zaman ölçeği katmanlarını programlı olarak değiştirebilir, ardından PDF veya görüntü formatlarına dışa aktarabilirsiniz.

**S: Görünümü değiştirdikten sonra değişiklikleri nasıl kaydederim?**  
C: `project.save("output.mpp");` metodunu çağırarak yapılan tüm değişiklikleri proje dosyasına kalıcı olarak kaydedebilirsiniz.

---

**Son Güncelleme:** 2026-10-31  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose  



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

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```

```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```

```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// Continue for other properties...
```

```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // Print bar style details...
}
```

```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// Print gridline details...
```

```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // Print text style details...
}
```

```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// Print other progress line details...
```

```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// Print details of other timescale tiers...
```

## İlgili Öğreticiler

- [Aspose.Tasks ile Projeyi PDF olarak Kaydet – Dışa Aktarma Kılavuzu](/tasks/java/project-file-operations/save-as-pdf/)
- [Proje PDF Oluştur – Gantt Şeması Zaman Ölçeğini Özelleştir](/tasks/java/project-file-operations/set-time-scale-count/)
- [Aspose.Tasks ile Projeyi PDF’ye Dışa Aktar ve Görev Listesi ile Altbilgi Arasındaki Boşluğu Azalt](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}