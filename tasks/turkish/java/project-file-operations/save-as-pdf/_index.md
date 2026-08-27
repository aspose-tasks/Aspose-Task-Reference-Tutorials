---
date: 2026-03-27
description: Aspose.Tasks for Java kullanarak projeyi PDF olarak kaydetmeyi öğrenin;
  MPP'yi PDF'ye dönüştürmek ve proje dosyalarını verimli bir şekilde dışa aktarmak
  için basit bir rehber.
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks ile Projeyi PDF Olarak Kaydetme – Dışa Aktarma Rehberi
url: /tr/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspise.Tasks ile Projeyi PDF Olarak Kaydetme – Dışa Aktarma Kılavuzu

## Giriş
Bu öğreticide, Aspose.Tasks for Java kullanarak **projeyi pdf olarak nasıl kaydedeceğinizi** keşfedeceksiniz. Tek satırlık bir dönüşümden gelişmiş PDF özelleştirmesine kadar her şeyi adım adım göstereceğiz, böylece herhangi bir MPP (veya diğer desteklenen format) dosyasını şık, paylaşılabilir bir PDF belgesine dönüştürebileceksiniz. Hızlı bir yazdırılabilir rapor ya da tamamen biçimlendirilmiş bir Gantt şeması ihtiyacınız olsun, bu adımlar sizi hızlıca hedefe ulaştıracak.

## Hızlı Yanıtlar
- **Aspose.Tasks'te “PDF dışa aktar” ne anlama geliyor?** Bir proje dosyasını (ör. MPP) görsel düzeni koruyan bir PDF belgesine dönüştürmek anlamına gelir.  
- **Hangi kütüphane sürümü gerekiyor?** `PdfSaveOptions`'ı destekleyen herhangi bir Aspose.Tasks for Java sürümü (en son sürüm önerilir).  
- **Bu dönüşüm için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim kullanımı için ticari lisans gereklidir.  
- **PDF görünümünü özelleştirebilir miyim?** Evet – zaman ölçeğini, lejandları ve diğer `PdfSaveOptions` ayarlarını belirleyebilirsiniz.  
- **Büyük projeler için dönüşüm hızlı mı?** Genellikle saniyeler içinde; performans proje boyutu ve seçilen seçeneklere bağlıdır.  

## Aspose.Tasks bağlamında “projeyi pdf olarak kaydetmek” ne anlama geliyor?
Aspose.Tasks ile bir projeyi PDF olarak kaydetmek, bir proje dosyasını (ör. `.mpp`, `.xml` veya `.xlsx`) alıp, Gantt şeması, görev kullanım görünümü veya yapılandırdığınız diğer sunum formatını yansıtan bir PDF oluşturmak anlamına gelir. Bu, raporlama, dokümantasyon veya teknik olmayan paydaşlarla yalnızca okunabilir görünümler paylaşmak için faydalıdır.

## Neden Gantt Şemasını PDF Olarak Dışa Aktarıyorsunuz?
- **Evrensel okunabilirlik:** PDF'ler, orijinal proje yazılımına ihtiyaç duymadan herhangi bir cihazda açılabilir.  
- **Profesyonel sunum:** Renkleri, yazı tiplerini ve düzeni, müşteri odaklı raporlar için korur.  
- **Kolay dağıtım:** E-posta, intranet veya bulut depolama üzerinden, sürüm kontrolü endişesi olmadan paylaşabilirsiniz.  
- **Uyumluluk ve arşivleme:** PDF'ler uzun vadeli depolama ve düzenleyici uyumluluk için idealdir.  

