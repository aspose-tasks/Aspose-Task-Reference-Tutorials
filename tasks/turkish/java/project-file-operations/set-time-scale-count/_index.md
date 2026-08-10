---
date: 2026-03-29
description: Aspose.Tasks for Java kullanarak Gantt şeması zaman ölçeği sayısını özelleştirirken
  proje PDF dosyaları oluşturmayı öğrenin. Bu rehber, Gantt'ı tam kontrolle PDF'ye
  nasıl dışa aktaracağınızı adım adım gösterir.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Proje PDF Oluştur – Gantt Çizelgesi Zaman Ölçeğini Özelleştir
url: /tr/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Proje PDF Oluştur – Gantt Şeması Zaman Ölçeğini Özelleştir

## Giriş
Eğer **proje PDF oluştur** dosyalarına ihtiyacınız varsa ve mükemmel ayarlanmış bir Gantt şemasını yansıtıyorsa, zaman‑ölçeği sayısını kontrol etmek anahtardır. Aspose.Tasks for Java ile alt ve orta zaman‑ölçeği katmanlarını programlı olarak ayarlayabilir, işaretçileri gizleyebilir ve ardından **projeyi PDF olarak kaydedebilir** ve kolay dağıtım sağlayabilirsiniz. Bu öğreticide, geliştirme ortamını kurmaktan özelleştirilmiş Gantt görünümünüzü sergileyen cilalı bir PDF üretmeye kadar ihtiyacınız olan her şeyi adım adım göstereceğiz.

## Hızlı Yanıtlar
- **“customize Gantt chart” ne anlama geliyor?** Zaman ölçeği katmanlarını, renkleri ve düzeni raporlama ihtiyaçlarınıza göre ayarlamak.  
- **Alt katman sayısını ayarlayan API yöntemi hangisidir?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Projeden doğrudan bir PDF oluşturabilir miyim?** Evet—`project.save(..., SaveFileFormat.Pdf)` kullanın.  
- **Üretim kullanımında lisansa ihtiyacım var mı?** Ticari bir lisans gereklidir; ücretsiz deneme sürümü mevcuttur.  
- **Hangi Java sürümü destekleniyor?** Java 8 ve üzeri, en son Aspose.Tasks kütüphanesiyle çalışır.

## Aspose.Tasks'te “customize Gantt chart” nedir?
Gantt şemasını özelleştirmek, zaman‑ölçeği aralıkları, işaretçiler ve görev çubukları gibi görsel bileşenlerini programlı olarak değiştirmek anlamına gelir; böylece şema, **proje görselleştirmesini yönetmek** istediğiniz şekilde hizalanır. Zaman‑ölçeği sayısını değiştirerek, her segmentin kaç gün, hafta veya ay temsil ettiğini kontrol eder ve şemayı farklı izleyiciler için daha anlaşılır hâle getirirsiniz.

## Neden özelleştirilmiş bir Gantt şemasıyla proje PDF oluşturmalısınız?
- **Paydaş‑hazır çıktısı:** PDF evrensel olarak görüntülenebilir, herkesin aynı zaman çizelgesi düzenini görmesini sağlar.  
- **Yazdırma‑dostu:** Zaman‑ölçeği katmanları üzerinde hassas kontrol, kalabalık veya belirsiz çıktıları önler.  
- **Otomasyon:** PDF oluşturmayı CI boru hatlarına veya raporlama hizmetlerine entegre ederek sıfır manuel çaba gerektirir.  

## Ön Koşullar
Başlamadan önce şunların kurulu olduğundan emin olun:

