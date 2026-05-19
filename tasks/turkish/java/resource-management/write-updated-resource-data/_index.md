---
date: 2026-01-15
description: Aspose.Tasks for Java kullanarak projeye kaynak eklemeyi, kaynak verilerini
  güncellemeyi ve projeyi MPP olarak kaydetmeyi öğrenin.
linktitle: Add Resource to Project Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java Kullanarak Projeye Kaynak Ekle
url: /tr/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java Kullanarak Projeye Kaynak Ekleme

## Giriş
Bu uygulamalı öğreticide, Aspose.Tasks Java API'sı ile **projeye kaynak ekleme** dosyalarını programlı olarak keşfedeceksiniz. Mevcut bir MS Project XML dosyasını yükleme, yeni bir kaynak ekleme, özelliklerini güncelleme ve sonunda **projeyi MPP olarak kaydetme** adımlarını göstereceğiz. Sonunda, herhangi bir Java tabanlı raporlama veya otomasyon aracına ekleyebileceğiniz net, tekrarlanabilir bir desen elde edeceksiniz.

## Hızlı Yanıtlar
- **“projeye kaynak ekleme” ne anlama gelir?** Microsoft Project dosyası içinde yeni bir kaynak girişi (kişi, ekipman, malzeme) oluşturur.  
- **Bu işlemi hangi kütüphane yönetir?** Aspose.Tasks for Java – Microsoft Project'in yüklü olmasına gerek yok.  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme sürümü çalışır; üretim için ticari lisans gereklidir.  
- **XML'i MPP'ye dönüştürebilir miyim?** Evet – XML dosyasını yükleyin ve `project.save(...)` kullanarak **projeyi MPP olarak kaydedin**.  
- **Hangi Java sürümü gerekiyor?** Java 6 veya üzeri (Java 8+ önerilir).

## “Projeye kaynak ekleme” nedir?
Bir projeye kaynak eklemek, MS Project dosyasının Resources (Kaynaklar) tablosuna yeni bir satır eklemek anlamına gelir. Bu satır, ad, maliyet oranları, grup ve görevlerin daha sonra başvurabileceği özel alanlar gibi ayrıntıları saklar.

## Neden Aspose.Tasks for Java Kullanmalı?
- **Microsoft Project bağımlılığı yok** – herhangi bir işletim sistemi veya CI sunucusunda çalışır.  
- **Tam doğruluk** – formatlar arasında dönüşüm yaparken tüm yerel Project özelliklerini korur.  
- **Zengin API** – görevleri, kaynakları, takvimleri ve daha fazlasını okumanıza, yazmanıza ve manipüle etmenize olanak tanır.

## Ön Koşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. Java Development Kit (JDK) 8 veya daha yeni bir sürüm yüklü.  
2. Aspose.Tasks for Java kütüphanesi – bunu [buradan](https://releases.aspose.com/tasks/java/) indirin.  
3. Java sözdizimi ve Maven/Gradle proje kurulumu hakkında temel bilgi.

## Paketleri İçe Aktarma
Gerekli Aspose.Tasks sınıflarını Java kaynak dosyanıza ekleyin:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Adım 1: Veri Dizinini Ayarlama
Kaynak XML ve oluşacak MPP dosyalarının nerede bulunacağını tanımlayın:

```java
String dataDir = "Your Data Directory";
```

## Adım 2: Giriş ve Çıkış Dosyalarını Belirtme
Dönüştürmek istediğiniz XML dosyasına (**XML'i MPP'ye dönüştür**) ve yeni kaynağı içerecek hedef MPP dosyasına işaret edin:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Adım 3: Projeyi Yükleme
XML kaynağından bir `Project` nesnesi oluşturun:

```java
Project project = new Project(file);
```

## Adım 4: Kaynak Ekleme ve Özellikleri Ayarlama
İşte **projeye kaynak ekleme** ve oranlarını ve grubunu yapılandırma kısmı:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

*Pro ipucu:* Tek bir çalıştırmada **birden fazla kaynağı güncellemek** için `add` çağrısını bir döngü içinde tekrarlayabilirsiniz.

## Adım 5: Projeyi Kaydetme
Son olarak, değişiklikleri kalıcı hale getirmek için **projeyi MPP olarak kaydedin**:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Sonuç
Aspose.Tasks for Java kullanarak **projeye nasıl kaynak ekleneceğini**, özelliklerinin nasıl güncelleneceğini ve **projeyi MPP olarak nasıl kaydedileceğini** yeni öğrendiniz. Bu yaklaşım, otomatik raporlama hatları, toplu kaynak ithalatları veya masaüstü uygulaması olmadan MS Project dosyalarını manipüle etmeniz gereken herhangi bir senaryo için idealdir.

## Sıkça Sorulan Sorular

**S1: Aspose.Tasks for Java kullanarak aynı projede birden fazla kaynağı güncelleyebilir miyim?**  
C: Evet, `project.getResources()` üzerinde döngü yapabilir veya `add` metodunu tekrarlayarak, her kaynağın alanlarını gerektiği gibi ayarlayabilirsiniz.

**S2: Aspose.Tasks, MS Project dışındaki diğer dosya formatlarını destekliyor mu?**  
C: Kesinlikle – XML, MPP, MPX, Primavera ve daha fazlası desteklenir.

**S3: Aspose.Tasks, farklı Java sürümleriyle uyumlu mu?**  
C: Kütüphane Java 6 ve üzeri sürümlerle çalışır; en iyi performans için Java 8+ şiddetle önerilir.

**S4: Aspose.Tasks ile MS Project dosyalarında başka işlemler yapabilir miyim?**  
C: Evet, görevleri, takvimleri, atamaları, özel alanları okuyabilir/yazabilir ve hatta raporlar oluşturabilirsiniz.

**S5: Aspose.Tasks için ek yardım veya destek nereden bulunur?**  
C: Topluluk yardımı ve resmi destek için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edin.

---

**Son Güncelleme:** 2026-01-15  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}