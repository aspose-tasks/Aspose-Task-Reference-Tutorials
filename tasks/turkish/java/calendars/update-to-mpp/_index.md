---
date: 2025-12-03
description: Aspose.Tasks for Java kullanarak takvim MS Project oluşturmayı, projeyi
  MPP'ye dönüştürmeyi ve projeyi MPP olarak zahmetsizce kaydetmeyi öğrenin.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks ile Takvim Oluşturun ve MS Project'i MPP Olarak Kaydedin
url: /tr/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Takvim MS Project Oluşturma ve MPP Olarak Kaydetme

## Giriş

Modern proje yönetiminde **takvim MS Project** dosyaları oluşturup ardından yerel MPP formatında paylaşmanız sıkça gerekir. Birden fazla kaynaktan takvimleri birleştiriyor ya da eski verileri taşıyorsanız, takvimi programatik olarak oluşturabilmek zaman kazandırır ve manuel hataları ortadan kaldırır. Bu öğretici, MS Project içinde bir takvim oluşturma, özelleştirme ve son olarak **projeyi MPP’ye dönüştürme** sürecini Aspose.Tasks Java API’si ile adım adım gösterir.

## Hızlı Yanıtlar
- **Bu öğreticide ne anlatılıyor?** MS Project’te bir takvim oluşturup Aspose.Tasks for Java ile MPP dosyası olarak kaydetmek.  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim ortamı için ticari lisans gerekir.  
- **Hangi Java sürümü gerekiyor?** Java 8 ve üzeri (JDK 8+).  
- **Takvimi özelleştirebilir miyim?** Evet – çalışma saatleri, istisnalar ve tatiller ekleyebilirsiniz.  
- **Uygulama ne kadar sürer?** Temel bir takvim için yaklaşık 10‑15 dakika.

## “create calendar MS Project” nedir?

Takvim MS Project oluşturmak, Microsoft Project dosyası içinde görev zamanlamasını yöneten çalışma günlerini, saatlerini ve istisnalarını programatik olarak tanımlamak anlamına gelir. Aspose.Tasks kullanarak bu takvimleri Microsoft Project UI’sini açmadan oluşturabilir, değiştirebilir ve kalıcı hâle getirebilirsiniz.

## Neden Aspose.Tasks bu görev için tercih edilmeli?

- **Tam .NET/Java uyumluluğu** – Java’yı destekleyen herhangi bir platformda çalışır.  
- **COM veya Office kurulumu gerekmez** – sunucu‑tarafı otomasyon için idealdir.  
- **Zengin API** – özel çalışma haftaları ve tatiller dahil tüm takvim özelliklerini destekler.  
- **Doğrudan MPP çıktısı** – ara dönüşüm olmadan **projeyi MPP olarak kaydedebilirsiniz**.

## Ön Koşullar

