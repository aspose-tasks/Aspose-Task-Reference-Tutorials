---
date: 2026-02-20
description: Aspose.Tasks for Java kullanarak proje başlangıç tarihini nasıl ayarlayacağınızı
  ve proje sapmalarını nasıl yöneteceğinizi öğrenin. Bu kılavuz ayrıca görev süresini
  verimli bir şekilde nasıl ayarlayacağınızı gösterir.
linktitle: Handle Task Variances in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Proje başlangıç tarihini ayarla ve görev varyanslarını yönet Aspose.Tasks
url: /tr/java/task-properties/handle-variances/
weight: 19
---

 maybe keep as is. In translation we kept it as bold English inside Turkish sentences. That's okay.

Now produce final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Proje başlangıç tarihini ayarlama ve görev varyanslarını yönetme Aspose.Tasks

## Giriş
Proje yönetimi dünyasında, **set project start date** programınıza sağlam bir temel vermek için attığınız ilk adımlardan biridir. Aspose.Tasks for Java bu adımı—ve ardından gelen görev varyanslarını yönetmeyi—kolay ve güvenilir kılar. Bu öğreticide proje başlangıç tarihini nasıl ayarlayacağınızı, görev süresini nasıl belirleyeceğinizi ve proje varyanslarını nasıl etkili bir şekilde yöneteceğinizi öğreneceksiniz.

## Hızlı Yanıtlar
- **Proje başlangıç tarihini ayarlamanın temel yöntemi nedir?** `project.set(Prj.START_DATE, …)` bir `java.util.Calendar` örneği ile kullanın.  
- **Varyans takibi için bir temel çizgiyi temsil eden sınıf hangisidir?** `BaselineType.Baseline`.  
- **Temel çizgi ayarlandıktan sonra görev başlangıç ve bitiş tarihlerini ayarlayabilir miyim?** Evet, sadece `Tsk.START` ve `Tsk.STOP` değerlerini güncelleyin.  
- **Geliştirme kullanımı için lisansa ihtiyacım var mı?** Değerlendirme için geçici bir lisans mevcuttur.  
- **Bu kodla hangi Aspose.Tasks sürümü çalışır?** En son Aspose.Tasks for Java sürümü.

## **set project start date** nedir?
Proje başlangıç tarihini ayarlamak, tüm görev tarihlerinin hesaplandığı takvim gününü tanımlar. Bu, takvim hesaplamalarını, kritik yol analizini ve temel çizgi oluşturulmasını etkiler ve doğru varyans yönetimi için hayati öneme sahiptir.

## Neden proje başlangıç tarihini ayarlamalı ve varyansları yönetmeliyiz?
- **Tahmin edilebilirlik:** Gerçek ilerlemeyi karşılaştırmak için bilinen bir temel çizgi oluşturur.  
- **Esneklik:** Orijinal planı kaybetmeden bireysel görev tarihlerini ayarlamanıza olanak tanır.  
- **Raporlama:** Takvim gecikmelerini veya erken bitişleri vurgulayan net varyans raporları sağlar.  

## Önkoşullar
İlerlemeye başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Java Geliştirme Ortamı – yüklü bir JDK ve hazır bir IDE veya derleme aracı.  
- Aspose.Tasks Kütüphanesi – kütüphaneyi **[buradan](https://releases.aspose.com/tasks/java/)** indirin.  

## Paketleri İçe Aktarma
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Adım 1: Projeyi Kurma
Tüm görevleri ve takvim bilgilerini tutacak yeni bir `Project` örneği oluşturun.

```java
Project project = new Project();
```

## Adım 2: Görev Ekleme
Kök görev altında bir görev ekleyin. Bu, daha sonra ayarlayacağımız iş öğesi olacak.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Adım 3: Başlangıç Tarihi ve Süre Ayarlama
Projenin başlangıç tarihini tanımlayın ve göreve bir süre verin. Bu, **set task duration** uygulamasını gösterir.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task.set(Tsk.DURATION, project.getDuration(2));
```

## Adım 4: Temel Çizgi Ayarlama
Planlanan ve gerçek tarihleri daha sonra karşılaştırabilmek için bir temel çizgi oluşturun—**manage project variances** için esastır.

```java
project.setBaseline(BaselineType.Baseline);
```

## Adım 5: Görev Başlangıç ve Bitiş Tarihlerini Ayarlama
Varyans senaryosunu simüle etmek için görevin başlangıç ve bitiş tarihlerini değiştirin.

```java
cal.set(2013, Calendar.NOVEMBER, 29, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2013, Calendar.NOVEMBER, 27, 8, 0, 0);
task.set(Tsk.STOP, cal.getTime());
```

*Tarihleri ve süreleri projenizin özel ihtiyaçlarına göre ayarlamaktan çekinmeyin.*

## Yaygın Sorunlar ve İpuçları
- **Temel çizgi, tarihleri ayarlamadan önce belirlenmelidir.** Tarihleri önce değiştirirseniz, temel çizgi orijinal plan yerine değiştirilmiş takvimi yakalar.  
- **Takvim ayları sıfır‑tabanlıdır.** `Calendar.FEBRUARY` ayının 1 olduğunu, 2 olmadığını unutmayın.  
- **Süre birimleri:** `project.getDuration(2)` varsayılan olarak iki günlük bir süre oluşturur; saat veya hafta gerekiyorsa birimi ayarlayın.

## Sonuç
**set project start date**, **set task duration** ve **manage project variances** konularında uzmanlaşarak Aspose.Tasks for Java kullanarak proje takviminiz üzerinde tam kontrol elde edersiniz. Yukarıdaki adımlar, çok‑fazalı projeler, kaynak tahsisi ve otomatik raporlama gibi daha karmaşık senaryolara genişletebileceğiniz sağlam bir temel sağlar.

## Sıkça Sorulan Sorular
### Aspose.Tasks tüm proje yönetimi ihtiyaçları için uygun mu?
Aspose.Tasks, geniş bir proje yönetimi gereksinim yelpazesi için uygun, esneklik ve güçlü özellikler sunan çok yönlü bir araçtır.

### Aspose.Tasks'i mevcut Java projemle entegre edebilir miyim?
Evet, sağlanan dokümantasyonu **[buradan](https://reference.aspose.com/tasks/java/)** izleyerek Aspose.Tasks'i Java projenize kolayca entegre edebilirsiniz.

### Aspose.Tasks için geçici bir lisans mevcut mu?
Evet, Aspose.Tasks için geçici bir lisansı **[buradan](https://purchase.aspose.com/temporary-license/)** alabilirsiniz.

### Aspose.Tasks için destek nereden alabilirim?
Destek ve tartışmalar için Aspose.Tasks forumunu **[buradan](https://forum.aspose.com/c/tasks/15)** ziyaret edin.

### Aspose.Tasks for Java'ı indirebilir miyim?
Evet, Aspose.Tasks for Java'ın en son sürümünü **[buradan](https://releases.aspose.com/tasks/java/)** indirebilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Tasks latest Java release  
**Author:** Aspose