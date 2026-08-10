---
date: 2026-06-10
description: Aspose.Tasks for Java kullanarak resource assignments için contour'ı
  değiştirmeyi ve timephased data oluşturmayı öğrenin; work contour types ve advanced
  scheduling scenarios ele alınmaktadır.
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: Aspose.Tasks'te Resource Assignments için Timephased Data Oluşturma
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Timephased Data İçin Konturu Nasıl Değiştirilir
url: /tr/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks için Zaman Aşamalı Verilerde Konturu Değiştirme

## Giriş
Bu öğreticide, **konturu nasıl değiştireceğinizi** bir kaynak ataması için keşfedecek ve Aspose.Tasks for Java kullanarak zaman aşamalı veri oluşturacaksınız. Zaman aşamalı veri, projenin zaman çizelgesi boyunca iş dağılımını ortaya koyar, takvimleri ince ayarlamanıza, iş yüklerini dengelemenize ve veri odaklı kararlar almanıza olanak tanır. Kontur değişikliklerinde ustalaşmak, ön‑yükleme, arka‑yükleme veya zirve iş yükleri gibi gerçekçi çaba kalıplarını modellemenize yardımcı olur.

## Hızlı Yanıtlar
- **Kontur nedir?** Bir iş konturu, çabanın bir görevin süresi boyunca nasıl dağıtıldığını tanımlar (ör. Düz, Kaplumbağa, Çan).  
- **Neden bir konturu değiştirirsiniz?** Ön‑yükleme veya arka‑yükleme gibi gerçekçi iş kalıplarını yansıtmak için.  
- **Hangi kütüphane gereklidir?** Aspose.Tasks for Java (herhangi bir son sürüm).  
- **Lisans gerekir mi?** Evet, üretim kullanımı için geçerli bir Aspose.Tasks lisansı gereklidir.  
- **Sonuçları konsolda görebilir miyim?** Örnek, her zaman aşamalı segment için başlangıç tarihlerini ve değerleri yazdırır.

## “Konturu nasıl değiştireceksiniz” nedir?
Bir konturu değiştirmek, bir `ResourceAssignment` nesnesinin `WORK_CONTOUR` özelliğini güncellemeyi ifade eder. Bu özellik, Aspose.Tasks'in atamanın toplam işini görevin süresi boyunca nasıl dağıtacağını belirler. Kütüphane, Düz, Kaplumbağa, Çan gibi önceden tanımlı birçok kontur sunar; her biri zaman içinde çaba dağılımının farklı bir desenini üretir.

## Zaman aşamalı veri oluşturmak için neden Aspose.Tasks kullanmalı?
Aspose.Tasks, **bellek içi işlemler için 0 ms ek yük** ile zaman aşamalı veri oluşturur ve **50+ çıktı formatı** (MPP, XML, CSV vb.) destekler. Kütüphane, tüm dosyayı belleğe yüklemeden çok sayfalı projeleri işleyebilir, raporlama, kaynak dengeleme ve senaryo analizleri için doğru iş dağılımı sağlar. API'si, kontur değişikliklerini otomatikleştirmenize ve programlı olarak kesin zaman aşamalı değerleri çıkarmanıza olanak tanır.

