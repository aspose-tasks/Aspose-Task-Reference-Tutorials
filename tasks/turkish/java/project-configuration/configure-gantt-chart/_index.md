---
date: 2025-12-09
description: Aspose.Tasks kullanarak Java'da veri dizinini nasıl ayarlayacağınızı
  ve Gantt şeması görünümünü nasıl yapılandıracağınızı öğrenin. Bu kılavuz ayrıca
  tablo alanlarını özelleştirmeyi ve Gantt şeması Java projelerini adım adım yapılandırmayı
  gösterir.
linktitle: Set Data Directory for Gantt Chart View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Gantt Şeması Görünümü için Veri Dizinini Ayarla
url: /tr/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Gantt Şeması Görünümü İçin Veri Dizinini Ayarlama

## Giriş
Bu öğreticide, **veri dizinini nasıl ayarlayacağınızı** ve Java kullanarak Aspose.Tasks projelerinde Gantt MS Project Şema Görünümünü yapılandırmayı öğreneceksiniz. Aspose.Tasks, Microsoft Project dosyalarını programlı olarak manipüle etmenizi sağlayan güçlü bir Java API'sidir. Bu kılavuzun sonunda **tablo alanlarını özelleştirebilecek**, veri dizinini ayarlayabilecek ve projenizi tam istediğiniz şekilde görselleştirebileceksiniz.

## Hızlı Yanıtlar
- **İlk adım nedir?** Proje dosyalarınızın bulunduğu veri dizini yolunu ayarlayın.  
- **Hangi kütüphane gereklidir?** Java için Aspose.Tasks (resmi siteden indirilebilir).  
- **Özel nitelikler ekleyebilir miyim?** Evet – genişletilmiş nitelikler tanımlayabilir ve bunları Gantt şemasında gösterebilirsiniz.  
- **Test için lisansa ihtiyacım var mı?** Değerlendirme amaçlı geçici bir lisans mevcuttur.  
- **Hangi IDE en iyisi?** Herhangi bir Java IDE (IntelliJ IDEA, Eclipse, NetBeans) çalışır.

## “Veri dizinini ayarlama” nedir ve neden önemlidir?
Veri dizinini ayarlamak, Aspose.Tasks'e proje dosyalarını nereden okuyup yazacağını bildirir. Doğru bir yol olmadan API `.mpp` dosyalarınızı bulamaz ve FileNotFound hatalarına yol açar. Bu dizini kodunuzun başında tanımlamak, geri kalan iş akışını temiz ve tekrarlanabilir hâle getirir.

## Gantt şemasında tablo alanlarını neden özelleştirirsiniz?
Özel tablo alanları, ek bilgileri—örneğin özel nitelikler, kaynak verileri veya proje‑özgü notlar—doğrudan Gantt görünümünde göstermenizi sağlar. Bu, şemayı paydaşlar için daha bilgilendirici hâle getirir ve birden fazla rapor arasında geçiş yapma ihtiyacını azaltır.

## Önkoşullar
1. **Java Development Kit (JDK)** – herhangi bir yeni sürüm (8+).  
2. **Aspose.Tasks Kütüphanesi** – bunu [buradan](https://releases.aspose.com/tasks/java/) indirin.  
3. **IDE** – IntelliJ IDEA, Eclipse veya tercih ettiğiniz herhangi bir Java‑uyumlu editör.

## Paketleri İçe Aktarma
İlk olarak, Aspose.Tasks ad alanını içe aktarın, böylece sınıflarıyla çalışabilirsiniz:

```java
import com.aspose.tasks.*;
```

## Adım‑Adım Kılavuz

### Adım 1: Veri Dizinini Ayarlama
Proje dosyalarınızı içeren klasörü tanımlayın. Bu, öğreticinin odaklandığı **veri dizinini ayarlama** adımıdır.

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` ifadesini `project.mpp` dosyasının bulunduğu klasörün mutlak yolu ile değiştirin.

### Adım 2: Proje Dosyasını Yükleme
Mevcut bir Microsoft Project dosyasını yükleyerek bir `Project` örneği oluşturun.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Adım 3: Yeni Aktivite Ekleme
Projeyi köküne yeni bir görev (aktivite) ekleyin.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Adım 4: Özel Nitelik Tanımlama
Daha sonra görevlere ekleyebileceğiniz bir özel nitelik tanımı oluşturun.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Adım 5: Göreve Özel Nitelik Ekleme
Yeni tanımlanan niteliği oluşturduğunuz göreve atayın.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Adım 6: Tabloyu Özelleştir – **tablo alanlarını özelleştir**
Gantt şema tablosunda özel niteliği bir sütun olarak ekleyin, genişlik, başlık ve hizalamayı belirterek.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Adım 7: Projeyi Kaydet
Değişiklikleri, Microsoft Project'te açılabilecek yeni bir dosyaya kaydedin.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| **FileNotFoundException** proje yüklenirken | **Veri dizinini ayarlama** yolu hatalı veya son slash eksik. | `dataDir`'in tam klasöre işaret ettiğini ve doğru dosya ayırıcı (`/` veya `\\`) içerdiğini doğrulayın. |
| Özel nitelik Gantt görünümünde görünmüyor | Tablo alanı yanlış bir indekse eklendi veya sütun genişliği çok küçük. | `table.getTableFields().add(3, attrField);` geçerli bir indeks kullandığından emin olun ve gerektiğinde `setWidth`'i ayarlayın. |
| Kaydetme sırasında LicenseException | Üretim kullanımı için geçerli bir lisans uygulanmadı. | `project.save()` çağrılmadan önce geçici veya kalıcı bir lisans uygulayın. |

## Sık Sorulan Sorular

**S: Aspose.Tasks'i diğer programlama dilleriyle kullanabilir miyim?**  
C: Evet, Aspose.Tasks .NET, Java ve C++ dahil birden fazla programlama dili için mevcuttur.

**S: Aspose.Tasks için ücretsiz deneme mevcut mu?**  
C: Evet, ücretsiz denemeyi [buradan](https://releases.aspose.com/) indirebilirsiniz.

**S: Aspose.Tasks için desteği nereden bulabilirim?**  
C: Destek ve sorularınızı [Aspose.Tasks forumunda](https://forum.aspose.com/c/tasks/15) bulabilirsiniz.

**S: Aspose.Tasks için lisans nasıl satın alınır?**  
C: Lisansı [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

**S: Test amaçları için geçici bir lisansa ihtiyacım var mı?**  
C: Evet, geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

## Sonuç
Artık **veri dizinini ayarlamayı**, yeni bir aktivite eklemeyi, bir özel nitelik tanımlamayı ve eklemeyi ve Aspose.Tasks for Java kullanarak Gantt şema görünümünde **tablo alanlarını özelleştirmeyi** öğrendiniz. Bu adımlar, proje verilerinin nasıl gösterileceği üzerinde tam kontrol sağlar, Gantt şemalarınızı daha bilgilendirici ve paydaşlarınızın ihtiyaçlarına göre özelleştirir.

---

**Son Güncelleme:** 2025-12-09  
**Test Edilen:** Aspose.Tasks Java 24.12 (latest)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}