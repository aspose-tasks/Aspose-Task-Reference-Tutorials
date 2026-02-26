---
date: 2026-02-26
description: Aspose.Tasks for Java ile görevleri nasıl böleceğinizi öğrenin – görevleri
  bölme, proje takvimini ayarlama ve kaynak ataması oluşturma konusunda kesin rehber.
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Görevleri Nasıl Bölümlere Ayırılır
url: /tr/java/task-properties/split-tasks/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Görevleri Nasıl Bölümlere Ayırırsınız

## Giriş
Java tabanlı bir projede **görevleri nasıl bölümlere ayıracağınızı** arıyorsanız, doğru yerdesiniz. Aspose.Tasks for Java, uzun süren bir görevi daha küçük, yönetilebilir parçalara ayırmanın temiz, programatik bir yolunu sunar; bu da kaynak dengelemesi, doğru raporlama ve daha sıkı proje zaman çizelgeleri için yardımcı olur. Bu öğreticide, proje takvimini ayarlamaktan bir kaynak ataması oluşturmaya ve nihayetinde görevi birden çok bölüme ayırmaya kadar tüm süreci adım adım inceleyeceğiz.

## Hızlı Yanıtlar
- **Görev bölme nedir?** Tek bir görevi toplam süresini koruyarak birkaç daha küçük aralığa bölmek.  
- **Java'da görevleri neden bölmeliyim?** Kesin kaynak tahsisi ve daha iyi ilerleme takibi sağlar.  
- **Hangi kütüphane yardımcı olur?** Aspose.Tasks for Java, bölme ve zaman‑fazlaması için yerleşik yöntemler sunar.  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme çalışır; üretim için lisans gerekir.  
- **Hangi Java sürümü destekleniyor?** Kütüphane Java 8 ve üzeri sürümlerle çalışır.

## Önkoşullar
Öğreticiye başlamadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- Makinenizde Java Development Kit (JDK) yüklü olmalı.  
- Aspose.Tasks for Java kütüphanesini indirin ve projenize ekleyin. İndirmek için [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) sayfasını ziyaret edebilirsiniz.

## Paketleri İçe Aktarma
Gerekli paketleri Java projenize aşağıdaki gibi dahil edin:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## Adım 1: Yeni Bir Proje Oluşturma
Aspose.Tasks kütüphanesini kullanarak yeni bir proje oluşturun:

```java
// Create a new project
Project splitTaskProject = new Project();
```

## Adım 2: Proje Takvimini Ayarlama
**Proje takvimini** ayarlamak, çalışma günlerini, tatilleri ve takvimin genel zaman çizelgesini tanımlar. Bu adım, doğru zaman‑fazlamalı hesaplamalar için gereklidir.

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Adım 3: Kök Görev Ekleme
Her projenin bir kök konteyneri gerekir. Kök görev eklemek, sonraki tüm görevleri ekleyeceğiniz bir yer sağlar.

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## Adım 4: Bölünecek Yeni Görevi Ekleme
Bölmek istediğiniz görevi oluşturun. Örnek olarak üç günlük bir süre belirliyoruz.

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## Adım 5: Kaynak Ataması Oluşturma
Bir **kaynak ataması**, bir kaynağı (veya yer tutucuyu) göreve bağlar. Zaman‑fazlamalı veri oluşturulmadan önce bu gereklidir.

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## Adım 6: Zaman‑Fazlamalı Veri Oluşturma
Zaman‑fazlamalı veri, işin görevin süresi boyunca nasıl dağıtıldığını gösterir. Oluşturulması, görevin bölünmeye hazırlanmasını sağlar.

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## Adım 7: Görevi Bölme
Şimdi **görevi parçalara bölüyoruz**. Bu örnekte üç günlük görevi üç bir günlük bölüme ayırıyoruz.

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Neden Görev Bölünür?
Görevleri bölmek, aşağıdaki konularda daha ince kontrol sağlar:
- **Kaynak dengelemesi:** Her bölüme farklı kaynaklar atayabilirsiniz.  
- **İlerleme takibi:** Durumu bölüm bazında güncelleyebilirsiniz.  
- **Raporlama:** Daha ayrıntılı Gantt şemaları ve raporlar oluşturabilirsiniz.

## Yaygın Sorunlar ve Çözümler
- **Takvim verisi eksik:** Bölmeden önce `timephasedDataFromTaskDuration` metodunu çağırdığınızdan emin olun.  
- **Sıfır‑süreli bölümler:** Her bölünmüş aralığın sıfır olmayan bir süresi olduğundan emin olun; aksi takdirde kütüphane bunu görmezden gelir.  
- **Lisans istisnaları:** Geçerli bir lisans olmadan çalışmak, dışa aktarılan dosyalara filigran ekleyebilir.

## Sıkça Sorulan Sorular
### Farklı sürelerde görevleri bölüp ayırabilir miyim?
Evet, her parçanın süresini proje gereksinimlerinize göre ayarlayabilirsiniz.

### Aspose.Tasks for Java tüm Java sürümleriyle uyumlu mu?
Aspose.Tasks for Java, Java 8 ve üzeri sürümlerle sorunsuz çalışacak şekilde tasarlanmıştır; geniş bir uyumluluk sağlar.

### Aspose.Tasks for Java'ı ücretsiz kullanabilir miyim?
Aspose.Tasks for Java, satın almadan önce özelliklerini keşfetmenizi sağlayan ücretsiz bir deneme sunar.

### Aspose.Tasks for Java için destek nasıl alınır?
Yardım almak ve toplulukla iletişime geçmek için [Aspose.Tasks for Java support forum](https://forum.aspose.com/c/tasks/15) adresini ziyaret edin.

### Aspose.Tasks for Java için geçici bir lisansa ihtiyacım var mı?
Test ve değerlendirme amaçlı olarak [bu bağlantıdan](https://purchase.aspose.com/temporary-license/) geçici bir lisans alabilirsiniz.

---

**Son Güncelleme:** 2026-02-26  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}