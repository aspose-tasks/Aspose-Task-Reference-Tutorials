---
date: 2026-05-15
description: Aspose.Tasks for Java kullanarak proje başlangıç tarihini nasıl ayarlayacağınızı,
  proje bilgilerini nasıl yazacağınızı ve projeyi XML olarak nasıl kaydedeceğinizi
  öğrenin.
keywords:
- set project start date
- save project as xml
- Aspose.Tasks Java
linktitle: Aspose.Tasks ile Proje Bilgilerini Yazma
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to set project start date, write project information, and
    save project as XML using Aspose.Tasks for Java.
  headline: Set Project Start Date in MS Project using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to set project start date, write project information, and
    save project as XML using Aspose.Tasks for Java.
  name: Set Project Start Date in MS Project using Aspose.Tasks for Java
  steps:
  - name: '**Java Development Kit (JDK)** – any recent version (8+ recommended).'
    text: '**Java Development Kit (JDK)** – any recent version (8+ recommended).'
  - name: '**Aspose.Tasks for Java library** – download it from [here](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java library** – download it from [here](https://releases.aspose.com/tasks/java/).'
  - name: '**An IDE** – IntelliJ IDEA, Eclipse, or your favorite Java editor.'
    text: '**An IDE** – IntelliJ IDEA, Eclipse, or your favorite Java editor.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java provides robust functionalities for both reading
      and writing MS Project files.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, Aspose.Tasks for Java supports various MS Project versions,
      ensuring seamless handling of MPP, XML, and Primavera formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial version allows full feature exploration but inserts a watermark
      on generated files and limits the number of project entities you can create.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: MS Project'te Proje Başlangıç Tarihini Aspose.Tasks for Java ile Ayarlama
url: /tr/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project'te Proje Başlangıç Tarihini Aspose.Tasks for Java ile Ayarlama

## Giriş
Bu öğreticide, **proje başlangıç tarihini** ayarlamayı ve Aspose.Tasks for Java ile ek MS Project bilgileri yazmayı öğreneceksiniz. Proje takvimlerini otomatikleştiriyor, raporlar oluşturuyor ya da Project verilerini daha büyük bir sisteme entegre ediyor olsanız, başlangıç tarihini programlı olarak kontrol etmek zaman çizelgeleriniz üzerinde kesin bir kontrol sağlar. Ortamı kurmaktan güncellenmiş projeyi XML dosyası olarak kaydetmeye kadar her adımı adım adım göstereceğiz; böylece bu teknikleri hemen uygulamaya başlayabilirsiniz.

## Hızlı Yanıtlar
- **Bir projeyi manipüle etmek için birincil sınıf nedir?** `Project` Aspose.Tasks kütüphanesinden.  
  `Project` sınıfı, bellekte bir MS Project dosyasını temsil eder.  
- **Proje başlangıç tarihini nasıl ayarlarım?** `project.set(Prj.START_DATE, <date>)` kullanın.  
  `Prj.START_DATE`, projenin başlangıç tarihini ayarlamak için kullanılan özellik anahtarıdır.  
- **Durum tarihini de ayarlayabilir miyim?** Evet, `project.set(Prj.STATUS_DATE, <date>)` ile.  
  `Prj.STATUS_DATE`, projenin mevcut durumunu yansıtan tarihi belirtir.  
- **Projeyi dışa aktarmak için hangi formatı kullanmalıyım?** `SaveFileFormat.Xml` ile XML olarak kaydedin.  
  `SaveFileFormat.Xml`, projenin XML formatında kaydedileceğini gösterir.  
- **Üretim ortamında lisansa ihtiyacım var mı?** Tam işlevsellik için geçerli bir Aspose.Tasks lisansı gereklidir.  
- **Aspose.Tasks hangi ortamları destekliyor?** Windows, Linux ve macOS, Java 8+ ile.

## Proje başlangıç tarihi nedir?
Proje başlangıç tarihini ayarlamak, takvimin başladığı takvim gününü belirler ve tüm görev hesaplamaları, bağımlılıklar ve kritik yol analizleri için temel oluşturur. Bu tarihi programlı olarak tanımlayarak, oluşturulan her proje dosyasının aynı noktadan başlamasını sağlarsınız; manuel giriş hatalarını ortadan kaldırır ve derlemeler arasında tekrarlanabilir sonuçlar elde edilmesini garantiler.

