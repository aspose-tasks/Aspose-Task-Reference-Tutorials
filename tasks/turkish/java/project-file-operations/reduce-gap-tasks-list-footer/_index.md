---
date: 2026-05-20
description: Aspose.Tasks for Java kullanarak projeyi PDF'ye nasıl dışa aktaracağınızı,
  altbilgi boşluğunu nasıl azaltacağınızı ve projeyi görüntü olarak nasıl kaydedeceğinizi
  öğrenin. MS Project düzeninizi zahmetsizce optimize edin.
keywords:
- export project to pdf
- save project as image
- reduce footer gap
- remove white space pdf
- how to reduce footer gap
linktitle: Projeyi PDF'ye Dışa Aktar ve Aspose.Tasks'te Görev Listesi ile Altbilgi
  Arasındaki Boşluğu Azalt
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to export project to PDF, reduce footer gap, and save project
    as image using Aspose.Tasks for Java. Optimize your MS Project layout effortlessly.
  headline: Export Project to PDF and Reduce Gap Between Tasks List and Footer in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It minimizes blank space at the bottom of each page, allowing more tasks
      to fit on a single page and reducing the total page count.
    question: How does reducing the footer gap affect pagination?
  - answer: Yes, by setting `setRenderToSinglePage(true)` in `ImageSaveOptions` you
      can control pagination while still reducing the gap.
    question: Can I apply the same gap‑reduction setting to a single page only?
  - answer: Currently it is supported for PNG, PDF, and HTML exports. For other formats
      you may need to adjust layout manually.
    question: Is the `setReduceFooterGap` option available for other output formats?
  - answer: All custom fields are retained during export; the layout adjustments only
      affect spacing, not data.
    question: What if my project contains custom fields—are they preserved?
  - answer: Aspose.Tasks streams data and can process multi‑hundred‑page MPP files
      without loading the entire file into memory; however, allocate sufficient heap
      space when exporting high‑resolution images.
    question: Does the library handle large projects efficiently?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Projeyi PDF'ye Dışa Aktar ve Aspose.Tasks'te Görev Listesi ile Altbilgi Arasındaki
  Boşluğu Azalt
url: /tr/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projeyi PDF Olarak Dışa Aktarma ve Aspose.Tasks'te Görev Listesi ile Altbilgi Arasındaki Boşluğu Azaltma

## Giriş  
Bu öğreticide **projeyi PDF olarak dışa aktarmanın** nasıl yapılacağını ve Microsoft Project dosyalarında görev listesi ile altbilgi arasındaki istenmeyen boşluğun nasıl azaltılacağını keşfedeceksiniz. Kılavuzun sonunda Aspose.Tasks for Java kullanarak temiz PDF'ler, PNG görüntüler ve HTML sayfaları, sıkı bir düzenle oluşturabileceksiniz. Süreci adım adım inceleyeceğiz ve bunun profesyonel raporlamada neden önemli olduğunu göreceksiniz.

## Hızlı Yanıtlar  
- **“Projeyi PDF olarak dışa aktarma” ne anlama geliyor?** Bir MPP dosyasını görevleri, zaman çizelgelerini ve biçimlendirmeyi koruyan bir PDF belgesine dönüştürür.  
- **Neden altbilgi boşluğunu azaltmalıyım?** Daha küçük bir boşluk, özellikle basılı veya web üzerinden görüntülenen belgelerde daha sıkı, daha profesyonel görünümlü raporlar oluşturur.  
- **Projeyi aynı zamanda bir görüntü olarak kaydedebilir miyim?** Evet – Aspose.Tasks PNG, JPEG ve diğer görüntü formatlarını destekler.  
- **Özel bir lisansa ihtiyacım var mı?** Ücretsiz bir deneme sürümü mevcuttur; üretim kullanımı için ticari lisans gereklidir.  
- **Hangi Java sürümü gereklidir?** Java 8 veya üzeri, mevcut Aspose.Tasks kütüphanesiyle çalışır.  

