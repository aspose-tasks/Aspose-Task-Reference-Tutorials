---
date: 2025-12-31
description: Aspose.Tasks for Java kullanarak proje başlangıç tarihini nasıl ayarlayacağınızı,
  proje bilgilerini nasıl yazacağınızı ve projeyi XML olarak nasıl kaydedeceğinizi
  öğrenin.
linktitle: Write Project Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java kullanarak MS Project'te Proje Başlangıç Tarihini Ayarlama
url: /tr/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project'te Proje Başlangıç Tarihini Aspose.Tasks for Java ile Ayarlama

## Giriş
Bu öğreticide, **set project start date** nasıl yapılır ve Aspose.Tasks for Java ile ek MS Project bilgileri nasıl yazılır keşfedeceksiniz. Proje takvimlerini otomatikleştiriyor, raporlar oluşturuyor veya Proje verilerini daha büyük bir sisteme entegre ediyor olsanız da, başlangıç tarihini programlı olarak kontrol etmek zaman çizelgeleriniz üzerinde kesin bir kontrol sağlar. Ortamı kurmaktan güncellenmiş projeyi XML dosyası olarak kaydetmeye kadar her adımı adım adım göstereceğiz, böylece bu teknikleri hemen uygulamaya başlayabilirsiniz.

## Hızlı Yanıtlar
- **Bir projeyi manipüle etmek için birincil sınıf nedir?** `Project` Aspose.Tasks kütüphanesinden.  
- **Proje başlangıç tarihini nasıl ayarlarım?** `project.set(Prj.START_DATE, <date>)` kullanın.  
- **Durum tarihini de ayarlayabilir miyim?** Evet, `project.set(Prj.STATUS_DATE, <date>)` ile.  
- **Projeyi dışa aktarmak için hangi formatı kullanmalıyım?** `SaveFileFormat.Xml` ile XML olarak kaydedin.  
- **Üretim kullanımında lisansa ihtiyacım var mı?** Tam işlevsellik için geçerli bir Aspose.Tasks lisansı gereklidir.

## **set project start date** nedir?
Proje başlangıç tarihini ayarlamak, planlanan tüm görevlerin başladığı takvim gününü tanımlar. Bu tarih, görev süreleri, bağımlılıklar ve kritik yollar gibi hesaplamalar için referans noktasıdır. Tarihi programlı olarak ayarlayarak, birden fazla proje dosyası arasında tutarlılık sağlarsınız ve manuel giriş hatalarını ortadan kaldırırsınız.

## Proje bilgilerini yazmak için Aspose.Tasks for Java neden kullanılmalı?
- **Tam API kapsamı:** Microsoft Project yüklü olmadan her Project özelliğini okuyabilir, değiştirebilir ve yazabilirsiniz.  
- **Çapraz platform:** Windows, Linux ve macOS'ta çalışır.  
- **Otomasyona hazır:** Toplu işleme, CI pipeline'larına veya anlık proje takvimleri üreten arka uç hizmetlerine idealdir.  

## Ön Koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Java Development Kit (JDK)** – herhangi bir güncel sürüm (8+ önerilir).  
2. **Aspose.Tasks for Java kütüphanesi** – [buradan](https://releases.aspose.com/tasks/java/) indirin.  
3. **Bir IDE** – IntelliJ IDEA, Eclipse veya favori Java editörünüz.  

## Paketleri İçe Aktarma
İlk olarak, Java projenizde gerekli paketleri içe aktarın:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Adım 1: Veri Dizinini Ayarlama
Proje verilerinizin saklanacağı dizini tanımlayın.
```java
String dataDir = "Your Data Directory";
```

## Adım 2: Project Örneği Oluşturma
Yeni bir project örneği başlatın.
```java
Project project = new Project();
```

## Adım 3: Proje Bilgi Özelliklerini Ayarlama
Burada **project start date**'i, başlangıçtan takvimi ve durum tarihini ayarlıyoruz—birincil ve ikincil anahtar kelimeler olan *write project information* ve *how to set status*'i kapsayacak şekilde.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## Adım 4: Projeyi XML Olarak Kaydetme
Son olarak, güncellenmiş proje dosyasını kalıcı hale getiriyoruz. Bu, ikincil anahtar kelime **save project as xml**'i gösterir.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Yaygın Sorunlar ve Çözümler
| Issue | Reason | Fix |
|-------|--------|-----|
| **Yanlış başlangıç tarihi** | Java'da takvim ayı sıfır‑tabanlıdır. | Gösterildiği gibi `Calendar.JULY` (veya ay indeksine 1 ekleyerek) kullanın. |
| **Dosya kaydedilmedi** | `dataDir` mevcut değil veya yazma izni yok. | Dizini önceden oluşturun veya yazılabilir bir yol seçin. |
| **Lisans uyarısı** | Lisans olmadan çalıştırmak bir filigran ekler. | `Project` nesnesini oluşturmadan önce geçerli bir Aspose.Tasks lisansı uygulayın. |

## SSS
### Q: Aspose.Tasks for Java ile MS Project dosyalarını okuyabilir miyim?
A: Evet, Aspose.Tasks for Java MS Project dosyalarını okuma ve yazma için güçlü işlevsellik sağlar.  
### Q: Aspose.Tasks for Java farklı MS Project sürümleriyle uyumlu mu?
A: Kesinlikle, Aspose.Tasks for Java çeşitli MS Project sürümlerini destekler, farklı dosya formatları arasında uyumluluk sağlar.  
### Q: Aspose.Tasks for Java deneme sürümünde herhangi bir sınırlama var mı?
A: Deneme sürümü kütüphanenin yeteneklerini keşfetmenizi sağlar, ancak çıktı dosyalarına filigran eklenmesi gibi bazı sınırlamaları vardır.  
### Q: Aspose.Tasks for Java için destek nasıl alınır?
A: Aspose.Tasks topluluk forumundan [burada](https://forum.aspose.com/c/tasks/15) yardım alabilirsiniz.  
### Q: Aspose.Tasks for Java için geçici bir lisans satın alabilir miyim?
A: Evet, kısa vadeli kullanım için geçici lisanslar mevcuttur. [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.  

## Sonuç
Artık **set project start date**'i nasıl ayarlayacağınızı, temel proje bilgilerini nasıl yazacağınızı ve Aspose.Tasks for Java kullanarak **save project as XML**'i nasıl yapacağınızı öğrendiniz. Bu temel bileşenler, proje yönetimi iş akışlarını otomatikleştirmenizi, tutarlı takvimler oluşturmanızı ve MS Project verilerini Java uygulamalarınıza entegre etmenizi sağlar.

---

**Son Güncelleme:** 2025-12-31  
**Test Edilen Sürüm:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}