## Projeye ait bilgileri yazmak için Aspose.Tasks for Java neden kullanılmalı?
Aspose.Tasks for Java, **150'den fazla yapılandırılabilir proje özelliği** sunar ve **30'dan fazla dosya formatını** destekler; böylece Microsoft Project yüklü olmadan MS Project verilerini okuyabilir, değiştirebilir ve yazabilirsiniz. Kütüphane Windows, Linux ve macOS'ta çalışır, çok sayfalı dosyaları bellek‑verimli modda işler ve CI/CD boru hatlarına, toplu‑işlem hizmetlerine veya bulut‑tabanlı arka uçlara entegre edilebilir. Bu ölçülebilir yetenekler, kurumsal ölçekli otomasyon için en güvenilir seçeneği oluşturur.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. **Java Development Kit (JDK)** – herhangi bir yeni sürüm (8+ önerilir).  
2. **Aspose.Tasks for Java kütüphanesi** – bunu [buradan](https://releases.aspose.com/tasks/java/) indirin.  
3. **Bir IDE** – IntelliJ IDEA, Eclipse veya favori Java editörünüz.  

## Paketleri İçe Aktar
İlk olarak, Java projenizde gerekli paketleri içe aktarın:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Adım 1: Veri Dizinini Ayarla
Proje verilerinizin saklanacağı dizini tanımlayın.
```java
String dataDir = "Your Data Directory";
```

## Adım 2: Proje Örneği Oluştur
`Project` sınıfı, Aspose.Tasks'in üst‑seviye nesnesi olup bellekte tek bir MS Project dosyasını temsil eder. Başlatılması, hemen doldurmaya başlayabileceğiniz boş bir takvim oluşturur.
```java
Project project = new Project();
```

## Adım 3: Proje Bilgi Özelliklerini Ayarla
Burada **proje başlangıç tarihini**, başlangıç‑tarihi‑bazlı takvim bayrağını ve durum tarihini ayarlarız—*projeye ait bilgi yazma* ve *durumu nasıl ayarlarım* anahtar kelimelerini kapsar.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## Adım 4: Projeyi XML Olarak Kaydet
Son olarak, güncellenmiş proje dosyasını kalıcı hale getirin. XML olarak kaydetmek, sonraki araçlarla maksimum uyumluluğu sağlar ve dosya boyutunu küçük tutar.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Yaygın Sorunlar ve Çözümler
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **Yanlış başlangıç tarihi** | Takvim ayı Java'da sıfır‑tabanlıdır. | Gösterildiği gibi `Calendar.JULY` (veya ay indeksine 1 ekleyin) kullanın. |
| **Dosya kaydedilmedi** | `dataDir` mevcut değil veya yazma izni yok. | Dizini önceden oluşturun veya yazılabilir bir yol seçin. |
| **Lisans uyarısı** | Lisans olmadan çalıştırmak bir filigran ekler. | `Project` nesnesini oluşturmadan önce geçerli bir Aspose.Tasks lisansı uygulayın. |

## Sıkça Sorulan Sorular

**S: Aspose.Tasks for Java ile MS Project dosyalarını okuyabilir miyim?**  
C: Evet, Aspose.Tasks for Java, MS Project dosyalarını okuma ve yazma için güçlü işlevler sunar.

**S: Aspose.Tasks for Java farklı MS Project sürümleriyle uyumlu mu?**  
C: Kesinlikle, Aspose.Tasks for Java çeşitli MS Project sürümlerini destekler ve MPP, XML ve Primavera formatlarını sorunsuz bir şekilde işleyebilir.

**S: Aspose.Tasks for Java deneme sürümünde herhangi bir sınırlama var mı?**  
C: Deneme sürümü tam özellik keşfine izin verir ancak oluşturulan dosyalara filigran ekler ve oluşturabileceğiniz proje varlıklarının sayısını sınırlar.

**S: Aspose.Tasks for Java için destek nasıl alabilirim?**  
C: Aspose.Tasks topluluk forumundan [burada](https://forum.aspose.com/c/tasks/15) yardım isteyebilirsiniz.

**S: Aspose.Tasks for Java için geçici bir lisans satın alabilir miyim?**  
C: Evet, kısa vadeli kullanım için geçici lisanslar mevcuttur. Birini [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

## Sonuç
Artık Aspose.Tasks for Java kullanarak **proje başlangıç tarihini** ayarlamayı, temel proje bilgilerini yazmayı ve **projeyi XML olarak kaydetmeyi** öğrendiniz. Bu yapı taşları, proje yönetimi iş akışlarını otomatikleştirmenizi, tutarlı takvimler oluşturmanızı ve MS Project verilerini Java uygulamalarınıza entegre etmenizi sağlar. Sonraki adımda, otomatik takvimlerinizi daha da zenginleştirmek için görevleri, kaynakları ve özel alanları nasıl ekleyeceğinizi keşfedin.

---

**Son Güncelleme:** 2026-05-15  
**Test Edilen:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose

## İlgili Eğitimler

- [Aspose.Tasks for Java ile Proje Takvimini Nasıl Ayarlarsınız](/tasks/java/calendars/properties/)
- [Aspose.Tasks for Java ile Microsoft Project'ten Proje Bilgilerini Nasıl Okursunuz](/tasks/java/project-properties/read-project-info/)
- [MPP Dosyasını Java'da Yükle - Aspose.Tasks ile Proje Özelliklerini Yönet](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}