---
date: 2026-02-26
description: Aspose.Tasks for Java'da görevi devam ettirmeyi ve durdurmayı öğrenin,
  tarih bazlı görev filtreleme ile kesin proje kontrolü sağlayın.
linktitle: How to Resume Task and Stop Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Görevi Yeniden Başlatma ve Görevi Durdurma
url: /tr/java/task-properties/stop-resume-task/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Görevi Yeniden Başlatma ve Durdurma

## Introduction
Java‑tabanlı bir proje yönetimi çözümü geliştiriyorsanız, bir görevi geçici olarak **durdurmanız** ve daha sonra **devam ettirmeniz** sıkça gerekebilir. Aspose.Tasks for Java, görevleri durdurma ve yeniden başlatma için yerleşik özellikler sunarak bunu kolaylaştırır. Bu öğreticide **görevi nasıl yeniden başlatacağınızı** ve **görevi nasıl durduracağınızı** programlı olarak öğrenecek, ayrıca **tarihe göre görevleri filtreleme** yöntemini görerek takviminizde yalnızca ilgili öğelerle çalışabileceksiniz.

## Quick Answers
- **“stop” bir görev için ne anlama geliyor?** Bir durdurma tarihi ayarlar, bu tarihten sonra çalışmayı duraklatır.  
- **Durdurulmuş bir görevi nasıl yeniden başlatırım?** Durdurma tarihinden daha sonraki bir yeniden başlatma tarihi atayarak.  
- **İşlemi bir tarih aralığıyla sınırlayabilir miyim?** Evet – görevleri filtrelemek için bir minimum tarih kullanın.  
- **Hangi kütüphane sürümü gerekiyor?** Aspose.Tasks for Java’nın herhangi bir güncel sürümü (API stabil kalmıştır).  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme yeterlidir; üretim için lisans gereklidir.

## What is “how to resume task” in Aspose.Tasks?
Bir görevi yeniden başlatmak, `Task` nesnesine bir **RESUME** tarihi sağlamaktır. Proje motoru takvimi işlerken, çalışma o tarihten itibaren devam eder. Bu, kaynak bulunabilirliğinin kesintisi veya dış bağımlılıklar gibi duraklamaları yönetmek için özellikle faydalıdır.

## Why use the stop/resume feature?
- **Zaman çizelgeleri üzerinde kontrol:** Görevi silmeden çalışmayı duraklatın.  
- **Doğru raporlama:** Gantt şemalarında gerçekçi başlangıç/bitiş tarihleri gösterin.  
- **Kolay otomasyon:** Tarih filtreleriyle birden çok görevi aynı anda güncelleyin.

## Prerequisites
Başlamadan önce şunların olduğundan emin olun:

- Java temellerine sağlam bir hakimiyet.  
- Makinenizde JDK kurulu.  
- Projenize eklenmiş Aspose.Tasks for Java kütüphanesi (indirmek için [buraya](https://releases.aspose.com/tasks/java/) tıklayın).  

## Import Packages
İlk olarak, projeler ve görevlerle çalışabilmek için gerekli sınıfları içe aktarın.

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```

## Step 1: Initialize the Project and Collector
MPP dosyanıza işaret eden bir `Project` örneği oluşturun ve hiyerarşideki tüm görevleri toplamak için bir `ChildTasksCollector` ayarlayın.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

## Step 2: Define a Minimum Date for Filtering
Yalnızca anlamlı durdurma veya yeniden başlatma tarihleri olan görevlerle çalışmak istiyorsanız bir **minimum tarih** tanımlayın. Bu, *tarihe göre görevleri filtreleme* tekniğinin temelidir.

```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```

## Step 3: Iterate, Check, and Display Stop/Resume Values
Şimdi toplanan görevler üzerinde döngü kurun, **görevi durdurma** mantığını uygulayın ve tarihleri yazdırın. Kod ayrıca `RESUME` özelliğini okuyarak **görevi yeniden başlatma** yöntemini gösterir.

```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```

> **Pro tip:** `System.out.println` çağrılarını kendi mantığınızla (ör. tarihleri güncelleme, dosyaya loglama veya görev nesnelerini değiştirme) değiştirerek görevleri gerçekten *durdurabilir* veya *yeniden başlatabilirsiniz*.

## Common Issues and Solutions
| Issue | Cause | Fix |
|-------|-------|-----|
| `NullPointerException` on `tsk.get(Tsk.STOP)` | Görevin durdurma tarihi ayarlanmamış. | `null` kontrolü yapın ve `.before(minDate)` çağrısından önce kontrol edin. |
| Dates appear as `NA` even after setting | Minimum tarih çok yeni. | Daha eski bir `minDate` kullanın veya filtreyi kaldırın. |
| Changes not reflected in the saved MPP | Değişikliklerden sonra proje kaydedilmemiş. | Görevleri güncelledikten sonra `project.save("output.mpp");` çağırın. |

## Frequently Asked Questions

### Is Aspose.Tasks for Java suitable for large‑scale projects?
Absolutely! Aspose.Tasks for Java is designed to handle projects of varying sizes, ensuring efficiency and reliability.

### Can I customize the date for stopping and resuming tasks?
Yes, the provided example allows flexibility in setting the minimum date according to your project requirements.

### Where can I find additional support for Aspose.Tasks for Java?
Visit the [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) for community support and discussions.

### Is there a free trial available for Aspose.Tasks for Java?
Yes, you can access the [free trial](https://releases.aspose.com/) to explore the features before making a purchase.

### How can I obtain a temporary license for Aspose.Tasks for Java?
You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/) for testing purposes.

**Additional Q&A**

**Q: How do I actually set a new stop date for a task?**  
A: Use `tsk.set(Tsk.STOP, new Date(...));` and then save the project.

**Q: Can I filter tasks by a specific range instead of just a minimum date?**  
A: Yes—compare both `before` and `after` against your start and end dates.

**Q: Does the API automatically recalculate the schedule after changing stop/resume dates?**  
A: After modifying dates, call `project.calculateCriticalPath();` to refresh the schedule.

## Conclusion
In this guide we covered **how to resume task** and **how to stop task** using Aspose.Tasks for Java, along with a practical method to **filter tasks by date**. By integrating these snippets into your application, you gain fine‑grained control over project timelines and can automate schedule adjustments with confidence.

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}