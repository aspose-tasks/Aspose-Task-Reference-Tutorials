---
date: 2026-02-05
description: Aspose.Tasks for Java kullanarak bir takvime tatilleri eklemeyi, takvimi
  bir projeye atamayı ve MS Project dosyasını MPP olarak kaydetmeyi öğrenin.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Tatilleri Takvime Ekle ve Aspose.Tasks ile MPP Olarak Kaydet
url: /tr/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Takvime Tatilleri Ekleyin ve Aspose.Tasks ile MPP Olarak Kaydedin

## Giriş

Modern proje yönetiminde **add holidays to calendar** dosyalarına sık sık ihtiyaç duyarsınız, bir **MS Project calendar** oluşturursunuz ve ardından takvimi yerel MPP formatında paylaşabilirsiniz. Birden fazla kaynaktan zaman çizelgelerini birleştiriyor ya da eski verileri taşıyorsanız, takvimi programlı olarak oluşturmak manuel hataları ortadan kaldırır ve teslim süresini hızlandırır. Bu öğretici, MS Project içinde bir takvim oluşturma, tatillerle özelleştirme, **assign calendar to project** ve sonunda Aspose.Tasks Java API kullanarak **convert project to MPP** işlemlerinin tamamını adım adım gösterir.

## Hızlı Yanıtlar
- **Bu öğretici neyi kapsıyor?** Tatilleri takvime ekleme, takvimi bir projeye atama ve sonucu Aspose.Tasks for Java ile MPP dosyası olarak kaydetme.  
- **Lisans gerekir mi?** Geliştirme için ücretsiz deneme yeterlidir; üretim için ticari lisans gereklidir.  
- **Hangi Java sürümü gerekli?** Java 8 ve üzeri (JDK 8+).  
- **Takvimi özelleştirebilir miyim?** Evet – çalışma saatleri, istisnalar ve tatiller ekleyebilirsiniz.  
- **Uygulama ne kadar sürer?** Temel bir takvim için yaklaşık 10‑15 dakika.  

## “create calendar MS Project” nedir?

“create calendar MS Project”, Microsoft Project dosyası içinde görev zamanlamasını yöneten çalışma günlerini, saatlerini ve istisnalarını programlı olarak tanımlamak anlamına gelir. Aspose.Tasks kullanarak **java create project calendar** oluşturabilir, değiştirebilir ve Microsoft Project UI'sını hiç açmadan değişiklikleri kalıcı hale getirebilirsiniz.

## Neden Aspose.Tasks bu görev için kullanılmalı?

- **Full .NET/Java compatibility** – Java destekleyen herhangi bir platformda çalışır.  
- **No COM or Office installation needed** – sunucu‑tarafı otomasyon ve **automate schedule generation** için idealdir.  
- **Rich API** – özel çalışma haftaları ve tatiller dahil olmak üzere her takvim özelliğini destekler.  
- **Direct MPP output** – ara dönüşümler olmadan **save project as MPP** yapabilirsiniz.

## Önkoşullar

