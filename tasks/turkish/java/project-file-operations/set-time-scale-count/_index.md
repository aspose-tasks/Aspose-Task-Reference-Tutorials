---
date: 2025-12-21
description: Aspose.Tasks for Java kullanarak Gantt şeması görünümlerini özelleştirmeyi,
  proje görselleştirmesini yönetmeyi ve projeyi PDF olarak kaydetmeyi öğrenin. Zaman
  ölçeği sayısını zahmetsizce ayarlayın.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Gantt Şemasını Özelleştir – Aspose.Tasks'te MS Project Zaman Ölçeği Sayısını
  Ustalıkla Kullanma
url: /tr/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gantt Şemasını Özelleştirme – Aspose.Tasks ile MS Project Zaman Ölçeği Sayısını Ustalıkla Kullanma

## Giriş
Microsoft Project'te **Gantt şemasını özelleştirme** görsellerine ihtiyaç duyuyorsanız, zaman‑ölçeği sayısını kontrol etmek temel bir tekniktir. Aspose.Tasks for Java ile alt ve orta zaman‑ölçeği katmanlarını programlı olarak ayarlayabilir, tik görünürlüğünü ince ayar yapabilir ve ardından **projeyi PDF olarak kaydedebilir** ve paydaşlarla paylaşabilirsiniz. Bu öğretici, ortamı kurmaktan özelleştirilmiş Gantt görünümünüzü yansıtan şık bir PDF oluşturulana kadar tüm süreci adım adım anlatır.

## Hızlı Yanıtlar
- **“Gantt şemasını özelleştirmek” ne anlama geliyor?** Raporlama ihtiyaçlarınıza uygun zaman‑ölçeği katmanlarını, renkleri ve düzeni ayarlamak.  
- **Alt katman sayısını ayarlayan API metodu hangisidir?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Projeden doğrudan PDF oluşturabilir miyim?** Evet—`project.save(..., SaveFileFormat.Pdf)` kullanın.  
- **Üretim kullanımında lisansa ihtiyacım var mı?** Ticari bir lisans gereklidir; ücretsiz bir deneme sürümü mevcuttur.  
- **Hangi Java sürümü destekleniyor?** Java 8 ve üzeri, en yeni Aspose.Tasks kütüphanesiyle çalışır.

## Aspose.Tasks'de “Gantt şemasını özelleştirme” nedir?
Gantt şemasını özelleştirmek, zaman‑ölçeği aralıkları, tik işaretleri ve görev çubukları gibi görsel bileşenleri programlı olarak değiştirerek şemanın **proje görselleştirmesini yönetme** biçiminize uymasını sağlamaktır. Zaman‑ölçeği sayısını değiştirerek, her segmentin kaç gün, hafta veya ay temsil ettiğini kontrol eder, böylece farklı izleyiciler için şema daha anlaşılır hâle gelir.

## Önkoşullar
Başlamadan önce şunların olduğundan emin olun:

