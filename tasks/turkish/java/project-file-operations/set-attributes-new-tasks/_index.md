---
date: 2025-12-21
description: Aspose.Tasks for Java kullanarak proje oluşturmayı ve yeni görevler için
  MS Project özelliklerini ayarlamayı, projeyi XML olarak kaydetmeyi ve görev özelliklerini
  özelleştirmeyi öğrenin.
linktitle: Set Attributes for New Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Proje Nasıl Oluşturulur – Aspose.Tasks ile Yeni Görev Özelliklerini Ayarlama
url: /tr/java/project-file-operations/set-attributes-new-tasks/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Proje Oluşturma – Yeni Görev Özelliklerini Ayarlama

## Giriş
Bu kapsamlı rehberde **proje dosyalarını nasıl oluşturacağınızı** ve Aspose.Tasks Java kütüphanesini kullanarak yeni görevler için Microsoft Project özelliklerini nasıl ayarlayacağınızı keşfedeceksiniz. Geliştirme ortamınızı hazırlamaktan projeyi XML dosyası olarak kaydetmeye kadar her adımı adım adım gösterecek, böylece **görev özelliklerini özelleştirebilir** ve proje yönetimi iş akışınızı kolaylaştırabilirsiniz.

## Hızlı Yanıtlar
- **Bu öğreticide ne anlatılıyor?** Yeni görevler için varsayılan başlangıç tarihlerini ayarlama ve projeyi XML olarak kaydetme.  
- **Hangi kütüphane gerekiyor?** Aspose.Tasks for Java.  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim ortamı için ticari lisans gerekir.  
- **Diğer görev varsayılanlarını değiştirebilir miyim?** Evet, Aspose.Tasks birçok görev‑seviyesi varsayılanını değiştirmenize izin verir.  
- **Hangi çıktı formatı kullanılıyor?** XML (SaveFileFormat.Xml).

## Aspose.Tasks'te Proje Nedir?
*Proje*, bir Microsoft Project dosyasını yansıtan bir nesne modelidir. Görevler, kaynaklar, takvimler ve diğer zamanlama verilerini depolar; böylece proje dosyalarını programlı olarak okuyabilir, değiştirebilir ve oluşturabilirsiniz.

## Görev Varsayılanlarını Neden Ayarlamalıyız?
Yeni görevler için başlangıç tarihi gibi varsayılan değerleri ayarlamak, planın tamamında tutarlılık sağlar. Her görevi manuel olarak güncellemek zorunda kalmaz ve zamanlama hataları riskini azaltır.

