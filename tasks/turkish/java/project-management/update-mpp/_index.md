---
date: 2025-12-28
description: Java için Aspose.Tasks, bir Java proje yönetimi kütüphanesini kullanarak
  görev eklemeyi ve MPP dosyalarını güncellemeyi öğrenin. MPP'de görev oluşturmak
  ve projeyi MPP olarak kaydetmek için adım adım rehberimizi izleyin.
linktitle: How to Add Task and Update MPP File in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Görev Ekleme ve MPP Dosyasını Güncelleme
url: /tr/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Görev Ekleme ve MPP Dosyasını Güncelleme

## Giriiş
Bu öğreticide **görev ekleme** ve Aspose.Tasks for Java kullanarak bir MPP dosyasının güncelleme sürecini görüntülersiniz; bu, önde gelen **java proje yönetimi kütüphanesidir**. Özel bir zamanlayıcı oluşturulması ya da mevcut proje planlarını programlı olarak değiştirilmesi istenmelidir, bu rehberde değişiklik yapılması yeni bir MPP belgesi olarak kaydedilmesine kadar tüm adımların boyutu anlatılır.

## Hızlı Yanıtlar
- **Bu bağlamda “nasıl görev eklenir” ne anlaşılıyor?**Mevcut bir Microsoft Project (MPP) dosyası içinde programlı olarak yeni bir görev oluşturmayı ifade eder.
- **İşlemi hangi kütüphaneyi gerçekleştiriyor?**Aspose.Tasks for Java, sağlam bir java proje yönetimidir.
- **Lisans gerekir mi?**Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim ortamı için ticari lisans gereklidir.
- **Sonucu MPP olarak kaydedebilir miyim?**Evet—`project.save(..., SaveFileFormat.Mpp)` kullanarak **projeyi mpp olarak kaydetme**.
- **Hangi Java sürümü gerekiyor mu?**Java8 veya üzeri.

## MPP dosyasına "görev nasıl eklenir" nedir?
Görev değiştirme, proje ilerlemesine yeni bir iş öğesi seçme, başlangıç/bitiş tarihlerini büyütme ve değiştirme MPP dosyasına yazmak geri anlamına gelir. Aspose.Tasks, düşük seviyeli dosya formatı detaylarını soyutlayarak iş mantığınıza odaklanmanızı sağlar.

## Aspose.Tasks for Java'yı neden kullanmalısınız?
- **Microsoft Project 2007‑2021 dosyalarıyla tam uyumluluk**.
- **COM veya Office kurulumuna gerek yoktur**—tamamen Java API'si.
- **Zengin özellik seti**: görev bağlama, kaynak dağıtımı, özel alanlar ve daha fazlası.
- **Büyük proje dosyaları için yüksek performans**, sunucu‑tarafı otomasyonları için idealdir.

## Önkoşullar
1. **Java Geliştirme Ortamı** – JDK8+ yüklü ve çalışıyor.
2. **Aspose.Tasks for Java** – [indirme sayfasının](https://releases.aspose.com/tasks/java/) indirilir.
3. **Temel Java bilgisi** – Sınıflar, nesneler ve tarih işleme konularına hakim olun.

## Paketleri İçe Aktar
Öncelikle ihtiyacınız olacak sınıfları içe aktarın. Bu, proje düzenlemeye, görev özelliklerine ve tarih işlemeye erişmenizi sağlar.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Adım 1: Veri Dizini Tanımlama
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` ifadesini, kaynak MPP dosyanızın bulunduğu mutlak yol ile değiştirin.

## Adım 2: Mevcut Projeyi Okuma
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
`Project` yapıcısı **SampleMSP2010.mpp** dosyasını yükler ve üzerinde çalışabileceğiniz bir nesne modeli sunar.

## Adım 3: Yeni Bir Görev Oluşturma (görev nasıl eklenir)
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Bu satır, kök göreve *Task1* adlı bir alt görev ekleyerek **görevi mpp içinde oluşturur**.

## Adım 4: Başlangıç ​​ve Bitiş Tarihlerini Belirleme
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Burada yeni eklenen görevin takvimini tanımlıyoruz. Tarihleri proje zaman çizelgenize uygun şekilde ayarlayın.

## Adım 5: Projeyi Kaydetme (projeyi mpp olarak kaydetme)
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
Güncellenen proje, yeni görevle birlikte **AfterLinking.mpp** olarak kalıcı hale getirilir.

## Yaygın Sorunlar ve Çözümler
| Sayı | Çözüm |
|----------|----------|
| **Dosya bulunamadı** | `dataDir` sonunun bir yol ayırıcısının (`/` veya `\\`) görünmesini ve dosya adının doğru olduğunu doğrulayın. |
| **Yanlış tarihler** | `Takvim` aylarının sıfır‑tabanlı olduğunu unutmayın; Temmuz için `Takvim.JULY` geçerlidir. |
| **Lisans istisnası** | Değerlendirme su işaretlerini önlemek için herhangi bir API programından önce geçerli bir Aspose.Tasks lisansını yükleyin. |

## Sıkça Sorulan Sorular
**S: Birden fazla görev aynı anda nasıl eklerim?**
A: Görev adları koleksiyonunu döngüye alıp “görev oluştur” aralığını döngü içinde sürekli olarak.

**S: Yeni görev için özel alanları ayarlayabilir miyim?**
A: Evet—`task.set(Tsk.CUSTOM_FIELD_x, value)` kullanın; *x* alan indeksidir.

**S: Mevcut bir programın düzeni olarak kopyalamak mümkün mü?**
A: Kaynak görevi (`Task cloned = sourceTask.clone();`) klonlayın ve ardından istediğiniz ebeveyne ekleyin.

**S: Yeni bir görev seçme yerine mevcut bir görevi güncellemem gerekiyorsa ne yapmalıyım?**
A: Görevi ID ile alın (`Görev mevcut = project.getRootTask().getChildren().getById(id);`) ve özellikleri verilir.

**S: Aspose.Tasks PDF veya PNG gibi diğer formatlarda saklamayı mı sakladınız?**
A: Evet—`project.save("output.pdf", SaveFileFormat.Pdf);` veya görsel temsiller için `SaveFileFormat.Png` kullanın.

---

**Son Güncelleme:** 2025-12-28
**Test Edildiği Sürüm:** Aspose.Tasks for Java 24.12
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}