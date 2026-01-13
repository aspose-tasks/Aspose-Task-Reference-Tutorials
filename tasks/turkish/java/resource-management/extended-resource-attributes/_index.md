---
date: 2026-01-13
description: Aspose.Tasks for Java ile özel öznitelik oluşturmayı, Microsoft Project
  dosyasını yüklemeyi, sayısal değeri ayarlamayı ve projeyi XML olarak kaydetmeyi
  öğrenin.
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks kullanarak MS Project'te Özel Öznitelik Oluşturma
url: /tr/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project'te Aspose.Tasks Kullanarak Özel Nitelik Oluşturma

## Giriş
Bu öğreticide, **Microsoft Project dosyasında kaynaklar için özel nitelik** oluşturmayı Aspose.Tasks for Java kullanarak öğreneceksiniz. Bir Microsoft Project dosyasını yükleme, yeni bir sayısal nitelik tanımlama, bir değer atama ve sonunda projeyi XML olarak kaydetme adımlarını göstereceğiz. Sonunda, kendi proje‑yönetim çözümlerinizde uyarlayabileceğiniz net, uygulamalı bir örnek elde edeceksiniz.

## Hızlı Yanıtlar
- **“custom attribute” ne demektir?**  
  Bir kaynak veya görev için ekstra bilgi (ör. Yaş, Beceri Seviyesi) depolayan kullanıcı tanımlı alan.  
- **Bu işlemi hangi kütüphane yönetir?**  
  Aspose.Tasks for Java, özel nitelikler oluşturmak ve yönetmek için akıcı bir API sağlar.  
- **Lisans gerekir mi?**  
  Değerlendirme için ücretsiz geçici bir lisans yeterlidir; üretim için tam lisans gereklidir.  
- **Sayısal değerler ayarlayabilir miyim?**  
  Evet – `setNumericValue` metodunu bir `BigDecimal` ile (ör. `30.5345`) kullanın.  
- **Proje nasıl kaydedilir?**  
  Değiştirilen dosya `SaveFileFormat.Xml` kullanılarak XML olarak kaydedilebilir.

## Özel Nitelik Nedir?
Bir **custom attribute** (genişletilmiş nitelik olarak da adlandırılır), Microsoft Project'te kaynaklara veya görevlere ekleyebileceğiniz ek bir sütundur. Yerleşik alanların kapsamadığı verileri, örneğin çalışan yaşı, sertifika seviyesi veya herhangi bir iş‑özel metriği yakalamanızı sağlar.