## Ön Koşullar
1. **Java Geliştirme Ortamı** – Java 8 veya üzeri yüklü olmalı.  
2. **Aspose.Tasks for Java** – [indirme bağlantısından](https://releases.aspose.com/tasks/java/) indirin.  
3. **IDE** – Eclipse, IntelliJ IDEA veya herhangi bir Java‑uyumlu editör.

## Paketleri İçe Aktarma
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.TaskStartDateType;
```

## Aspose.Tasks ile Proje Oluşturma – Yeni Görev Özelliklerini Ayarlama
### Adım 1: Veri Dizinini Tanımlama
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` ifadesini çıktının kaydedileceği mutlak yol ile değiştirin.

### Adım 2: Bir Project Örneği Oluşturma
```java
Project prj = new Project();
```
Bu, özelleştirmeye hazır boş bir proje oluşturur.

### Adım 3: Yeni Görev Özelliğini Ayarlama
```java
prj.set(Prj.NEW_TASK_START_DATE, TaskStartDateType.CurrentDate);
```
Yukarıdaki satır, Aspose.Tasks'e daha sonra ekleyeceğiniz herhangi bir görev için **geçerli tarihi** başlangıç tarihi olarak atamasını söyler.

### Adım 4: Projeyi Kaydetme
```java
prj.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
Burada **projeyi XML olarak kaydediyoruz**, bu format değişim ve sonraki işlemler için yaygın olarak desteklenir.

### Adım 5: Sonucu Görüntüleme
```java
System.out.println("Project file generated Successfully");
```
Basit bir konsol mesajı, dosyanın hatasız bir şekilde oluşturulduğunu onaylar.

## Görev Özelliklerini Nasıl Ayarlarım
Başlangıç tarihinin yanı sıra, `Prj` enum'ı kullanarak süre, takvim ve öncelik gibi diğer varsayılan görev ayarlarını da değiştirebilirsiniz. Bu esneklik, **görev özelliklerini** kuruluşunuzun standartlarına göre özelleştirmenizi sağlar.

## Projeyi XML Olarak Nasıl Kaydederim
XML olarak kaydetmek, tam proje yapısını korurken dosyanın insan tarafından okunabilir olmasını sağlar. Diğer araçlarla entegrasyon, sürüm kontrolü veya otomatik pipeline'lar için idealdir.

## Yaygın Sorunlar ve Çözümleri
- **Geçersiz veri dizini yolu** – Klasörün var olduğundan ve uygulamanın yazma iznine sahip olduğundan emin olun.  
- **Lisans bulunamadı** – `Project` nesnesini oluşturmadan önce Aspose.Tasks lisansınızı yükleyin; aksi takdirde değerlendirme filigranı görürsünüz.  
- **Beklenmeyen başlangıç tarihleri** – `Prj.NEW_TASK_START_DATE` ayarını yaptıktan sonra başka bir kodun bu değeri geçersiz kılmadığını kontrol edin.

## SSS
### S: Aspose.Tasks for Java ile mevcut proje dosyalarını manipüle edebilir miyim?
C: Evet, Aspose.Tasks for Java mevcut proje dosyalarını okuma, değiştirme ve çeşitli formatlarda kaydetme gibi kapsamlı işlevler sunar.  
### S: Aspose.Tasks for Java için daha fazla belge ve kaynak nerede bulunur?
C: [Aspose.Tasks for Java dokümantasyon sayfasında](https://reference.aspose.com/tasks/java/) belgeleri ve kaynakları inceleyebilirsiniz.  
### S: Aspose.Tasks for Java için ücretsiz deneme mevcut mu?
C: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.  
### S: Aspose.Tasks for Java için geçici lisanslar nasıl alınır?
C: Geçici lisansları [geçici lisans sayfasından](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.  
### S: Aspose.Tasks for Java ile ilgili sorunlar veya sorular için destek nereden alınır?
C: [Aspose.Tasks for Java destek forumunda](https://forum.aspose.com/c/tasks/15) toplulukla etkileşime geçebilir ve destek alabilirsiniz.

**Ek Soru‑Cevap**

**S: Projeyi oluşturduktan sonra varsayılan başlangıç tarihini değiştirebilir miyim?**  
C: Evet, yeni görev eklemeden önce istediğiniz zaman `prj.set(Prj.NEW_TASK_START_DATE, ...)` çağrısı yapabilirsiniz.  

**S: XML olarak kaydetmek büyük projelerde performansı etkiler mi?**  
C: XML metin tabanlıdır, bu yüzden dosya boyutu ikili formatlardan daha büyük olabilir, ancak çoğu tipik proje boyutu için hâlâ hızlıdır.  

**S: Global olarak ayarlayabileceğim başka görev varsayılanları var mı?**  
C: Kesinlikle – `NEW_TASK_DURATION`, `NEW_TASK_COST` ve `NEW_TASK_PRIORITY` gibi özellikler de `Prj` enum'ı aracılığıyla yapılandırılabilir.

## Sonuç
Artık **proje dosyalarını nasıl oluşturacağınızı**, yeni görevler için varsayılan başlangıç tarihlerini nasıl ayarlayacağınızı ve Aspose.Tasks for Java kullanarak **projeyi XML olarak nasıl kaydedeceğinizi** öğrendiniz. Bu adımları ustalıkla uygulayarak **görev özelliklerini** herhangi bir proje‑yönetim senaryosuna uyacak şekilde özelleştirebilir, tutarlılığı artırabilir ve değerli zaman tasarrufu sağlayabilirsiniz.

---

**Son Güncelleme:** 2025-12-21  
**Test Edilen Sürüm:** Aspose.Tasks for Java 24.12 (yazım anındaki en yeni sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}