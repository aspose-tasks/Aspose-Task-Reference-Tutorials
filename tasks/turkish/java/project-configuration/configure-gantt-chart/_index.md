---
date: 2026-02-13
description: Aspose.Tasks Java'da yeni bir etkinlik oluşturmayı, veri dizinini ayarlamayı
  ve projeyi MPP olarak kaydetmeyi öğrenin. Bu adım adım rehber ayrıca tablo alanlarını
  özelleştirmeyi de kapsar.
linktitle: How to Create New Activity & Set Data Directory Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Yeni Aktivite Oluşturma ve Aspose.Tasks Veri Dizinini Ayarlama
url: /tr/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Yeni Aktivite Oluşturma ve Veri Dizinini Ayarlama Aspose.Tasks

## Giriş
Bu öğreticide **veri dizinini ayarlama**, **yeni aktivite oluşturma** ve Gantt MS Project Chart View'i Aspose.Tasks projelerinde Java kullanarak **projeyi MPP olarak kaydetme** konularını öğreneceksiniz. Aspose.Tasks, Microsoft Project dosyalarını programlı olarak manipüle etmenizi sağlayan güçlü bir Java API'sidir. Bu kılavuzun sonunda **tablo alanlarını özelleştirme**, veri dizinini ayarlama ve projenizi tam istediğiniz gibi görselleştirme yeteneğine sahip olacaksınız.

## Hızlı Yanıtlar
- **İlk adım nedir?** Proje dosyalarınızın bulunduğu veri dizini yolunu ayarlayın.  
- **Hangi kütüphane gereklidir?** Aspose.Tasks for Java (resmi siteden indirilebilir).  
- **Özel nitelikler ekleyebilir miyim?** Evet – genişletilmiş nitelikler tanımlayabilir ve Gantt şemasında gösterebilirsiniz.  
- **Test için lisansa ihtiyacım var mı?** Değerlendirme amaçlı geçici bir lisans mevcuttur.  
- **Hangi IDE en iyisi?** Herhangi bir Java IDE (IntelliJ IDEA, Eclipse, NetBeans) çalışacaktır.

## “Veri dizinini ayarla” nedir ve neden önemlidir?
Veri dizinini ayarlamak, Aspose.Tasks'e proje dosyalarını nereden okuyup yazacağını söyler. Doğru bir yol olmadan API `.mpp` dosyalarınızı bulamaz ve FileNotFound hatalarına yol açar. Bu dizini kodunuzun başında tanımlamak, geri kalan iş akışını temiz ve tekrarlanabilir hâle getirir.

## Gantt şemasında tablo alanlarını neden özelleştirirsiniz?
Özel tablo alanları, ek bilgileri—örneğin özel nitelikler, kaynak verileri veya proje‑özel notlar—doğrudan Gantt görünümünde göstermenizi sağlar. Bu, paydaşlar için şemayı daha bilgilendirici hâle getirir ve birden fazla rapor arasında geçiş yapma ihtiyacını azaltır.

## Yeni aktivite nasıl oluşturulur?
Yeni bir aktivite (görev) oluşturmak, bir proje takvimini oluştururken veya güncellerken temel işlemlerden biridir. Görevleri programlı olarak ekleyerek karmaşık proje planlarının otomatik üretilmesini, diğer sistemlerden veri entegrasyonunu veya manuel düzenleme yapmadan toplu değişiklikleri uygulamayı sağlayabilirsiniz.

## Önkoşullar
1. **Java Development Kit (JDK)** – herhangi bir güncel sürüm (8+).  
2. **Aspose.Tasks Library** – bunu [buradan](https://releases.aspose.com/tasks/java/) indirin.  
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
Projeye kök seviyesinde yeni bir görev (aktivite) ekleyin. Bu, programlı olarak **yeni aktivite nasıl oluşturulur** gösterir.

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

### Adım 6: Tabloyu Özelleştirme – **tablo alanlarını özelleştir**
Gantt şema tablosuna özel niteliği bir sütun olarak ekleyin, genişlik, başlık ve hizalamayı belirterek.

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
Değişiklikleri Microsoft Project'te açılabilecek yeni bir dosyaya kaydedin. Bu adım **projeyi MPP olarak kaydeder**.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| **FileNotFoundException** proje yüklenirken | **set data directory** yolu hatalı veya son slash eksik. | `dataDir`'in tam klasöre işaret ettiğini ve doğru dosya ayırıcı (`/` veya `\\`) içerdiğini doğrulayın. |
| Gantt görünümünde özel nitelik görünmüyor | Tablo alanı yanlış indekse eklendi veya sütun genişliği çok küçük. | `table.getTableFields().add(3, attrField);` geçerli bir indeks kullandığından emin olun ve gerektiğinde `setWidth`'i ayarlayın. |
| Kaydetme sırasında LicenseException | Üretim kullanımı için geçerli bir lisans uygulanmadı. | `project.save()` çağrılmadan önce geçici veya kalıcı bir lisans uygulayın. |

## Sıkça Sorulan Sorular

**S: Aspose.Tasks'i diğer programlama dilleriyle kullanabilir miyim?**  
C: Evet, Aspose.Tasks .NET, Java ve C++ dahil olmak üzere birden fazla programlama dili için mevcuttur.

**S: Aspose.Tasks için ücretsiz deneme sürümü mevcut mu?**  
C: Evet, ücretsiz bir deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

**S: Aspose.Tasks için desteği nereden bulabilirim?**  
C: Destek ve sorularınızı [Aspose.Tasks forumunda](https://forum.aspose.com/c/tasks/15) bulabilirsiniz.

**S: Aspose.Tasks için lisans nasıl satın alınır?**  
C: Lisansı [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

**S: Test amaçlı geçici bir lisansa ihtiyacım var mı?**  
C: Evet, geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

## Sonuç
Artık **veri dizinini ayarlama**, **yeni aktivite oluşturma**, bir özel nitelik tanımlama ve ekleme ve **projeyi MPP olarak kaydetme** işlemlerini, Aspose.Tasks for Java kullanarak Gantt şema görünümünde **tablo alanlarını özelleştirme** ile nasıl yapacağınızı öğrendiniz. Bu adımlar, proje verilerinin nasıl gösterileceği üzerinde tam kontrol sağlar, Gantt şemalarınızı daha bilgilendirici ve paydaşlarınızın ihtiyaçlarına uygun hâle getirir.

---

**Son Güncelleme:** 2026-02-13  
**Test Edilen Versiyon:** Aspose.Tasks Java 24.12 (latest)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}