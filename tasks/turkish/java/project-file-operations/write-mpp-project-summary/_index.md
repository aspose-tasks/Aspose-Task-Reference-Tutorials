---
date: 2025-12-23
description: Aspose.Tasks for Java kullanarak MPP özetini nasıl oluşturacağınızı ve
  proje yazarını nasıl güncelleyeceğinizi öğrenin. Proje bilgilerini zahmetsizce ayarlayın
  ve alın.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks ile MPP Özeti Oluşturma ve Proje Yazarını Güncelleme
url: /tr/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile MPP Proje Özeti Yazma

## Giriş
Bu öğreticide, bir Microsoft Project dosyası için **MPP özeti** bilgisi oluşturacak ve Aspose.Tasks Java kütüphanesini kullanarak **proje yazarını** güncelleme detaylarını öğreneceksiniz. Proje yönetim aracı oluşturuyor ya da raporlamayı otomatikleştiriyor olun, özet özelliklerini programlı olarak kontrol etmek zaman tasarrufu sağlar ve projelerinizde tutarlılığı garanti eder.

## Hızlı Yanıtlar
- **“create MPP summary” ne anlama geliyor?** Microsoft Project'in Proje Özeti Bilgileri iletişim kutusunda görünen yüksek‑seviye proje özelliklerini (yazar, revizyon, anahtar kelimeler vb.) ayarlamak anlamına gelir.  
- **Bu işlemi hangi kütüphane yönetir?** Aspose.Tasks for Java, bu özellikleri okuma ve yazma için akıcı bir API sağlar.  
- **Lisans gerekir mi?** Ücretsiz deneme sürümü mevcuttur, ancak üretim kullanımı için ticari bir lisans gereklidir.  
- **Dosya kaydedildikten sonra da yazar değiştirilebilir mi?** Evet – `project.set(Prj.AUTHOR, "New Author")` çağırarak **project author** güncelleyebilir ve ardından dosyayı yeniden kaydedebilirsiniz.  
- **Hangi dosya formatları destekleniyor?** Hem MPP hem de XML (SaveFileFormat.Xml) tam olarak desteklenir.

## MPP özeti oluşturmak nedir?
MPP özeti oluşturmak, projenin meta verilerini—yazar, revizyon numarası, anahtar kelimeler, yorumlar, oluşturma tarihi ve yazdırma tarihi—doldurmayı içerir. Bu meta veriler, Proje Özeti Bilgileri kaydı içinde depolanır ve Microsoft Project'in **File → Info** bölümünde görüntülenir.

## Neden proje yazarını güncellemeliyiz?
**project author** bilgisinin doğru tutulması, denetim izleri, iş birliği ve raporlama için çok önemlidir. Birden fazla ekip üyesi katkıda bulunduğunda, en son değişiklikleri yansıtmak veya çalışmayı doğru şekilde atfetmek için **project author** güncellemeniz gerekebilir.

## Önkoşullar
1. Makinenizde yüklü Java Development Kit (JDK).  
2. Aspose.Tasks for Java – bunu [here](https://releases.aspose.com/tasks/java/) adresinden indirin.  
3. IntelliJ IDEA, Eclipse veya NetBeans gibi bir IDE.

## Paketleri İçe Aktarma
Firstly, import the necessary packages into your Java class:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Adım 1: Projeyi Kur ve Özet Bilgilerini Tanımla
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
Yukarıdaki kodda yazar, revizyon ve anahtar kelimeler gibi **MPP summary** alanları **create MPP summary** oluşturuyoruz. Daha sonra `project.set(Prj.AUTHOR, "New Name")` çağırarak **project author** güncelleyebilirsiniz.

## Adım 2: Proje Özet Bilgilerini Kaydet
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
Projeyi kaydetmek, az önce tanımladığınız tüm özet verileri kalıcı hale getirir.

## Adım 3: Proje Özet Bilgilerini Oku
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
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
Bu kod parçacığı, özet bilgileri **read back** (geri okuma) nasıl yapacağınızı gösterir ve **create MPP summary** işleminin başarılı olduğunu doğrular.

## Yaygın Sorunlar ve Çözümler
- **Okuduktan sonra null değerler:** Projenin yeniden yüklemeden önce başarılı bir şekilde kaydedildiğinden emin olun. Dosya yollarını ve izinleri kontrol edin.  
- **Tarih biçimlendirme farklılıkları:** `project.get(Prj.CREATION_DATE)` bir `java.util.Date` döndürür. Özel bir görüntü formatına ihtiyacınız varsa `SimpleDateFormat` kullanın.  
- **Lisans ayarlanmamış:** Geçerli bir lisans olmadan Aspose.Tasks değerlendirme modunda çalışır ve bir filigran ekleyebilir. Lisansınızı kodun başında kaydedin.

## Sıkça Sorulan Sorular
**S: Aspose.Tasks for Java'yı diğer Java kütüphaneleriyle kullanabilir miyim?**  
C: Evet, Aspose.Tasks for Java, proje yönetimi yeteneklerinizi artırmak için diğer Java kütüphaneleriyle sorunsuz bir şekilde entegre edilebilir.

**S: Aspose.Tasks for Java için bir deneme sürümü mevcut mu?**  
C: Evet, ücretsiz bir deneme sürümünü [here](https://releases.aspose.com/) adresinden indirebilirsiniz.

**S: Aspose.Tasks for Java ne sıklıkla güncelleniyor?**  
C: Aspose.Tasks for Java, Java ve Microsoft Project dosyalarının en son sürümleriyle uyumluluğu sağlamak için düzenli olarak güncellenir.

**S: Proje özet bilgilerini daha da özelleştirebilir miyim?**  
C: Kesinlikle, Aspose.Tasks for Java, proje özet bilgilerini özel gereksinimlerinize göre özelleştirmek için kapsamlı seçenekler sunar.

**S: Aspose.Tasks for Java için nereden destek alabilirim?**  
C: Aspose.Tasks topluluk forumundan [here](https://forum.aspose.com/c/tasks/15) destek alabilirsiniz.

## Sonuç
Bu öğreticide, **MPP summary** verilerini nasıl **create MPP summary** oluşturacağınızı, **project author** nasıl **update project author** güncelleyeceğinizi ve bu değişiklikleri Aspose.Tasks for Java kullanarak nasıl doğrulayacağınızı gösterdik. Bu adımları otomatikleştirerek proje meta verileri üzerinde tam kontrol elde eder, uygulamalarınızı daha sağlam ve proje raporlarınızı daha doğru hâle getirirsiniz.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}