## Ön Koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Java Development Kit (JDK):** Makinenizde JDK 8 veya daha yeni bir sürüm yüklü olmalı.  
2. **Aspose.Tasks for Java Kütüphanesi:** Kütüphaneyi resmi siteden [buradan](https://releases.aspose.com/tasks/java/) indirin.  
3. **Bir Proje Dosyası:** Dönüşüm için hazır bir proje dosyanız (ör. `HomeMovePlan.mpp`) olsun.  

## Import Packages
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```

## Step‑by‑Step Guide

### Step 1: Read the Input Project File
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
`"Your Data Directory"` ifadesini `.mpp` dosyanızın bulunduğu mutlak yol ile değiştirin. Bu, projeyi belleğe yükler, böylece üzerinde işlem yapabilir veya dışa aktarabilirsiniz.

### Step 2: Save the Project as PDF (Basic Conversion)
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Yukarıdaki satır, basit bir **projeyi pdf olarak kaydet** işlemini gerçekleştirir ve aynı klasörde `Project5.pdf` dosyasını oluşturur.

### Step 3: Fit Contents to Cell Size (Advanced PDF Save Options)
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Burada, düzeni kontrol etmek için **pdf save options** kullanımını gösteriyoruz:
- `setFitContent(true)` içeriğin hücre genişliğine sığmasını zorlar.  
- `setTimescale(Timescale.Months)` zaman ölçeğini aylara değiştirir.  
- `setPresentationFormat(PresentationFormat.TaskUsage)` Görev Kullanımı görünümünü seçer.

### Step 4: Hide Legends (Cleaner Output)
```java
o.setLegendOnEachPage(false);
```
Lejantları devre dışı bırakmak, özellikle büyük projelerde PDF'yi daha kompakt hale getirebilir.

### Step 5: Save the Project with Applied Options
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Bu son adım, yukarıda tanımlanan özel seçenekleri kullanarak PDF'yi yazar ve sayfa başına lejant olmadan temiz, ay ölçekli bir belge üretir.

## Gantt Şemasını PDF Olarak Dışa Aktar – Özel Stil
Sadece Gantt şemasını belirli bir görünüyle dışa aktarmak istiyorsanız, `PresentationFormat`'u `GanttChart` olarak ayarlayın ve `setBarColor` veya `setShowCriticalTasks` gibi ek seçenekleri düzenleyin. Bu yaklaşım, görsel öğeler üzerinde tam kontrol sağlayarak **gantt şemasını pdf olarak dışa aktarmanıza** olanak tanır.

## Yaygın Sorunlar ve İpuçları
- **Dosya bulunamadı:** `dataDir`'in bir dosya ayırıcı (`/` veya `\\`) ile bittiğinden ve doğru dizini işaret ettiğinden emin olun.  
- **Boş sayfalar:** Seçilen `PresentationFormat`'un beklediğiniz görünüme (ör. Gantt, Görev Kullanımı) uygun olduğunu doğrulayın.  
- **Büyük dosyalar daha uzun sürer:** İşlem süresini azaltmak için çok büyük projelerde `o.setFitContent(false)` ayarlamayı düşünün.  

## Frequently Asked Questions

**Q: Aspose.Tasks tüm Java sürümleriyle uyumlu mu?**  
A: Evet, Aspose.Tasks JDK 6 ve üzeri Java sürümlerini destekler.

**Q: PDF çıktısının görünümünü özelleştirebilir miyim?**  
A: Kesinlikle! Aspose.Tasks, zaman ölçeği, lejant görünürlüğü ve sunum formatı gibi çok sayıda **pdf save options** sunarak PDF'yi ihtiyaçlarınıza göre şekillendirmenizi sağlar.

**Q: Aspose.Tasks başka dosya formatlarını da dönüştürmeyi destekliyor mu?**  
A: Evet, MPP, XML, XLSX ve birçok diğer format arasında dönüşüm yapabilirsiniz; bu da **mpp'yi pdf'ye dönüştürmek** ve diğer dönüşümler için çok yönlü bir araç olmasını sağlar.

**Q: Aspose.Tasks için bir deneme sürümü mevcut mu?**  
A: Evet, Aspose.Tasks'in ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) alabilirsiniz.

**Q: Aspose.Tasks için destek nereden alınabilir?**  
A: Destek ve yardım için resmi [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edin.

## Sonuç
Bu kılavuzu izleyerek, Aspose.Tasks kullanarak herhangi bir Java projesinden **projeyi pdf olarak nasıl kaydedeceğinizi** artık biliyorsunuz; basit tek satırlık kayıttan `PdfSaveOptions` ile gelişmiş özelleştirmeye kadar. Bu teknikleri, raporlama, müşteri sunumları veya arşivleme amaçları için şık ve paylaşılabilir PDF'ler üretmek üzere kullanın.

---

**Son Güncelleme:** 2026-03-27  
**Test Edilen:** Aspose.Tasks for Java 24.12 (yazım zamanı itibarıyla en son)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}