1. **Java Development Kit (JDK) 8+** – `java -version` komutunun 1.8 veya daha yeni bir sürüm gösterdiğinden emin olun.  
2. **Aspose.Tasks for Java** – en yeni JAR dosyasını [Aspose website](https://releases.aspose.com/tasks/java/) adresinden indirin.  
3. **IDE** – IntelliJ IDEA, Eclipse veya tercih ettiğiniz herhangi bir editör.  
4. **Basic Java knowledge** – sınıflar, metodlar ve dosya I/O konularına aşina olun.

## Takvime Tatil Eklemek İçin

Aşağıda ortamı kurmaktan son MPP dosyasını kaydetmeye kadar her adımı anlatıyoruz. Kod blokları orijinal öğreticiden değiştirilmemiştir; açıklamalar netlik sağlamak amacıyla genişletilmiştir.

### Adım 1: Gerekli Paketleri İçe Aktarın

İlk olarak Aspose.Tasks sınıflarını ve Java yardımcılarını kapsam içine alın.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Adım 2: Veri Dizinini Ayarlayın

Giriş şablonunuzun ve çıkış dosyalarınızın bulunacağı yeri tanımlayın. Yer tutucuyu makinenizdeki gerçek yol ile değiştirin.

```java
String dataDir = "Your Data Directory";
```

### Adım 3: Giriş ve Çıkış Dosya Adlarını Tanımlayın

Mevcut bir MPP dosyasını (veya boş bir projeyi) yükleyecek ve sonucu yeni bir dosyaya yazacağız.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Adım 4: Projeyi Yükleyin ve Yeni Bir Takvim Ekleyin

Kaynak dosyadan bir `Project` örneği oluşturun ve **“Calendar 1”** adlı bir takvim ekleyin.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Adım 5: Takvimi Özelleştirin (İsteğe Bağlı)

Özel çalışma saatleri, tatiller veya istisnalar eklemeniz gerekiyorsa kendi yardımcı metodunuzu çağırın. Örnekte `GetTestCalendar` bir yer tutucu olarak kullanılmıştır.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** `cal1.getWeekDays()` metodunu doğrudan manipüle ederek haftanın her günü için çalışma saatlerini ayarlayabilir veya `cal1.getExceptions()` metodunu kullanarak **add holidays to calendar** yapabilirsiniz.

### Adım 6: Takvimi Projeye Ata

Projeye, tüm zamanlama hesaplamaları için yeni oluşturulan takvimi kullanmasını söyleyin.

```java
project.set(Prj.CALENDAR, cal1);
```

### Adım 7: Projeyi MPP Olarak Kaydedin

Şimdi **convert project to MPP** işlemini `SaveFileFormat.Mpp` seçeneğiyle kaydederek gerçekleştirin.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Adım 8: Başarılı Tamamlamayı Onaylayın

Basit bir konsol mesajı, işlemin hatasız tamamlandığını bildirir.

```java
System.out.println("Process completed Successfully");
```

## Yaygın Kullanım Senaryoları

- **Automated schedule generation** tekrarlayan projeler için (ör. haftalık sprintler).  
- **Migrating legacy CSV or Excel calendars** tam özellikli bir MS Project dosyasına dönüştürmek.  
- **Server‑side reporting** bir web servisin talep üzerine MPP dosyası döndürdüğü durumlar.  

## Sorun Giderme ve Yaygın Tuzaklar

| Sorun | Neden | Çözüm |
|-------|-------|-----|
| `project.save` sırasında `NullPointerException` | `dataDir` mevcut olmayan bir klasöre işaret ediyor | Dizinin var olduğundan emin olun veya programatik olarak oluşturun. |
| Takvim görevlerde uygulanmadı | Görevler hâlâ varsayılan takvime referans veriyor | `Prj.CALENDAR` ayarlandıktan sonra, görevlerin `Task.CALENDAR` değerleri daha önce geçersiz kılındıysa onları da güncelleyin. |
| Çıktı dosyası 0 KB | Yazma izinleri eksik | JVM'yi uygun dosya sistemi izinleriyle çalıştırın veya yazılabilir bir yol seçin. |

## Sıkça Sorulan Sorular

**S: Aspose.Tasks for Java farklı MS Project sürümleriyle uyumlu mu?**  
C: Evet, Aspose.Tasks for Java Project 2007'den en yeni sürüme kadar geniş bir MS Project sürüm yelpazesini destekler, sorunsuz uyumluluk sağlar.

**S: Takvimleri proje gereksinimlerine göre özelleştirebilir miyim?**  
C: Kesinlikle. Çalışma günlerini tanımlayabilir, özel çalışma haftaları ayarlayabilir, tatiller ekleyebilir ve tek bir proje dosyasında birden fazla takvim oluşturabilirsiniz.

**S: Aspose.Tasks for Java sorun giderme ve destek sağlıyor mu?**  
C: Evet, Aspose.Tasks topluluk forumundan [burada](https://forum.aspose.com/c/tasks/15) yardım alabilirsiniz.

**S: Aspose.Tasks for Java için ücretsiz deneme mevcut mu?**  
C: Evet, tamamen işlevsel bir ücretsiz deneme [burada](https://releases.aspose.com/) mevcuttur.

**S: Aspose.Tasks for Java için geçici bir lisans nasıl alınır?**  
C: Geçici lisanslar Aspose web sitesinden [burada](https://purchase.aspose.com/temporary-license/) talep edilebilir.

**Son Güncelleme:** 2026-02-05  
**Test Edilen Sürüm:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}