1. **Java Geliştirme Ortamı** – JDK 8 ve üzeri yüklü.  
2. **Aspose.Tasks for Java Kütüphanesi** – [buradan](https://releases.aspose.com/tasks/java/) indirin.  
3. **Temel Java Bilgisi** – Java sözdizimi ve nesne‑yönelimli kavramlara aşina olmak.

## Paketleri İçe Aktar
Java projenize gerekli sınıfları içe aktarın:

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
Proje dosyalarınızın okunacağı ve yazılacağı yeri tanımlayın:

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` ifadesini makinenizdeki mutlak yol ile değiştirin.

### Adım 2: Yeni Bir Proje Örneği Oluştur
Tüm görevleri ve görünüm ayarlarını tutacak yeni bir `Project` nesnesi oluşturun:

```java
Project project = new Project();
```

### Adım 3: Gantt Şeması Görünümünü Yapılandır
Bir `GanttChartView` nesnesi oluşturun—bu, şema görünümünü kontrol etmek için **generate Gantt view Java** kodunu yazacağınız yerdir:

```java
GanttChartView view = new GanttChartView();
```

### Adım 4: Alt Katman İçin Zaman Ölçeği Sayısını Ayarla
Alt katmanı iki aralık gösterecek şekilde ayarlayın ve işaretçileri gizleyin:

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
Son olarak, **özelleştirilmiş Gantt şeması** dahil projenizi bir PDF dosyasına dışa aktarın:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

Ortaya çıkan PDF, alt ve orta zaman‑ölçeği katmanlarının nasıl **özelleştirildiğini** gösterir ve paydaşlara net, yazdırılabilir bir takvim görünümü sunar.

## Yaygın Sorunlar ve Sorun Giderme
- **PDF boş** – `dataDir` yolunun bir dosya ayırıcı (`/` veya `\`) ile bittiğinden ve dizinin mevcut olduğundan emin olun.  
- **İşaretçiler hâlâ görünüyor** – `setShowTicks(false)` metodunun her iki katmanda da çağrıldığını doğrulayın.  
- **Süre uygulanmadı** – Süre oluştururken `TimeUnitType.Hour` (veya uygun bir birim) kullandığınızı doğrulayın.

## Sıkça Sorulan Sorular

**Q: Aspose.Tasks for Java büyük ölçekli proje dosyalarını işleyebilir mi?**  
A: Evet, kütüphane geniş proje verilerinin yüksek performanslı işlenmesi için optimize edilmiştir.

**Q: Aspose.Tasks for Java farklı Java IDE'leriyle uyumlu mu?**  
A: Kesinlikle – Eclipse, IntelliJ IDEA, NetBeans ve diğer popüler IDE'lerle sorunsuz çalışır.

**Q: Zaman ölçeği ayarlarının ötesinde Gantt şemalarının görünümünü özelleştirebilir miyim?**  
A: Evet, Aspose.Tasks çubuk renkleri, yazı tipleri ve ızgara çizgileri gibi kapsamlı stil seçenekleri sunar.

**Q: Aspose.Tasks for Java için bir deneme sürümü mevcut mu?**  
A: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) edinebilirsiniz.

**Q: Aspose.Tasks for Java için destek nereden alınabilir?**  
A: Destek ve yardımı Aspose.Tasks forumunda [buradan](https://forum.aspose.com/c/tasks/15) bulabilirsiniz.

**Q: Gantt şemasının arka plan rengini programlı olarak nasıl değiştiririm?**  
A: `java.awt.Color` sınıfını içe aktardıktan sonra `view.getGanttChartProperties().setBackgroundColor(Color)` metodunu kullanın.

## Sonuç
Bu adımları izleyerek, Aspose.Tasks for Java kullanarak tamamen özelleştirilmiş bir Gantt şeması zaman ölçeğiyle **proje PDF oluştur** dosyalarını nasıl oluşturacağınızı, **proje görselleştirmesini** geliştireceğinizi ve **projeyi PDF olarak kaydet** öğreneceksiniz. Bu yaklaşım, görsel çıktının tam kontrolünü size verir ve ekibinizle ya da müşterilerinizle net, profesyonel takvimleri paylaşmayı kolaylaştırır.

---

**Son Güncelleme:** 2026-03-29  
**Test Edilen Versiyon:** Aspose.Tasks for Java (latest)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}