1. **Java Geliştirme Ortamı** – JDK 8 veya daha yeni bir sürüm yüklü.  
2. **Aspose.Tasks for Java Kütüphanesi** – [buradan](https://releases.aspose.com/tasks/java/) indirin.  
3. **Temel Java Bilgisi** – Java sözdizimi ve nesne‑yönelimli kavramlara aşina olmak.

## Paketleri İçe Aktarma
Java projenize gerekli sınıfları ekleyin:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Adım‑Adım Kılavuz

### Adım 1: Veri Dizinini Ayarla
Proje dosyalarınızın okunup yazılacağı yeri tanımlayın:

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` kısmını makinenizdeki mutlak yol ile değiştirin.

### Adım 2: Yeni Bir Proje Örneği Oluştur
Tüm görevleri ve görünüm ayarlarını tutacak yeni bir `Project` nesnesi oluşturun:

```java
Project project = new Project();
```

### Adım 3: Gantt Şeması Görünümünü Yapılandır
Bir `GanttChartView` nesnesi oluşturun—bu, şema görünümünü kontrol etmek için **Gantt view Java** kodu oluşturacağınız yerdir:

```java
GanttChartView view = new GanttChartView();
```

### Adım 4: Alt Katman İçin Zaman Ölçeği Sayısını Ayarla
Alt katmanı iki aralık gösterecek şekilde ayarlayın ve tik işaretlerini gizleyin:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Adım 5: Orta Katman İçin Zaman Ölçeği Sayısını Ayarla
Aynı yapılandırmayı orta katmana uygulayın:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Adım 6: Özelleştirilmiş Görünümü Projeye Ekle
Az önce yapılandırdığınız görünümü `Project` örneğine ekleyin:

```java
project.getViews().add(view);
```

### Adım 7: Örnek Görevler Ekle (Test Verileri)
Özelleştirilmiş Gantt şemasını göstermek için belirli sürelerle birkaç görev oluşturun:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Adım 8: Projeyi PDF Olarak Kaydet
Son olarak, **özelleştirilmiş Gantt şemanız** dahil proje dosyasını bir PDF dosyasına dışa aktarın:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

Ortaya çıkan PDF, alt ve orta zaman‑ölçeği katmanlarının **özelleştirildiğini** gösterir ve paydaşlara takvimin net, yazdırılabilir bir görünümünü sunar.

## Yaygın Sorunlar ve Çözümleme
- **PDF boş** – `dataDir` yolunun bir dosya ayırıcı (`/` veya `\`) ile bittiğinden ve dizinin mevcut olduğundan emin olun.  
- **Tikler hâlâ görünüyor** – `setShowTicks(false)` metodunun her iki katmanda da çağrıldığını doğrulayın.  
- **Süre uygulanmadı** – Süre oluştururken `TimeUnitType.Hour` (veya uygun birim) kullandığınızı teyit edin.

## Sık Sorulan Sorular

**S: Aspose.Tasks for Java büyük ölçekli proje dosyalarını işleyebilir mi?**  
C: Evet, kütüphane geniş proje verilerini yüksek performansla işlemek için optimize edilmiştir.

**S: Aspose.Tasks for Java farklı Java IDE'leriyle uyumlu mu?**  
C: Kesinlikle – Eclipse, IntelliJ IDEA, NetBeans ve diğer popüler IDE'lerle sorunsuz çalışır.

**S: Zaman‑ölçeği ayarlarının ötesinde Gantt şemalarının görünümünü özelleştirebilir miyim?**  
C: Evet, Aspose.Tasks çubuk renkleri, yazı tipleri ve ızgara çizgileri gibi kapsamlı stil seçenekleri sunar.

**S: Aspose.Tasks for Java için bir deneme sürümü var mı?**  
C: Evet, ücretsiz bir deneme sürümünü [buradan](https://releases.aspose.com/) alabilirsiniz.

**S: Aspose.Tasks for Java desteğini nereden alabilirim?**  
C: Destek ve yardım için Aspose.Tasks forumunu [burada](https://forum.aspose.com/c/tasks/15) bulabilirsiniz.

**S: Gantt şemasının arka plan rengini programlı olarak nasıl değiştiririm?**  
C: `java.awt.Color` sınıfını içe aktardıktan sonra `view.getGanttChartProperties().setBackgroundColor(Color)` metodunu kullanın.

## Sonuç
Bu adımları izleyerek **Gantt şemasını özelleştirme** zaman‑ölçeği katmanlarını nasıl ayarlayacağınızı, **proje görselleştirmesini** nasıl iyileştireceğinizi ve Aspose.Tasks for Java kullanarak **projeyi PDF olarak kaydetme** işlemini öğrendiniz. Bu yöntem, görsel çıktınız üzerinde tam kontrol sağlar ve ekibinizle veya müşterilerinizle net, profesyonel takvimleri paylaşmayı kolaylaştırır.

---

**Son Güncelleme:** 2025-12-21  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12 (yazım anındaki en yeni sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}