## “Projeyi PDF Olarak Dışa Aktarma” Nedir?  
Projeyi PDF olarak dışa aktarmak, içsel MPP yapısını herhangi bir cihazda Microsoft Project'e ihtiyaç duymadan açılabilen taşınabilir bir belgeye dönüştürür. Bu, durum raporları, paydaş güncellemeleri veya proje planlarının arşivlenmesi için idealdir. Orijinal düzeni, renkleri ve görev hiyerarşisini korur, böylece PDF kaynağa birebir eşdeğer görünür.

## Neden Altbilgi Boşluğunu Azaltmalıyız?  
Varsayılan altbilgi boşluğu gereksiz beyaz alan ekleyerek sayfalama sorunlarına ve dengesiz bir görünüme yol açabilir. Boşluğun azaltılması, içeriğin sayfayı verimli kullanmasını sağlar ve son PDF ya da görüntünün daha okunabilir olmasını temin eder. Daha sıkı bir düzen aynı zamanda toplam sayfa sayısını azaltır, bu da baskı maliyetlerini düşürür ve ekrandaki gezinmeyi iyileştirir.

## Görev Listesi ile Altbilgi Arasındaki Boşluğu Nasıl Azaltabilirsiniz?  
`setReduceFooterGap` dışa aktarma sırasında altbilgi boşluğunu kontrol eden bir Boolean özelliktir.  
Aspose.Tasks, görüntü, PDF ve HTML kaydetme işlemleri için `setReduceFooterGap(true)` seçeneği sunar. Bu bayrağın etkinleştirilmesi, motorun son görev satırı ile sayfa altbilgisi arasındaki boşluğu sıkıştırmasını sağlar. `true` olarak ayarlandığında, renderlayıcı herhangi bir görev verisini kesmeden otomatik olarak kenarı kırpar ve daha temiz bir sayfa düzeni üretir.

## Aspose.Tasks ile Projeyi Görüntü Olarak Kaydet  
`ImageSaveOptions` bir projenin görüntü dosyasına nasıl render edileceğini yapılandırır.  
`ImageSaveOptions` sınıfı, bir zaman çizelgesi anlık görüntüsünü PNG, JPEG veya BMP olarak dışa aktarmanıza olanak tanır. `setReduceFooterGap(true)` özelliğini de etkinleştirdiğinizde, oluşturulan görüntü sıkı PDF düzenini yansıtarak sunumlar veya panolar için temiz bir görsel sağlar.