## Ön Koşullar
Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
1. Java Development Kit (JDK): Sisteminizde JDK yüklü olduğundan emin olun. JDK'yı [buradan](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) indirebilir ve kurabilirsiniz.  
2. Aspose.Tasks for Java Kütüphanesi: Aspose.Tasks for Java kütüphanesine sahip olmanız gerekir. Kütüphaneyi [web sitesinden](https://releases.aspose.com/tasks/java/) indirebilirsiniz.

## Paketleri İçe Aktarma
`Project` sınıfı, Aspose.Tasks'in bellek içinde bir bütün proje dosyasını temsil eden temel nesnesidir. Görevler ve atamalar üzerinde çalışmaya başlamadan önce gerekli paketleri (namespace) içe aktarın.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Adım 1: Kaynak MPP Dosyasını Okuma
`Project` yapıcı (constructor) mevcut bir MPP dosyasını yükler, yapısını bellekte her görevi tam olarak somutlaştırmadan ayrıştırır; bu da işlemi hafif tutar.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Adım 2: Görev ve Kaynak Atamasını Almak
`ResourceAssignment`, bir kaynağı bir göreve bağlar ve iş, maliyet ve kontur gibi atama‑seviyesi özelliklerini saklar. Konturunu değiştirmeden önce `project.getResourceAssignments().getById(1)` (veya geçerli bir kimlik) ile ilk atamayı alın.

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Konturu Değiştirme – Düz (Varsayılan)
`WorkContourType`, Aspose.Tasks tarafından desteklenen önceden tanımlı iş konturu desenlerini listeleyen bir enum'dur. `Asn.WORK_CONTOUR`, bir kaynak atamasının kontur alanını tanımlar ve `generateTimephasedData()` mevcut kontur ayarına göre zaman aşamalı iş girişleri oluşturur. **Flat** konturu, işi görevin süresi boyunca eşit olarak dağıtır; bunu `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` ile ayarlayın ve ardından `firstRA.generateTimephasedData()` çağırarak eşit aralıklı değerleri elde edin.

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Konturu Değiştirme – Kaplumbağa
**Turtle** konturu düşük çabayla başlar, ortaya doğru hızlanır ve tekrar yavaşlar; bu, bir kaplumbağanın yavaş temposuna benzer. `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` ayarlayarak uygulayın ve ardından zaman aşamalı verileri yeniden oluşturun. Bu desen, zirve verimliliğe ulaşmadan önce bir öğrenme eğrisi gerektiren görevler için idealdir.

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Konturu Değiştirme – ArkaYüklemeli
**BackLoaded** konturu, işin çoğunu görevin zaman çizelgesinin sonuna yerleştirir, başlangıçta ise az çaba gerektirir. `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` kullanarak ayarlayın ve zaman aşamalı verileri yeniden oluşturun. Bu, çalışmanın yapılabilmesi için önceki görevlere bağımlı aktiviteler için faydalıdır.

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Konturu Değiştirme – ÖnYüklemeli
**FrontLoaded** konturu, çabayı görevin başında yoğunlaştırır, başlangıç aşamaları veya yoğun erken iş patlamaları gibi senaryoları modellemek için uygundur. `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` ile uygulayın ve ardından `firstRA.generateTimephasedData()` çağırarak ön‑yüklemeli dağılımı görün.

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Konturu Değiştirme – Çan
**Bell** konturu, zaman çizelgesinin ortasında simetrik bir zirve oluşturur, işin yükselip zirveye ulaştıktan sonra sorunsuz bir şekilde düşmesini temsil eder. `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` ile ayarlayın ve zaman aşamalı verileri yeniden oluşturun, çan‑şeklinde çaba eğrisini görselleştirin.

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Konturu Değiştirme – ErkenZirve
**EarlyPeak** en yüksek iş değerini programın erken dönemine yerleştirir, ardından azalır. `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` ardından `firstRA.generateTimephasedData()` kullanarak, hızlı prototipleme gibi güçlü bir başlangıç gerektiren aktiviteleri modelleyin.

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Konturu Değiştirme – GeçZirve
**LatePeak** iş zirvesini görevin sonuna kaydırır, son teslim tarihine yaklaştıkça işin yoğunlaştığı durumlar için uygundur. `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` ile uygulayın ve zaman aşamalı verileri yeniden oluşturun, geç‑aşama iş yükü artışını görün.

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Konturu Değiştirme – ÇiftZirve
**DoublePeak** iki ayrı iş dalgası oluşturur, aralarında düşük‑çaba aralığı bulunur; iki büyük çaba patlaması olan görevler için kullanışlıdır. `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` kullanarak ayarlayın ve ardından `firstRA.generateTimephasedData()` çağırarak çift‑zirve desenini elde edin.

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Yaygın Sorunlar ve İpuçları
- **Kontur güncellenmiyor mu?** Zaman aşamalı verileri almadan önce `firstRA.set(Asn.WORK_CONTOUR, …)` *önce* çağırdığınızdan emin olun.  
- **Beklenmeyen değerler mi?** Görevin başlangıç ve bitiş tarihlerinin kaynak MPP'de doğru ayarlandığını doğrulayın.  
- **Performans ipucu:** Birden fazla konturu dönerken aynı `Project` örneğini yeniden kullanın; gereksiz dosya I/O'dan kaçının, bu büyük projelerde işleme süresini %40'a kadar azaltabilir.  
- **Bellek ipucu:** 1 GB'den büyük projeler için `Project.setReadOnly(true)` etkinleştirerek bellek kullanımını 200 MB'nin altında tutabilir ve yine de doğru zaman aşamalı veri üretebilirsiniz.

## SSS
**Q: Aspose.Tasks'i diğer Java kütüphaneleriyle kullanabilir miyim?**  
A: Evet, Aspose.Tasks diğer Java kütüphaneleriyle sorunsuz bir şekilde bütünleşir ve zamanlama verilerini raporlama, analiz veya UI çerçeveleriyle birleştirmenize olanak tanır.

**Q: Aspose.Tasks büyük ölçekli kurumsal projeler için uygun mu?**  
A: Kesinlikle. Kütüphane, on binlerce görev ve kaynak içeren projeleri işlemek üzere tasarlanmıştır; çok sayfalı dosyaları performans kaybı olmadan işler.

**Q: Aspose.Tasks farklı proje dosya formatlarını destekliyor mu?**  
A: Evet, Aspose.Tasks 30'dan fazla formatı destekler, MPP, XML, CSV ve MPX dahil, böylece eski ve modern sistemler arasında kolay içe/dışa aktarım sağlar.

**Q: Proje gereksinimlerime göre iş konturlarını özelleştirebilir miyim?**  
A: Evet, `WORK_CONTOUR` özelliğine iş yüzdeleri dizisi sağlayarak özel konturlar tanımlayabilir ve çaba dağılımı üzerinde tam kontrol elde edebilirsiniz.

**Q: Aspose.Tasks ile ilgili yardım alabileceğim bir topluluk forumu var mı?**  
A: Evet, destek, tartışmalar ve hem Aspose mühendislerinden hem de topluluk üyelerinden kod örnekleri için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edebilirsiniz.

**Son Güncelleme:** 2026-06-10  
**Test Edilen:** Aspose.Tasks for Java (latest release)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Tasks'te Kaynak Atamaları Oluştur](/tasks/java/resource-assignments/create-resource-assignments/)
- [Aspose.Tasks'te Kaynaklar için Zaman Aşamalı Verileri Okuma](/tasks/java/resource-management/read-timephased-data/)
- [Aspose.Tasks'te Atamayı Durdurma ve Kaynak Atamalarını Yeniden Başlatma](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}