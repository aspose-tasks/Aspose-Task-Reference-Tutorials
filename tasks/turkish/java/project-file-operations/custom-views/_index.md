---
date: 2025-12-18
description: Aspose.Tasks for Java'da görünüm oluşturmayı, proje görünümünü kaydetmeyi
  ve görünüm özelliklerini ayarlamayı öğrenin. Özelleştirilmiş MS Project görünümleriyle
  proje yönetimi verimliliğini artırın.
linktitle: Custom Views in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Görünüm Nasıl Oluşturulur: Aspose.Tasks''te Özel MS Project Görünümleri'
url: /tr/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Görünüm Oluşturma: Aspose.Tasks'te Özel MS Project Görünümleri

## Giriş
Eğer projenizin benzersiz raporlama ihtiyaçlarına uygun **görünüm oluşturma** yöntemini arıyorsanız, doğru yerdesiniz. Proje yönetiminde, görünümleri özelleştirmek görev ve kaynakları yönetirken netliği ve verimliliği büyük ölçüde artırabilir. **Aspose.Tasks for Java**, **add custom view java**‑style çözümler eklemenizi sağlayan zengin bir API sunar ve MS Project görünümlerini tam istediğiniz gibi şekillendirmenize olanak tanır. Bu öğreticide, bir projeyi kurmaktan proje görünümünü kaydetmeye kadar adım adım süreci inceleyeceğiz.

## Hızlı Yanıtlar
- **Birincil amaç nedir?** Aspose.Tasks for Java kullanarak özel bir MS Project görünümü oluşturmak ve kalıcı hâle getirmek.  
- **Hangi sınıf bir görünüm oluşturur?** `GanttChartView` (veya diğer görünüm türleri).  
- **Görünümün menüde görünmesini nasıl sağlarım?** `view.setShowInMenu(true)` ayarlayın.  
- **Görünümü proje ile nasıl kaydederim?** `MPPSaveOptions` ile `setWriteViewData(true)` kullanın.  
- **Bir lisansa ihtiyacım var mı?** Evet, üretim kullanımı için geçerli bir Aspose.Tasks lisansı gereklidir.

## Önkoşullar
Başlamadan önce, aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

### Java Geliştirme Ortamı
Sisteminizde Java yüklü olduğundan emin olun.

### Aspose.Tasks for Java
Aspose.Tasks for Java'ı [buradan](https://releases.aspose.com/tasks/java/) indirip kurun.

## Paketleri İçe Aktarma
İlk olarak, Java projenize gerekli paketleri içe aktarın:
```java
import com.aspose.tasks.Field;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.HorizontalStringAlignment;
import com.aspose.tasks.MPPSaveOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.TableField;
import com.aspose.tasks.View;
```

## Adım 1: Projeyi Kurma
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```

## Adım 2: Görünüm Oluşturma
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```

## Adım 3: Görünüm Özelliklerini Özelleştirme *(set view properties)*
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```

### Görünüm Menüsünü Nasıl Gösterilir
`view.setShowInMenu(true)` çağrısı, yeni oluşturulan görünümün MS Project **view menu**'sunda görünmesini sağlar ve son kullanıcıların hızlı erişimini sağlar.

## Adım 4: Görünüm Ayarlarını Düzenleme
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```

## Adım 5: Görünümü Projeye Ekleme *(add custom view java)*
```java
// Add the view to our project
project.getViews().add(view);
```

## Adım 6: Projeyi Kaydetme *(save project view)*
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```

### Proje Görünümünü Kaydetmenin Önemi
`options.setWriteViewData(true)` ayarı, Aspose.Tasks'a MPP dosyasının içinde **project view** bilgisini kaydetmesini söyler, böylece özel görünüm oturumlar arasında kalıcı olur.

## Adım 7: Görünüm Özelliklerini Kontrol Etme
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```

## Yaygın Kullanım Senaryoları
- **Stakeholder Reporting:** Yalnızca üst‑seviye kilometre taşlarını ve kritik görevleri gösteren bir görünüm oluşturun.  
- **Resource Allocation:** Kaynakları atanan görevleriyle birlikte listeleyen bir görünüm oluşturun, böylece hızlı kapasite kontrolleri yapılabilir.  
- **Print‑Ready Documents:** Sayfa ayarlarını (Adım 4'teki gibi) ayarlayarak yazdırılabilir proje anlık görüntüleri oluşturun.

## Sorun Giderme İpuçları
- **View Not Appearing in Menu:** Kaydetmeden önce `view.setShowInMenu(true)` çağrıldığını doğrulayın.  
- **Missing Columns in Printout:** `setFirstColumnsCount`'un ihtiyacınız olan sütunlarla eşleştiğinden ve `setPrintFirstColumnsCountOnAllPages(true)`'un etkin olduğundan emin olun.  
- **License Exceptions:** Lisans hataları alırsanız, `Project` nesnesi oluşturulmadan önce geçerli bir Aspose.Tasks lisans dosyasının yüklendiğini doğrulayın.

## Sıkça Sorulan Sorular
### S1: Gantt grafikleri dışındaki görünümleri özelleştirebilir miyim?
C: Evet, Aspose.Tasks for Java, tablolar ve grafikler dahil olmak üzere Gantt grafikleri dışındaki çeşitli görünüm türlerini özelleştirme esnekliği sağlar.

### S2: Aspose.Tasks for Java büyük ölçekli projeler için uygun mu?
C: Kesinlikle. Kütüphane, her boyutta projeyi yönetebilecek şekilde tasarlanmıştır ve sağlam performans ile bellek yönetimi sunar.

### S3: Aspose.Tasks for Java görünümleri farklı formatlara dışa aktarmayı destekliyor mu?
C: Evet, görünümleri PDF, XLSX, HTML ve diğer formatlara dışa aktarabilirsiniz; bu, platformlar arasında sorunsuz paylaşımı sağlar.

### S4: Aspose.Tasks for Java kullanarak özel görünümlerin oluşturulmasını otomatikleştirebilir miyim?
C: Elbette. API tam otomasyonu mümkün kılar ve özel görünümleri programlı olarak oluşturup yönetmenizi sağlar.

### S5: Aspose.Tasks for Java desteği için bir topluluk forumu var mı?
C: Evet, Java ile ilgili sorular ve tartışmalar için [Aspose.Tasks forumunda](https://forum.aspose.com/c/tasks/15) yardım bulabilir ve diğer kullanıcılarla etkileşime geçebilirsiniz.

---

**Son Güncelleme:** 2025-12-18  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}