## Java Proje Dışa Aktarma PDF  
Aşağıdaki bölümler, MPP dosyasını yüklemekten üç farklı formatta kaydetmeye kadar tam bir **java proje dışa aktarma** iş akışını adım adım gösterir.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşulları karşıladığınızdan emin olun:
1. Java Development Kit (JDK) – sürüm 8 veya daha yeni.  
2. Aspose.Tasks for Java Library – indirmek için [burada](https://releases.aspose.com/tasks/java/).  

## Paketleri İçe Aktarma  
Kodlama kısmına geçmeden önce gerekli paketleri içe aktaralım:

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

## Adım 1: Veri Dizininizin Yolunu Belirtin  
```java
String dataDir = "Your Data Directory";
```  
`"Your Data Directory"` ifadesini, Microsoft Project dosyanızın (`HomeMovePlan.mpp` bu örnekte) bulunduğu gerçek veri dizininizin yolu ile değiştirin.

## Adım 2: MPP Dosyasını Oku  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```  
Bu kod satırı, `HomeMovePlan.mpp` adlı Microsoft Project dosyasını okur.

## Adım 3: ImageSaveOptions Ayarla (Projeyi Görüntü Olarak Kaydet)  
`ImageSaveOptions` bir projenin görüntü dosyasına nasıl render edileceğini yapılandırır.  
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```  
Görüntü kaydetme seçeneklerini yapılandırın, `ReduceFooterGap` özelliğini `true` olarak ayarlayarak görev listesi ile altbilgi arasındaki boşluğu azaltın.

## Adım 4: Görüntü Olarak Kaydet  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```  
Projeyi yapılandırılmış seçeneklerle bir görüntü olarak kaydedin.

## Adım 5: PdfSaveOptions Ayarla (Projeyi PDF Olarak Dışa Aktar)  
`PdfSaveOptions` bir projeyi PDF formatına dışa aktarırken ayarları belirler.  
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```  
PDF kaydetme seçeneklerini tanımlayın, `ReduceFooterGap` özelliğini `true` olarak ayarlamayı unutmayın.

## Adım 6: PDF Olarak Kaydet  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```  
Projeyi yapılandırılmış seçeneklerle bir PDF olarak kaydedin.

## Adım 7: HtmlSaveOptions Ayarla  
`HtmlSaveOptions` bir projeyi HTML'ye dönüştürürken stil ve düzen seçeneklerini kontrol eder.  
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```  
HTML kaydetme seçeneklerini belirtin, `ReduceFooterGap` özelliğini `true` olarak ayarlayın.

## Adım 8: HTML Olarak Kaydet  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```  
Projeyi yapılandırılmış seçeneklerle bir HTML dosyası olarak kaydedin.

## Yaygın Kullanım Senaryoları ve İpuçları  
- **Paydaş raporlaması:** Raporları kısa ve yazıcı dostu tutmak için altbilgi boşluğu azaltılmış PDF dışa aktarımı.  
- **Pano anlık görüntüleri:** Power BI veya Confluence için hızlı bir görsel gerektiğinde görüntü dışa aktarımı.  
- **Web yayıncılığı:** HTML dışa aktarımı etkileşimi korur ve doğrudan intranet portalına gömülebilir.  
- **Pro ipucu:** Çok büyük projeler için `ImageSaveOptions` içinde `Resolution` değerini 300 dpi'ye yükselterek netliği korurken boşluk azaltımından faydalanabilirsiniz.

## Sıkça Sorulan Sorular (Ek)

**Q: Altbilgi boşluğunu azaltmak sayfalama üzerinde nasıl bir etki yapar?**  
A: Her sayfanın alt kısmındaki boş alanı en aza indirir, böylece daha fazla görev tek bir sayfaya sığar ve toplam sayfa sayısı azalır.

**Q: Aynı boşluk azaltma ayarını yalnızca tek bir sayfaya uygulayabilir miyim?**  
A: Evet, `ImageSaveOptions` içinde `setRenderToSinglePage(true)` ayarlayarak sayfalama kontrolü yapabilir ve yine boşluğu azaltabilirsiniz.

**Q: `setReduceFooterGap` seçeneği diğer çıktı formatları için de mevcut mu?**  
A: Şu anda PNG, PDF ve HTML dışa aktarmaları için desteklenir. Diğer formatlar için düzeni manuel olarak ayarlamanız gerekebilir.

**Q: Projemde özel alanlar varsa—bunlar korunur mu?**  
A: Tüm özel alanlar dışa aktarım sırasında korunur; düzen ayarlamaları yalnızca boşlukları etkiler, veri kaybı olmaz.

**Q: Kütüphane büyük projeleri verimli bir şekilde işliyor mu?**  
A: Aspose.Tasks verileri akış olarak işler ve çok sayfalı MPP dosyalarını belleğe tamamen yüklemeden işleyebilir; ancak yüksek çözünürlüklü görüntüler dışa aktarırken yeterli heap alanı ayırmanız gerekir.

---

**Son Güncelleme:** 2026-05-20  
**Test Edilen Versiyon:** Aspose.Tasks 24.11 for Java  
**Yazar:** Aspose

## İlgili Eğitimler

- [Projeyi Görüntü Olarak Kaydet – 24bppRgb Formatı Aspose.Tasks ile](/tasks/java/project-file-operations/render-data-format-24bppRgb/)
- [Projeyi Şablon, CSV ve Metin Olarak Kaydet Aspose.Tasks for Java ile](/tasks/java/project-file-operations/save-csv-text-template/)
- [MPP Dosyası Nasıl Oluşturulur – Boş Projeyi MPP Formatında Oluştur ve Kaydet Aspose.Tasks ile](/tasks/java/project-configuration/create-save-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}