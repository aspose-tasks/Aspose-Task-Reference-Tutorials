---
date: 2026-03-29
description: Aspose.Tasks for Java kullanarak bir MPP projesinde anahtar kelimeleri
  ve oluşturma tarihini nasıl ayarlayacağınızı öğrenin. Kod örnekleriyle adım adım
  kılavuz.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks ile MPP Proje Özeti'nde Anahtar Kelimeleri Nasıl Ayarlarsınız
url: /tr/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile MPP Proje Özeti'nde Anahtar Kelimeleri Ayarlama

## Giriş
Bu öğreticide, Aspose.Tasks for Java kullanarak bir MPP proje dosyası için **anahtar kelimeleri ayarlamayı** ve diğer özet bilgileri keşfedeceksiniz. Yazar detayları, revizyon numaraları veya özel bir oluşturulma tarihi eklemeniz gerekse, bu kılavuz tam adımları, çalıştırmaya hazır kodla birlikte size gösterir. Sonunda anahtar kelimeleri ayarlayabilecek, java ile oluşturulma tarihini ayarlayabilecek ve dosyadan verileri geri okuyabileceksiniz.

## Hızlı Yanıtlar
- **Hangi kütüphane kullanılıyor?** Aspose.Tasks for Java  
- **Ana amaç?** MPP dosyasında anahtar kelimeleri, yazar bilgilerini ve oluşturulma tarihini ayarlama  
- **Kaç kod adımı var?** Üç basit kod bloğu (başlatma, kaydetme, okuma)  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir  
- **Desteklenen Java sürümü?** Java 8 ve üzeri  

## “Anahtar kelimeleri nasıl ayarlarsınız” MPP dosyasında nedir?
Anahtar kelimeler, bir Microsoft Project (MPP) dosyası içinde depolanan meta veri alanlarıdır. Projeleri sınıflandırmaya, hızlı aramayı sağlamaya ve sonraki araçlar için bağlamsal bilgi sunmaya yardımcı olurlar. Aspose.Tasks, `Prj.KEYWORDS` özelliğini sunarak bu değeri programatik olarak yazmayı veya güncellemeyi kolaylaştırır.

## Anahtar kelimeleri ve oluşturulma tarihini ayarlamak için neden Aspose.Tasks for Java kullanılmalı?
* **Tam .MPP uyumluluğu** – tüm Project 2007‑2023 formatlarıyla çalışır.  
* **COM veya Office kurulumu gerekmez** – saf Java, sunucu tarafı ortamları için mükemmel.  
* **Zengin API** – anahtar kelimelerin yanı sıra yazar, revizyon, yorumlar ve tarihleri tek bir çağrıda ayarlayabilirsiniz.  
* **Performans‑optimizeli** – büyük proje dosyalarında bile hızlı okuma/yazma.  

## Ön Koşullar
1. **Java Development Kit (JDK)** – JDK 8 veya daha yeni bir sürüm yüklü.  
2. **Aspose.Tasks for Java** – en son JAR dosyasını [buradan](https://releases.aspose.com/tasks/java/) indirin.  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans veya tercih ettiğiniz herhangi bir editör.  

## Paketleri İçe Aktarma
İlk olarak, ihtiyacınız olan sınıfları içe aktarın. Bu importlar, `Project` nesnesine, özet alanları için `Prj` enumerasyonuna ve kaydetme için `SaveFileFormat` enum'ına erişim sağlar.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Adım 1: Projeyi Kur ve Özet Bilgileri Tanımla
Bir `Project` örneği oluşturun, ardından istediğiniz meta verileri yazmak için `set` metodunu kullanın. `Calendar` nesnesiyle **anahtar kelimeleri ayarladığımıza** ve **java ile oluşturulma tarihini ayarladığımıza** dikkat edin.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## Adım 2: Proje Özet Bilgilerini Kaydet
Alanları doldurduktan sonra değişiklikleri kalıcı hale getirin. Burada projeyi kolay inceleme için XML olarak kaydediyoruz, ancak MPP olarak da kaydedebilirsiniz.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## Adım 3: Proje Özet Bilgilerini Oku
Meta verilerin doğru yazıldığını doğrulamak için dosyayı yeniden yükleyin ve her özelliği geri okuyun. Bu adım, **anahtar kelimeleri nasıl ayarlarsınız**ın uçtan uca gerçekten çalıştığını gösterir.

```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| **NullPointerException on `project.get(Prj.CREATION_DATE)`** | Kaydetmeden önce takvim hiç ayarlanmamıştı. | `save()`'den önce `project.set(Prj.CREATION_DATE, cal.getTime())` çağırdığınızdan emin olun. |
| **Keywords not appearing in Microsoft Project UI** | Dosya XML olarak kaydedildi ve doğrudan Project içinde açıldı. | MPP olarak kaydedin (`SaveFileFormat.MPP`) veya XML'i Project içinde *Import* (İçe Aktar) yoluyla açın. |
| **Date values shifted by timezone** | Java `Date` zaman dilimi bilgisi içerir. | UTC tarihine ihtiyacınız varsa `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))` kullanın. |

## Sıkça Sorulan Sorular

**Q: Aspose.Tasks for Java'ı diğer Java kütüphaneleriyle kullanabilir miyim?**  
A: Evet, Aspose.Tasks for Java diğer Java kütüphaneleriyle sorunsuz bir şekilde entegre edilerek proje yönetimi yeteneklerinizi artırabilir.

**Q: Aspose.Tasks for Java için deneme sürümü mevcut mu?**  
A: Evet, ücretsiz bir deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

**Q: Aspose.Tasks for Java ne sıklıkla güncelleniyor?**  
A: Aspose.Tasks for Java, Java ve Microsoft Project dosyalarının en son sürümleriyle uyumluluğu sağlamak için düzenli olarak güncellenir.

**Q: Proje özet bilgilerini daha da özelleştirebilir miyim?**  
A: Kesinlikle, Aspose.Tasks for Java, proje özet bilgilerini belirli gereksinimlerinize göre özelleştirmek için kapsamlı seçenekler sunar.

**Q: Aspose.Tasks for Java için destek nereden alınabilir?**  
A: Aspose.Tasks topluluk forumundan [burada](https://forum.aspose.com/c/tasks/15) destek alabilirsiniz.

---

**Son Güncelleme:** 2026-03-29  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.11 (yazım zamanındaki en son)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}