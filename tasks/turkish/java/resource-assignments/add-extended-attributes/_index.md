---
date: 2026-01-05
description: Aspose.Tasks for Java kullanarak proje başlangıç tarihini ayarlamayı
  ve MS Project XML dosyasını kaydetmeyi öğrenin. Java geliştiricileri için adım adım
  rehber.
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java ile Proje Başlangıç Tarihini Ayarlayın
url: /tr/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Proje Başlangıç Tarihini Aspose.Tasks for Java ile Ayarlama

## Giriş
Bu öğreticide, bir Microsoft Project dosyasında **proje başlangıç tarihini nasıl ayarlayacağınızı** ve ardından **MS Project XML'yi** Aspose.Tasks Java kütüphanesini kullanarak nasıl kaydedeceğinizi öğreneceksiniz. Raporlama hattını otomatikleştiriyor ya da özel bir proje‑yönetim aracı oluşturuyorsanız, bu görevi ustalaşmak zaman kazandırır ve manuel hataları ortadan kaldırır.

## Hızlı Cevaplar
- **Başlangıç tarihini ayarlamak için birincil yöntem nedir?** `project.set(Prj.START_DATE, …)` kullanın.
- **Dosyayı dışa aktarmak için hangi formatı kullanmalıyım?** `SaveFileFormat.Xml` ile XML olarak kaydedin.
- **Bu işlem için lisansa ihtiyacım var mı?** Deneme sürümü çalışır, ancak tam lisans su işaretlerini kaldırır.
- **Görevleri oluşturduktan sonra başlangıç tarihini değiştirebilir miyim?** Evet, görev eklemeden önce proje özelliğini güncelleyebilirsiniz.
- **Bu, tüm MS Project sürümleriyle uyumlu mu?** Aspose.Tasks XML, MPP ve daha fazlasını destekler.

## “Proje Başlangıç Tarihini Ayarlama” Nedir?
Proje başlangıç tarihini ayarlamak, tüm görev zamanlama hesaplamalarının başladığı temel takvimi tanımlar. Bu, programlı bir şekilde güvenilir bir proje takvimi oluşturmanın ilk adımıdır.

## Neden Aspose.Tasks for Java Kullanmalı?
Aspose.Tasks, Microsoft Project'in yüklü olmasını gerektirmeyen, herhangi bir platformda çalışan saf‑Java API'si sunar. Proje verilerini hızlı bir şekilde oluşturmanıza, değiştirmenize ve dışa aktarmanıza olanak tanır; bu da sunucu‑tarafı otomasyon için idealdir.

## Önkoşullar
1. **Java Development Kit (JDK)** – herhangi bir yeni JDK sürümü.
2. **Aspose.Tasks for Java** – [buradan](https://releases.aspose.com/tasks/java/) indirin.
3. **IDE** – IntelliJ IDEA, Eclipse veya tercih ettiğiniz Java IDE'si.

## Paketleri İçe Aktarma
İlk olarak, gerekli sınıfları içe aktarın:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Adım 1: Veri Dizinini Ayarlama
Oluşturulan dosyaların nerede saklanacağını tanımlayın.

```java
String dataDir = "Your Data Directory";
```

### Adım 2: Proje Örneği Oluşturma
Yeni, boş bir proje örneği oluşturun.

```java
Project project = new Project();
```

### Adım 3: Proje Bilgi Özelliklerini Ayarlama
Burada **proje başlangıç tarihini** ve ilgili zamanlama özelliklerini ayarlarız.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Adım 4: MS Project XML'yi Kaydetme
Yapılandırılmış projeyi bir XML dosyasına dışa aktarın.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Yaygın Sorunlar ve Çözümler
- **Yanlış tarih formatı:** Atamadan önce `java.util.Calendar` kullanıp `getTime()` çağırdığınızdan emin olun.
- **Dosya kaydedilmedi:** `dataDir`'in mevcut ve yazılabilir bir klasöre işaret ettiğini doğrulayın.
- **Lisans uyarıları:** Deneme sürümü su işaretleri ekler; bunları kaldırmak için geçerli bir lisans uygulayın.

## Sıkça Sorulan Sorular

### Q: Aspose.Tasks for Java ile MS Project dosyalarını okuyabilir miyim?  
**A:** Evet, Aspose.Tasks for Java, MS Project dosyalarını okuma ve yazma için sağlam işlevsellikler sağlar.

### Q: Aspose.Tasks for Java farklı MS Project sürümleriyle uyumlu mu?  
**A:** Kesinlikle, Aspose.Tasks for Java çeşitli MS Project formatlarını destekler ve geniş uyumluluk sağlar.

### Q: Aspose.Tasks for Java deneme sürümünün herhangi bir sınırlaması var mı?  
**A:** Deneme sürümü kütüphaneyi keşfetmenizi sağlar ancak çıktı dosyalarına su işaretleri ekler.

### Q: Aspose.Tasks for Java için desteği nasıl alabilirim?  
**A:** Aspose.Tasks topluluk forumundan [burada](https://forum.aspose.com/c/tasks/15) yardım isteyebilirsiniz.

### Q: Aspose.Tasks for Java için geçici bir lisans satın alabilir miyim?  
**A:** Evet, kısa vadeli kullanım için geçici lisanslar mevcuttur. Birini [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

### Q: XML olarak kaydetmek özel alanları korur mu?  
**A:** Evet, `SaveFileFormat.Xml` kullanarak kaydettiğinizde tüm özel nitelikler ve genişletilmiş alanlar korunur.

### Q: Görevleri ekledikten sonra başlangıç tarihini değiştirebilir miyim?  
**A:** Kaydetmeden önce istediğiniz zaman başlangıç tarihini güncelleyebilirsiniz; sadece `project.set(Prj.START_DATE, …)` tekrar çağırın.

---

**Son Güncelleme:** 2026-01-05  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}