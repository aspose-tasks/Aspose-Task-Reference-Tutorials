---
date: 2025-12-17
description: Aspose.Tasks for Java kullanarak projeyi PDF'ye nasıl dışa aktaracağınızı,
  altbilgi boşluğunu nasıl azaltacağınızı ve projeyi görüntü olarak nasıl kaydedeceğinizi
  öğrenin. MS Project düzeninizi zahmetsizce optimize edin.
linktitle: Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks
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
Bu öğreticide **projeyi PDF olarak dışa aktarmayı** ve Microsoft Project dosyalarında görev listesi ile altbilgi arasındaki istenmeyen boşluğu azaltmayı öğreneceksiniz. Rehberin sonunda Aspose.Tasks for Java kullanarak temiz PDF'ler, PNG görüntüler ve HTML sayfaları, sıkı bir yerleşimle oluşturabileceksiniz. Adım adım ilerleyelim.

## Hızlı Yanıtlar  
- **“Projeyi PDF olarak dışa aktarmak” ne anlama geliyor?** MPP dosyasını görevleri, zaman çizelgeleri ve biçimlendirmeyi koruyarak bir PDF belgesine dönüştürür.  
- **Altbilgi boşluğunu neden azaltmalıyım?** Daha küçük bir boşluk, özellikle yazdırılan veya web üzerinden görüntülenen belgelerde daha sıkı ve profesyonel raporlar oluşturur.  
- **Projeyi görüntü olarak da kaydedebilir miyim?** Evet – Aspose.Tasks PNG, JPEG ve diğer görüntü formatlarını destekler.  
- **Özel bir lisansa ihtiyacım var mı?** Ücretsiz deneme sürümü mevcuttur; üretim kullanımı için ticari lisans gereklidir.  
- **Hangi Java sürümü gerekiyor?** Java 8 veya üzeri, mevcut Aspose.Tasks kütüphanesiyle çalışır.

## “Projeyi PDF olarak dışa aktarmak” nedir?  
Projeyi PDF olarak dışa aktarmak, iç MPP yapısını, Microsoft Project'e ihtiyaç duymadan herhangi bir cihazda açılabilen taşınabilir bir belgeye dönüştürür. Durum raporları, paydaş güncellemeleri veya proje planlarını arşivlemek için idealdir.

## Altbilgi Boşluğunu Azaltmak Neden Önemli?  
Varsayılan altbilgi boşluğu gereksiz beyaz alan ekleyerek sayfalama sorunlarına ve dengesiz bir görünüme yol açar. Boşluğun azaltılması, içeriğin sayfayı verimli kullanmasını sağlar ve son PDF ya da görüntünün okunabilirliğini artırır.

## Görev Listesi ile Altbilgi Arasındaki Boşluk Nasıl Azaltılır?  
Aspose.Tasks, görüntü, PDF ve HTML kaydetme işlemleri için `setReduceFooterGap(true)` seçeneğini sunar. Bu bayrağın etkinleştirilmesi, son görev satırı ile sayfa altbilgisi arasındaki boşluğu sıkıştırır.

## Aspose.Tasks ile Projeyi Görüntü Olarak Kaydetme  
Programınızın takvimine görsel bir anlık görüntü eklemek isterseniz, **projeyi görüntü olarak kaydedebilir** (PNG) ve aynı boşluk‑azaltma ayarlarını uygulayabilirsiniz.

## Java Projesi ile PDF Dışa Aktarma  
Aşağıdaki bölümler, MPP dosyasını yüklemekten üç farklı formatta kaydetmeye kadar tam bir **java proje dışa aktarma** iş akışını adım adım gösterir.

