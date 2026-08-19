---
date: 2026-02-28
description: Aspose.Tasks for Java – proje yönetimi için güçlü bir kütüphane – kullanarak
  projeye görev eklemeyi ve Java ile görev takvimi oluşturmayı öğrenin.
linktitle: Tasks and Calendars in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projeye Görev Ekle ve Aspose.Tasks for Java ile Takvimleri Yönet
url: /tr/java/task-properties/tasks-and-calendars/
weight: 33
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projeye Görev Ekleme ve Takvimleri Aspose.Tasks for Java ile Yönetme

## Giriş
Projeye **görev eklemeye** ve takviminizi mükemmel bir şekilde hizalamaya hazır mısınız? Bu rehberde görev oluşturma, bunları özel takvimlere ekleme ve sektörde lider **java project management library** Aspose.Tasks'i kullanma adımlarını anlatacağız. Sonunda **create task calendar java**‑style **oluşturma** konusunda tam kontrol sahibi olacaksınız.

## Hızlı Yanıtlar
- **Ana amaç nedir?** Projeye görev eklemek ve bunu özel bir takvimle ilişkilendirmek.  
- **Hangi kütüphaneyi kullanmalıyım?** Aspose.Tasks for Java – tam özellikli bir project‑management API.  
- **Lisans gerekli mi?** Ücretsiz deneme sürümü mevcuttur; üretim için ticari lisans gereklidir.  
- **Gerekli JDK sürümü nedir?** Java 8 veya üzeri.  
- **Uygulama ne kadar sürer?** Temel senaryolar için genellikle 15 dakikadan az.

## “add task to project” nedir?
Projeye görev eklemek, bir Project nesnesi içinde bir iş öğesi oluşturmak ve özelliklerini (süre, başlangıç tarihi, takvim vb.) tanımlamak anlamına gelir. Bu işlem, takvim odaklı herhangi bir uygulamanın temel yapı taşıdır.

## Neden bir Java proje yönetim kütüphanesi kullanmalı?
Aspose.Tasks gibi özel bir kütüphane, karmaşık MS‑Project dosya formatı, kaynak dengeleme ve takvim hesaplamalarını sizin için yönetir. Tekrar tekrar aynı şeyi yapmaktan sizi kurtarır ve sektördeki standart araçlarla uyumluluğu garanti eder.

## Önkoşullar
Öğreticiye başlamadan önce aşağıdaki önkoşulların karşılandığından emin olun:
- Java Development Kit (JDK): Sisteminizde Java yüklü olduğundan emin olun.
- Aspose.Tasks Library: Aspose.Tasks kütüphanesini indirin ve projenize ekleyin. Kütüphaneyi [burada](https://releases.aspose.com/tasks/java/) bulabilirsiniz.

## Paketleri İçe Aktarma
Java projenizde, Aspose.Tasks için gerekli paketleri içe aktarın:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

## Adım 1: Projenizi Kurun
Yeni bir Java projesi oluşturarak ve Aspose.Tasks JAR dosyasını derleme yolunuza ekleyerek başlayın. Bu, tam API'ye erişmenizi sağlar.

## Adım 2: Projeye Görev Nasıl Eklenir
Yeni bir `Project` örneği oluşturun ve **Task1** adlı bir kök‑seviyesi görevi ekleyin. Bu, temel “add task to project” işlemini gösterir.

```java
Project project = new Project();
Task tsk = project.getRootTask().getChildren().add("Task1");
```

## Adım 3: Java’da Görev Takvimi Nasıl Oluşturulur
Projenize standart bir takvim ekleyin. Takvimler çalışma günlerini, tatilleri ve diğer zamanlama kurallarını tanımlar.

```java
Calendar cal = project.getCalendars().add("TaskCal1");
```

## Adım 4: Görevi Takvimle İlişkilendirme
Önceden oluşturulan görevi yeni takvime bağlayarak, zaman çizelgesinin takvimin çalışma saatlerine uymasını sağlayın.

```java
tsk.set(Tsk.CALENDAR, cal);
```

*İpucu:* İhtiyacınız olan her ek görev ve takvim için bu adımları tekrarlayın. `Calendar` API'sını kullanarak takvim istisnalarını (ör. çalışılmayan günler) da özelleştirebilirsiniz.

## Yaygın Sorunlar ve Çözümler
- **Görev takvim değişikliklerini yansıtmıyor:** Takvimleri değiştirdikten sonra `project.updateStructure()` çağırdığınızdan emin olun.  
- **`set` çağrısında NullPointerException:** Atamadan önce takvimin projeye başarıyla eklendiğini doğrulayın.  
- **İçe/dışa aktarma sonrası hatalı tarihler:** `project.save("output.mpp")` kullanın ve verilerin kalıcı olduğunu doğrulamak için yeniden açın.

## Sıkça Sorulan Sorular
### Aspose.Tasks for Java nasıl indirilir?
Kütüphaneyi indirmek için [bu linki](https://releases.aspose.com/tasks/java/) ziyaret edin.

### Aspose.Tasks belgelerini nerede bulabilirim?
Belgeleri [burada](https://reference.aspose.com/tasks/java/) inceleyin.

### Ücretsiz deneme sürümü var mı?
Evet, ücretsiz deneme sürümüne [buradan](https://releases.aspose.com/) ulaşabilirsiniz.

### Aspose.Tasks için destek nasıl alabilirim?
Destek için [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) topluluğuna katılın.

### Aspose.Tasks için lisans satın alabilir miyim?
Evet, lisansı [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

Ek Soru&Cevap

**Q:** Mevcut Microsoft Project dosyalarını okumak için Aspose.Tasks'i kullanabilir miyim?  
**A:** Kesinlikle. `Project` sınıfı `.mpp` ve `.xml` dosyalarını doğrudan yükleyebilir.

**Q:** Kütüphane bir proje için birden fazla takvimi destekliyor mu?  
**A:** Evet. İhtiyacınız kadar `Calendar` nesnesi oluşturabilir ve her birini farklı görevlere atayabilirsiniz.

## Sonuç
Tebrikler! **add task to project** nasıl yapılacağını, özel bir takvim oluşturmayı ve bunları Aspose.Tasks for Java ile birleştirmeyi başarıyla öğrendiniz. Bu güçlü kombinasyon, sağlam ve takvim‑bilincine sahip uygulamaları hızlı bir şekilde oluşturmanızı sağlar.

---

**Son Güncelleme:** 2026-02-28  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---