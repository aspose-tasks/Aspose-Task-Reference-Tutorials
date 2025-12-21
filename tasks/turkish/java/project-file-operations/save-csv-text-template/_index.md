---
date: 2025-12-21
description: Aspose.Tasks for Java kullanarak projeyi şablon olarak kaydetmeyi, MPP'yi
  CSV'ye dışa aktarmayı ve MPP'yi metne dönüştürmeyi öğrenin.
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Projeyi Şablon, CSV ve Metin Olarak Aspose.Tasks for Java ile Kaydet
url: /tr/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projeyi Şablon, CSV ve Metin Olarak Aspise.Tasks ile Kaydet

## Giriş
Bu öğreticide, **projeyi şablon olarak kaydetmeyi** ve ayrıca Microsoft Project (MPP) dosyalarınızı CSV ve düz metin formatlarına Aspose.Tasks Java kütüphanesini kullanarak dışa aktarmayı keşfedeceksiniz. Yeniden kullanılabilir bir proje şablonu oluşturmanız, analiz için CSV raporları üretmeniz veya entegrasyon için basit metin çıkartmaları yapmanız gerekirse, bu adımlar süreci hızlı ve verimli bir şekilde yönlendirecek.

## Hızlı Yanıtlar
- **MPP'yi CSV'ye dışa aktarabilir miyim?** Evet – `project.save(..., SaveFileFormat.CSV)` kullanın.  
- **Metni nasıl dışa aktarırım?** `SaveFileFormat.TEXT` ile kaydedin.  
- **“Projeyi şablon olarak kaydet” ne yapar?** Gerçek ve temel değerleri kaldıran bir `.mpt` dosyası oluşturur, yeniden kullanım için hazır.  
- **Lisans gerekir mi?** Bir deneme sürümü mevcuttur; üretim için ticari lisans gereklidir.  
- **Hangi Java sürümü gerekiyor?** Java 8+ desteklenir.

## “Projeyi şablon olarak kaydet” nedir?
`.mpt` olarak bir projeyi şablon olarak kaydetmek, yapıyı, görev hiyerarşisini ve kaynak atamalarını yakalar, aynı zamanda gerçek başlangıç/bitiş tarihlerini ve temel verileri kaldırır. Bu, şablonu birden çok yeni proje arasında standart bir proje düzenini yeniden kullanmak için ideal kılar.

## Neden Aspose.Tasks for Java kullanmalı?
Aspose.Tasks, Microsoft Project'i kurmadan Microsoft Project dosyalarını manipüle etmenizi sağlar. **MPP'yi nasıl dışa aktarılır**, **metni nasıl dışa aktarılır** ve **MPP'yi CSV'ye dönüştürür** gibi işlemleri saf Java kodundan destekler; bu da sunucu tarafı otomasyonu, CI boru hatları veya masaüstü yardımcı programları için mükemmeldir.

## Önkoşullar
1. Java Development Kit (JDK) 8 veya daha üstü yüklü.  
2. Aspose.Tasks for Java kütüphanesini projenize ekleyin. [buradan](https://releases.aspose.com/tasks/java/) indirin.  
3. Java sözdizimi ve Maven/Gradle proje kurulumu hakkında temel bilgi.

## Paketleri İçe Aktar
İlk olarak, Java kaynak dosyanıza gerekli sınıfları içe aktarın:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Projeyi CSV Olarak Kaydet (MPP'yi CSV'ye Dışa Aktar)
Bir MPP dosyasını CSV'ye dışa aktarmak, Excel veya BI araçlarında veri analizi için faydalıdır.

### Adım 1: Projeyi Yükle
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Adım 2: CSV Olarak Kaydet
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Projeyi Metin Olarak Kaydet (Metni Nasıl Dışa Aktar?)
Görevlerin, kaynakların veya atamaların düz metin temsiline ihtiyacınız varsa, projeyi bir metin dosyası olarak kaydedin.

### Adım 1: Projeyi Yükle
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Adım 2: Metin Olarak Kaydet
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Projeyi Şablon Olarak Kaydet (Java Proje Şablonu Oluştur)
Yeniden kullanılabilir bir şablon oluşturmak, **gerçek tarihleri** ve **temel verileri** kaldırır, **yeni** projeler için **temiz bir iskelet** bırakır.

### Adım 1: Projeyi Yükle
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Adım 2: Şablon Seçeneklerini Ayarla
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### Adım 3: Şablon Olarak Kaydet
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Yaygın Sorunlar ve İpuçları
- **Dosya Bulunamadı:** `YourProject.mpp` yolunun doğru olduğundan emin olun veya mutlak bir yol kullanın.  
- **Lisans İstisnaları:** Geçerli bir lisans olmadan, kütüphane değerlendirme modunda çalışır ve filigran ekleyebilir. Lisansınızı kodun başında uygulayın (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **Büyük Projeler:** Çok büyük MPP dosyaları için JVM yığın boyutunu (`-Xmx2g`) artırmayı düşünün, `OutOfMemoryError` hatasından kaçınmak için.

## Sonuç
**Projeyi şablon olarak kaydetmeyi**, **MPP'yi CSV'ye dışa aktarmayı** ve **MPP'yi metne dönüştürmeyi** Aspose.Tasks for Java kullanarak ele aldık. Bu yetenekler, proje verilerini otomatikleştirmenizi, yeniden kullanılabilir şablonlar oluşturmanızı ve proje bilgilerini diğer sistemlere entegre etmenizi sağlar — Microsoft Project kurulumuna ihtiyaç duymadan.

## SSS
### Q: Aspose.Tasks for Java karmaşık proje dosyalarını işleyebilir mi?
A: Kesinlikle! Aspose.Tasks for Java, farklı **karmaşıklık** seviyelerindeki projeleri kolaylıkla yönetebilir ve Microsoft Project dosya formatları için kapsamlı destek sağlar.  
### Q: Aspose.Tasks for Java için bir deneme sürümü mevcut mu?
A: Evet, [buradan](https://releases.aspose.com/) Aspose.Tasks for Java için **ücretsiz deneme** sürümü alabilirsiniz.  
### Q: Aspose.Tasks for Java için **destek** nereden bulabilirim?
A: [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret ederek Aspose.Tasks for Java ile ilgili her türlü yardım ve soruya ulaşabilirsiniz.  
### Q: Aspose.Tasks for Java için geçici bir lisans satın alabilir miyim?
A: Evet, [buradan](https://purchase.aspose.com/temporary-license/) geçici bir lisans satın alarak kütüphanenin tam potansiyelini değerlendirebilirsiniz.  
### Q: Aspose.Tasks for Java farklı işletim sistemleriyle uyumlu mu?
A: Evet, Aspose.Tasks for Java Windows, macOS ve Linux dahil olmak üzere çeşitli işletim sistemleriyle uyumludur.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose  

---