1. **Java Development Kit (JDK) 8+** – `java -version` komutunun 1.8 veya daha yeni bir sürüm gösterdiğinden emin olun.  
2. **Aspose.Tasks for Java** – en yeni JAR dosyasını [Aspose web sitesinden](https://releases.aspose.com/tasks/java/) indirin.  
3. **IDE** – IntelliJ IDEA, Eclipse veya tercih ettiğiniz herhangi bir editör.  
4. **Temel Java bilgisi** – sınıflar, metodlar ve dosya I/O konularına aşina olun.

## Adım‑Adım Kılavuz

### Adım 1: Gerekli Paketleri İçe Aktarın

İlk olarak, Aspose.Tasks sınıflarını ve Java yardımcı sınıflarını projenize dahil edin.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Adım 2: Veri Dizinini Ayarlayın

Girdi şablonunuzun ve çıktı dosyalarınızın bulunacağı yeri tanımlayın. Yer tutucuyu makinenizdeki gerçek yol ile değiştirin.

```java
String dataDir = "Your Data Directory";
```

### Adım 3: Girdi ve Çıktı Dosya Adlarını Belirleyin

Mevcut bir MPP dosyasını (veya boş bir projeyi) yükleyecek ve sonucu yeni bir dosyaya yazacağız.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Adım 4: Projeyi Yükleyin ve Yeni Bir Takvim Ekleyin

Kaynak dosyadan bir `Project` örneği oluşturun ve **“Calendar 1”** adında bir takvim ekleyin.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Adım 5: Takvimi Özelleştirin (İsteğe Bağlı)

Belirli çalışma saatleri, tatiller veya istisnalar eklemeniz gerekiyorsa kendi yardımcı metodunuzu çağırın. Örnekte `GetTestCalendar` bir yer tutucu olarak kullanılmıştır.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **İpucu:** `cal1.getWeekDays()` üzerinden doğrudan çalışılan saatleri haftanın her günü için ayarlayabilirsiniz.

### Adım 6: Takvimi Projeye Atayın

Projeye, tüm zamanlama hesaplamaları için yeni oluşturulan takvimi kullanmasını söyleyin.

```java
project.set(Prj.CALENDAR, cal1);
```

### Adım 7: Projeyi MPP Olarak Kaydedin

Şimdi **projeyi MPP’ye dönüştürün** ve `SaveFileFormat.Mpp` seçeneğiyle kaydedin.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Adım 8: Başarılı Tamamlamayı Doğrulayın

Basit bir konsol mesajı, işlemin hatasız tamamlandığını size bildirir.

```java
System.out.println("Process completed Successfully");
```

## Yaygın Kullanım Senaryoları

- **Tekrarlayan projeler için otomatik takvim oluşturma** (ör. haftalık sprintler).  
- **Eski CSV veya Excel takvimlerini tam özellikli bir MS Project dosyasına taşıma**.  
- **Sunucu‑tarafı raporlama**; bir web servisi isteğe bağlı MPP dosyası döndürür.  

## Sorun Giderme ve Yaygın Tuzaklar

| Sorun | Nedeni | Çözüm |
|-------|--------|------|
| `project.save` sırasında `NullPointerException` | `dataDir` mevcut olmayan bir klasöre işaret ediyor | Klasörün var olduğundan emin olun veya program içinde oluşturun. |
| Takvim görevlerde uygulanmıyor | Görevler hâlâ varsayılan takvime referans veriyor | `Prj.CALENDAR` ayarlandıktan sonra, daha önce geçersiz kılınmışsa her görevin `Task.CALENDAR` değerini de güncelleyin. |
| Çıktı dosyası 0 KB | Yazma izinleri eksik | JVM’i uygun dosya sistemi izinleriyle çalıştırın veya yazılabilir bir yol seçin. |

## Sıkça Sorulan Sorular

**S: Aspose.Tasks for Java farklı MS Project sürümleriyle uyumlu mu?**  
C: Evet, Aspose.Tasks for Java Project 2007’den en yeni sürüme kadar geniş bir MS Project sürüm yelpazesini destekler, sorunsuz uyumluluk sağlar.

**S: Takvimleri proje gereksinimlerine göre özelleştirebilir miyim?**  
C: Kesinlikle. Çalışma günlerini tanımlayabilir, özel çalışma haftaları oluşturabilir, tatiller ekleyebilir ve tek bir proje dosyasında birden fazla takvim yaratabilirsiniz.

**S: Aspose.Tasks for Java destek ve yardım sağlıyor mu?**  
C: Evet, Aspose.Tasks topluluk forumundan [burada](https://forum.aspose.com/c/tasks/15) yardım alabilirsiniz.

**S: Aspose.Tasks for Java için ücretsiz deneme mevcut mu?**  
C: Evet, tamamen işlevsel bir ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) edinebilirsiniz.

**S: Aspose.Tasks for Java için geçici bir lisans nasıl alınır?**  
C: Geçici lisanslar Aspose web sitesinden [burada](https://purchase.aspose.com/temporary-license/) talep edilebilir.

---

**Son Güncelleme:** 2025-12-03  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}