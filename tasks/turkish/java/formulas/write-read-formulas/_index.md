---
date: 2025-12-07
description: Aspose.Tasks for Java kullanarak proje dosyasını nasıl kaydedeceğinizi,
  MS Project formüllerini nasıl yazıp okuyacağınızı ve özel alan formüllerini nasıl
  ekleyeceğinizi öğrenin.
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks ile Proje Dosyasını Kaydedin ve MS Project Formüllerini Yazın
url: /tr/java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Proje Dosyasını Kaydet ve Aspose.Tasks ile MS Project Formülleri Yaz

## Giriş
Proje yönetimi alanında, verilerin etkili bir şekilde işlenmesi çok önemlidir. Aspose.Tasks for Java, Microsoft Project dosyalarından veri manipülasyonu ve çıkarımını kolaylaştıran sağlam bir çözümdür. Sunduğu güçlü özelliklerden biri, MS Project formüllerini yazma ve okuma yeteneğidir. **Bu formülleri uyguladıktan sonra *save project file* nasıl kaydedileceğini de öğreneceksiniz**, böylece değişiklikleriniz gelecekteki analizler için kalıcı olur. Bu eğitim, bu işlevi kullanarak proje yönetimi görevlerinizi geliştirme sürecinde size rehberlik edecektir.

## Hızlı Yanıtlar
- **“save project file” ne yapar?** Bellekteki tüm değişiklikleri diskteki bir .mpp dosyasına yazar.  
- **Özel alan formülleri ekleyebilir miyim?** Evet – “double task cost” gibi bir formül atayarak özel bir alan oluşturabilirsiniz.  
- **Kodu çalıştırmak için lisansa ihtiyacım var mı?** Değerlendirme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Hangi IDE en iyisi?** Herhangi bir Java IDE (IntelliJ IDEA, Eclipse, VS Code) örneği derleyecektir.  
- **API en son MS Project sürümüyle uyumlu mu?** Aspose.Tasks, tüm yeni .mpp formatlarını destekler.

## Aspose.Tasks'te “save project file” nedir?
Bir proje dosyasını kaydetmek, `Project` nesnesinin mevcut durumunu—görevler, kaynaklar ve herhangi bir özel formül dahil—fiziksel bir Microsoft Project dosyasına (`.mpp`) kalıcı olarak kaydetmek anlamına gelir. Bu işlem, özel alan eklemek veya görev maliyetlerini değiştirmek gibi verileri değiştirdikten sonra gereklidir.

## Neden özel bir alan ekleyip özel alan formülü oluşturmalıyız?
Özel bir alan eklemek, varsayılan alanların kapsamadığı ek bilgiler için esnek bir konteyner sağlar. **double task cost** gibi bir formül ekleyerek, hesaplamaları otomatikleştirir, manuel hataları azaltır ve takvim verilerinizi tutarlı tutarsınız.

## Önkoşullar
Bu eğitime başlamadan önce, aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1. **Java Development Kit (JDK)** – Makinenizde Java 8 veya daha üstü yüklü.  
2. **Aspose.Tasks for Java** – [burada](https://releases.aspose.com/tasks/java/) indirip kurun.  
3. **Integrated Development Environment (IDE)** – Java geliştirme için tercih ettiğiniz IDE'yi seçin (IntelliJ IDEA, Eclipse, VS Code vb.).

## Paketleri İçe Aktarma
Başlamak için, Java projenize gerekli paketleri içe aktarın:

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Adım 1: Veri Dizinini Ayarlama
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
MS Project dosyalarınızın bulunduğu klasörü tanımlayın. Kaynak dosyayı burada yükleyecek ve daha sonra **save project file** işlemini burada yapacaksınız.

## Adım 2: Proje Dosyasını Yükleme
```java
Project project = new Project(dataDir + "project.mpp");
```
Mevcut Microsoft Project dosyasını bir `Project` nesnesine yükleyin, böylece içeriğini okuyabilir veya değiştirebilirsiniz.

## Adım 3: Özel Alan Ekle ve Özel Alan Formülü Oluştur
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```
Bu adımda **add custom field** “Double Costs” ve **create custom field formula** işlemlerini yapıyoruz; bu formül, görevin `[Cost]` değerini 2 ile çarpar, yani **double task cost** elde eder. `setFormula` yöntemi hesabı doğrudan proje dosyasına gömer.

## Adım 4: Görev Ekle ve Maliyeti Ayarla
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Yeni bir görev oluşturun ve ardından temel maliyeti `100` olarak atayın. Proje kaydedildiğinde, daha önce tanımlanan formül sayesinde özel alan otomatik olarak `200` gösterir.

## Adım 5: Proje Dosyasını Kaydet
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Son olarak, tüm değişikliklerle birlikte **save project file** yapın. `save` yöntemi, yeni özel alan ve hesaplanan değerler dahil güncellenmiş projeyi `saved.mpp` dosyasına yazar.

## Yaygın Sorunlar ve Çözümleri
| Sorun | Neden | Çözüm |
|-------|--------|-----|
| **Formül uygulanmadı** | Özel alan, projenin `ExtendedAttributes` koleksiyonuna eklenmedi. | Kaydetmeden önce `project.getExtendedAttributes().add(attr);` kodunun çalıştırıldığından emin olun. |
| **Dosya bulunamadı** | `dataDir` yolu hatalı. | Dizin dizesinin bir yol ayırıcı (`/` veya `\\`) ile bittiğini doğrulayın. |
| **Maliyet 0 olarak görünüyor** | Görev maliyeti kaydetmeden önce ayarlanmamış. | `project.save`'den önce `task.set(Tsk.COST, ...)` çağırın. |

## Sıkça Sorulan Sorular
**S: Aspose.Tasks tüm MS Project sürümleriyle uyumlu mu?**  
C: Evet, Aspose.Tasks, eski .mpp formatlarından en yeni sürümlere kadar geniş bir MS Project sürüm yelpazesini destekler.

**S: Aspose.Tasks'i mevcut Java projemle entegre edebilir miyim?**  
C: Kesinlikle. API, sorunsuz entegrasyon için tasarlanmıştır; sadece Aspose.Tasks JAR dosyasını projenizin sınıf yoluna ekleyin.

**S: Oluşturabileceğim formül türlerinde herhangi bir sınırlama var mı?**  
C: Kütüphane, aritmetik, mantıksal ve yerleşik fonksiyonlar dahil olmak üzere çoğu yerel MS Project formül sözdizimini destekler. Karmaşık özel fonksiyonlar için geçici çözümler gerekebilir.

**S: Aspose.Tasks çok platformlu dağıtımı destekliyor mu?**  
C: Evet, kütüphane Java'yı destekleyen herhangi bir platformda çalışır; Windows, Linux ve macOS dahil.

**S: Aspose.Tasks için teknik destek nasıl alabilirim?**  
C: Topluluk yardımı için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edin veya ticari lisansınız varsa bir destek bileti açın.

## Sonuç
Bu eğitimde, Aspose.Tasks for Java kullanarak **save project file**, **add custom field** ve **double task cost** yapan **create a custom field formula** işlemlerini ele aldık. Bu adımları izleyerek hesaplamaları otomatikleştirebilir, proje verilerinizi zenginleştirebilir ve tüm değişikliklerin gelecekteki raporlama ve analizler için kalıcı olmasını sağlayabilirsiniz.

---

**Son Güncelleme:** 2025-12-07  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}