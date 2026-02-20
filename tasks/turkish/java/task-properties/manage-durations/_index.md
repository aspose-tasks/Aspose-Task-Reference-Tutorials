---
date: 2026-02-20
description: Aspose.Tasks for Java ile projeye görev eklemeyi ve süreleri yönetmeyi
  keşfedin. Süreyi nasıl ayarlayacağınızı ve süreyi kolayca nasıl dönüştüreceğinizi
  öğrenin.
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projeye Görev Ekle ve Süreleri Aspose.Tasks ile Yönet
url: /tr/java/task-properties/manage-durations/
weight: 20
---

am ne olur?**"

Answer translate.

Then horizontal line.

**Last Updated:** 2026-02-20 => keep same.

**Tested With:** Aspose.Tasks for Java (latest) => keep.

**Author:** Aspose => keep.

Then closing shortcodes.

Finally backtop button shortcode.

Make sure to keep all shortcodes exactly.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Görev Ekleyin Projeye ve Süreleri Aspose.Tasks ile Yönetin

## Giriş
Bu öğreticide **projeye görev ekleme** ve süresini Aspose.Tasks for Java kullanarak kontrol etmeyi öğreneceksiniz. Yeni bir proje planlama aracı oluşturuyor ya da mevcut bir çözümü genişletiyor olun, görev‑süre yönetimini ustalaşmak doğru zamanlama ve raporlama için gereklidir.

## Hızlı Yanıtlar
- **“projeye görev ekleme” ne anlama geliyor?** Bir proje kökü altında ya da belirli bir özet görev altında yeni bir görev nesnesi oluşturur.  
- **Hangi sınıf bir süreyi temsil eder?** `com.aspose.tasks.Duration`.  
- **Süre nasıl ayarlanır?** `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))` kullanın.  
- **Bir süreyi başka bir birime dönüştürebilir miyim?** Evet, `duration.convert(TimeUnitType.Hour)` ya da diğer `TimeUnitType` değerlerini çağırın.  
- **Üretim için lisansa ihtiyacım var mı?** Ticari kullanım için geçerli bir Aspose.Tasks lisansı gereklidir.

## “projeye görev ekleme” nedir?
Projeye görev eklemek, bir `Task` nesnesi oluşturup onu projenin görev hiyerarşisine eklemek anlamına gelir. Bu işlem, görev için iş, kaynak veya süre tanımlamadan önceki ilk adımdır.

## Neden görev sürelerini yönetin?
Doğru süreler, gerçekçi zaman çizelgeleri, kaynak tahsisi ve kritik yol analizini sağlar. Aspose.Tasks ile süreleri programlı olarak ayarlayabilir, okuyabilir, dönüştürebilir ve düzenleyebilirsiniz; böylece proje takvimleri üzerinde tam kontrol elde edersiniz.

## Önkoşullar
Başlamadan önce aşağıdakilerin kurulu olduğundan emin olun:

- Java Development Kit (JDK): Makinenizde Java yüklü olduğundan emin olun. [buradan](https://www.oracle.com/java/technologies/javase-downloads.html) indirebilirsiniz.
- Aspose.Tasks Kütüphanesi: Aspose.Tasks kütüphanesini projenize indirin ve ekleyin. Kütüphaneyi [burada](https://releases.aspose.com/tasks/java/) bulabilirsiniz.

## Paketleri İçe Aktarın
Java projenizde Aspose.Tasks ile çalışmak için gerekli paketleri içe aktarın:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Adım 1: Projenizi Kurun
```java
// Create a new project
Project project = new Project();
```

## Adım 2: Yeni Bir Görev Ekleyin (projeye görev ekleme)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## Süreyi Nasıl Ayarlarsınız
Görev artık mevcut, uzunluğunu tanımlayabilirsiniz. Varsayılan olarak, süreler gün cinsinden ifade edilir.

## Adım 3: Görev Süresini Alın ve Dönüştürün
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## Süreyi Nasıl Dönüştürürsünüz
`convert` metodu, bir `Duration` nesnesini bir `TimeUnitType` değerinden başka birine (ör. gün → saat, hafta → gün) çevirmeyi sağlar.

## Adım 4: Görev Süresini 1 Hafta Olarak Güncelleyin
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## Adım 5: Görev Süresini Azaltın
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

Bu adımları izleyerek **projeye bir görev eklemiş** ve süresini Aspose.Tasks for Java kullanarak yönetmiş oldunuz.

## Yaygın Tuzaklar ve İpuçları
- **Tuzak:** Aritmetik işlem yapmadan önce süreyi dönüştürmeyi unutmak hatalı sonuçlara yol açabilir. Birimi her zaman `duration.getTimeUnit()` ile doğrulayın.  
- **İpucu:** Süreleri daha sonra dönüştürmek yerine istediğiniz birimde oluşturmak için `project.getDuration(value, TimeUnitType)` kullanın.  
- **Tuzak:** Negatif bir süre ayarlamak bir istisna fırlatır. Girdi değerlerini doğruladığınızdan emin olun.

## Sonuç
Bu rehberde **projeye görev ekleme**, varsayılan süresini okuma, **süreyi ayarlama** ve **süreyi farklı zaman birimlerine dönüştürme** konularını ele aldık. Artık bu teknikleri daha büyük zamanlama uygulamalarına entegre ederek hassas proje planlaması yapabilirsiniz.

## SSS

### Aspose.Tasks tüm Java sürümleriyle uyumlu mu?
Aspose.Tasks Java 6 ve sonraki sürümlerle uyumludur.

### Aspose.Tasks'i ticari projelerde kullanabilir miyim?
Evet, Aspose.Tasks'i hem kişisel hem de ticari projelerde kullanabilirsiniz. Lisans detayları için [buraya](https://purchase.aspose.com/buy) bakın.

### Ek destek ve kaynakları nerede bulabilirim?
Topluluk desteği ve tartışmalar için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edin.

### Test amaçlı geçici bir lisans nasıl alabilirim?
Test ve değerlendirme için geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) alabilirsiniz.

### Aspose.Tasks için ücretsiz deneme mevcut mu?
Satın almadan önce Aspose.Tasks'i keşfetmek için ücretsiz deneme sürümüne [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

## Sıkça Sorulan Sorular

**S: Bir görevin süresi ayarlandıktan sonra nasıl değiştiririm?**  
C: Mevcut süreyi `task.get(Tsk.DURATION)` ile alın, değiştirin (ör. `add`, `subtract` veya `convert`), ardından `task.set(Tsk.DURATION, newDuration)` ile geri ayarlayın.

**S: Süreyi dakikalar içinde ayarlayabilir miyim?**  
C: Evet, `project.getDuration(value, TimeUnitType.Minute)` kullanarak dakikalar cinsinden bir süre oluşturabilirsiniz.

**S: Süreyi değiştirmek görevin başlangıç ve bitiş tarihlerini otomatik olarak günceller mi?**  
C: Yalnızca projenin zamanlama modu otomatik olarak ayarlanmışsa günceller. Aksi takdirde, `project.calculateCriticalPath()` ile takvimi yeniden hesaplamanız gerekir.

**S: Süreyi ham bir sayı olarak almak mümkün mü?**  
C: Mevcut zaman birimindeki sayısal değeri elde etmek için `duration.getTimeSpan()` metodunu çağırın.

**S: Mevcut süreden daha fazlasını çıkarırsam ne olur?**  
C: API bir `ArgumentOutOfRangeException` fırlatır. Sonucun pozitif kalmasını her zaman doğrulayın.

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Tasks for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}