## MS Project'te Neden Özel Nitelik Oluşturmalısınız?
- **Proje verilerini kuruluşunuzun ihtiyaçlarına göre özelleştirin.**  
- **İleri raporlamayı etkinleştirin**; daha sonra sorgulanabilecek değerler depolayın.  
- **Birden çok proje arasında tutarlılığı koruyun**; aynı nitelik tanımını programatik olarak uygulayın.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Java Geliştirme Ortamı** – JDK 8 veya üzeri yüklü.  
2. **Aspose.Tasks for Java** – En son sürümü [buradan](https://releases.aspose.com/tasks/java/) indirin.  
3. **IDE** – Eclipse, IntelliJ IDEA veya herhangi bir Java‑uyumlu IDE.  

## Adım‑Adım Kılavuz

### Paketleri İçe Aktar
İlk olarak, ihtiyacınız olan Aspose.Tasks sınıflarını içe aktarın. Bu sınıflar projeleri, kaynakları ve genişletilmiş nitelikleri işlemek için temel işlevselliği sağlar.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

### Adım 1: Veri Dizinini Tanımla
Kaynak proje dosyanızın bulunduğu ve çıktının yazılacağı klasörü ayarlayın.

```java
String dataDir = "Your Data Directory";
```

### Adım 2: Microsoft Project Dosyasını Yükle
Mevcut dosyayı yükleyerek bir `Project` örneği oluşturun. Bu, **Microsoft proje dosyasını yükle** adımıdır ve içeriğine tam erişim sağlar.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### Adım 3: Özel Niteliği Tanımla
Yeni bir sayısal nitelik olan **Age**'i tanımlayacağız. API, tanımın zaten var olup olmadığını kontrol eder; yoksa oluşturur.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### Adım 4: Java'da Sayısal Değer Ayarla
Belirli bir kaynak için nitelik örneği oluşturun ve `setNumericValue` kullanarak sayısal bir değer atayın. Bu, **set numeric value java** işleminin bir gösterimidir.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### Adım 5: Kaynak Ekle ve Özel Niteliği Bağla
**R1** adında yeni bir kaynak ekleyin ve önceden oluşturulan özel niteliği ona iliştirin.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### Adım 6: Projeyi XML Olarak Kaydet
Değişiklikleri kalıcı hâle getirmek için projeyi kaydedin. Bu, **save project as xml** adımıdır ve güncellenmiş dosyanın temiz bir XML temsili oluşturur.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### Adım 7: Sonucu Görüntüle
İşlemin hatasız tamamlandığını gösteren dostane bir onay mesajı yazdırın.

```java
System.out.println("Process completed Successfully");
```

Bu adımları izleyerek **özel nitelik** oluşturmuş, bir Microsoft Project dosyasını yüklemiş, Java ile sayısal bir değer ayarlamış ve projeyi XML olarak kaydetmiş oldunuz.

## Yaygın Tuzaklar ve İpuçları
- **Nitelik ID çakışmaları:** Yeni bir tanım oluşturmadan önce `getById` ile kontrol edin; böylece yinelenen ID'lerden kaçının.  
- **Kesinlik yönetimi:** `BigDecimal` ondalık kesinliğini korur; tam değerler için `float` veya `double` kullanmaktan kaçının.  
- **Dosya yolları:** `FileNotFoundException` hatalarını önlemek için mutlak yollar kullanın veya IDE'nizin çalışma dizinini yapılandırın.  

## Sık Sorulan Sorular

**S: Görevler için de özel nitelikler oluşturabilir miyim?**  
C: Evet – nitelik tanımlarken `ExtendedAttributeTask` kullanın, `ExtendedAttributeResource` yerine.

**S: Aynı anda birden fazla özel nitelik eklemek mümkün mü?**  
C: Kesinlikle. Her nitelik için ayrı `ExtendedAttributeDefinition` nesneleri oluşturun ve istediğiniz kaynaklara veya görevlere bağlayın.

**S: Projeyi hangi formatlarda kaydedebilirim?**  
C: Aspose.Tasks XML, MPP ve PDF, HTML gibi çeşitli formatları destekler. Bu örnekte `SaveFileFormat.Xml` kullandık.

**S: Geliştirme sürümleri için Aspose.Tasks lisansına ihtiyacım var mı?**  
C: Değerlendirme için geçici bir lisans yeterlidir. Üretim dağıtımları için tam lisans gereklidir.

**S: Daha sonra özel nitelik değerlerini nasıl okuyabilirim?**  
C: `resource.getExtendedAttributes()` ile ilişkilendirilmiş nitelikleri döngüye alıp, `getNumericValue()` veya `getTextValue()` ile değerlerini alabilirsiniz.

## Sonuç
Aspose.Tasks for Java ile Microsoft Project'te **özel nitelik** oluşturmak, iş akışını anladıktan sonra oldukça basittir: projeyi yükleyin, niteliği tanımlayın, değerini ayarlayın, bir kaynağa bağlayın ve dosyayı kaydedin. Bu yaklaşım, proje veri modellerinizi programatik olarak genişletmenizi, daha zengin raporlamalar yapmanızı ve iş süreçlerinizle daha sıkı entegrasyon sağlamanızı mümkün kılar.

---

**Son Güncelleme:** 2026-01-13  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}