## Ön Koşullar
Başlamadan önce aşağıdaki ön koşulları karşıladığınızdan emin olun:
1. Java Development Kit (JDK) – sürüm 8 veya üzeri.  
2. Aspose.Tasks for Java Kütüphanesi – **[buradan](https://releases.aspose.com/tasks/java/)** indirebilirsiniz.  

## Paketleri İçe Aktarma
Kodlamaya geçmeden önce gerekli paketleri içe aktaralım:
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
`"Your Data Directory"` ifadesini, Microsoft Project dosyanızın (`HomeMovePlan.mpp` bu örnekte) bulunduğu gerçek veri dizini yolu ile değiştirin.

## Adım 2: MPP Dosyasını Oku
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Bu satır, `HomeMovePlan.mpp` adlı Microsoft Project dosyasını okur.

## Adım 3: ImageSaveOptions Ayarla (Projeyi Görüntü Olarak Kaydet)
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
Görüntü kaydetme seçeneklerini yapılandırın, `ReduceFooterGap` değerini `true` yaparak görev listesi ile altbilgi arasındaki boşluğu azaltın.

## Adım 4: Görüntü Olarak Kaydet
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Projeyi, yapılandırılmış seçeneklerle bir görüntü olarak kaydedin.

## Adım 5: PdfSaveOptions Ayarla (Projeyi PDF Olarak Dışa Aktar)
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
PDF kaydetme seçeneklerini tanımlayın, `ReduceFooterGap` değerini `true` olarak ayarladığınızdan emin olun.

## Adım 6: PDF Olarak Kaydet
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Projeyi, yapılandırılmış seçeneklerle bir PDF dosyası olarak kaydedin.

## Adım 7: HtmlSaveOptions Ayarla
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
HTML kaydetme seçeneklerini belirleyin, `ReduceFooterGap` değerini `true` yapın.

## Adım 8: HTML Olarak Kaydet
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Projeyi, yapılandırılmış seçeneklerle bir HTML dosyası olarak kaydedin.

## Sonuç  
Sonuç olarak, Microsoft Project dosyalarında görev listesi ile altbilgi arasındaki boşluğun azaltılması, Aspose.Tasks for Java ile oldukça basit bir işlemdir. Bu öğreticideki adımları izleyerek **projeyi PDF olarak dışa aktarabilir**, görüntü olarak kaydedebilir veya HTML oluşturabilir, aynı zamanda düzeni sıkı ve profesyonel tutabilirsiniz.

## SSS

### S: Aspose.Tasks tüm Microsoft Project sürümleriyle uyumlu mu?

C: Aspose.Tasks, Microsoft Project 2003‑2019 formatlarını destekler ve çeşitli sürümlerle uyumluluk sağlar.

### S: Proje belgelerimde altbilginin görünümünü özelleştirebilir miyim?

C: Evet, Aspose.Tasks altbilgi görünümünü özelleştirmek için geniş seçenekler sunar; boşlukları azaltma ve içerik yerleşimini ayarlama gibi.

### S: Aspose.Tasks PNG, PDF ve HTML dışındaki formatları da destekliyor mu?

C: Evet, Aspose.Tasks XLSX, XML, MPP ve daha birçok formatı destekler.

### S: Aspose.Tasks için bir deneme sürümü var mı?

C: Evet, **[buradan](https://releases.aspose.com/)** ücretsiz bir deneme sürümü indirebilirsiniz.

### S: Aspose.Tasks kullanırken sorun yaşarsam nereden destek alabilirim?

C: Aspose.Tasks topluluk forumundan **[burada](https://forum.aspose.com/c/tasks/15)** yardım alabilirsiniz.

## Sıkça Sorulan Sorular (Ek)

**S: Altbilgi boşluğunu azaltmak sayfalama üzerinde nasıl bir etki yapar?**  
C: Her sayfanın alt kısmındaki boş alanı en aza indirir, daha fazla görevin tek bir sayfada yer almasını sağlar ve toplam sayfa sayısını azaltır.

**S: Boşluk‑azaltma ayarını yalnızca tek bir sayfaya uygulayabilir miyim?**  
C: Evet, `ImageSaveOptions` içinde `setRenderToSinglePage(true)` ayarını kullanarak sayfalama kontrolü yapabilir ve aynı zamanda boşluğu azaltabilirsiniz.

**S: `setReduceFooterGap` seçeneği diğer çıktı formatları için mevcut mu?**  
C: Şu anda PNG, PDF ve HTML dışa aktarmaları için desteklenir. Diğer formatlarda yerleşimi manuel olarak ayarlamanız gerekebilir.

**S: Projemde özel alanlar varsa bunlar korunur mu?**  
C: Tüm özel alanlar dışa aktarma sırasında korunur; yerleşim ayarlamaları yalnızca boşlukları etkiler, veri kaybı olmaz.

**S: Kütüphane büyük projeleri verimli bir şekilde işliyor mu?**  
C: Aspose.Tasks verileri akış (stream) olarak işler ve büyük MPP dosyalarını işleyebilir; yüksek çözünürlüklü görüntülere dışa aktarırken yeterli belleğe sahip olduğunuzdan emin olun.

---

**Son Güncelleme:** 2025-12-17  
**Test Edilen Versiyon:** Aspose.Tasks 24.11 for Java  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}