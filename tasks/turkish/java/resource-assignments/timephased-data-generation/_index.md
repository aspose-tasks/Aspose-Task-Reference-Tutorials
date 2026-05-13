---
date: 2026-01-10
description: Aspose.Tasks for Java kullanarak konturu nasıl değiştireceğinizi ve kaynak
  atamaları için zaman aşamalı veri oluşturmayı öğrenin, proje yönetimi verimliliğini
  artırın.
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Zaman Aşamalı Veriler İçin Konturu Nasıl Değiştirilir
url: /tr/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Zaman Aşamalı Verilerde Konturu Değiştirme

## Giriş
Bu öğreticide, **konturu nasıl değiştireceğinizi** bir kaynak ataması için keşfedecek ve Aspose.Tasks for Java kullanarak zaman aşamalı veri oluşturacaksınız. Zaman aşamalı veri, çalışmanın proje zaman çizelgesi üzerindeki dağılımını gösterir; böylece takvimleri ince ayarlayabilir, iş yüklerini dengeleyebilir ve veri odaklı kararlar alabilirsiniz.

## Hızlı Yanıtlar
- **Kontur nedir?** Bir iş konturu, çabanın bir görevin süresi boyunca nasıl dağıtıldığını tanımlar (ör. Düz, Kaplumbağa, Çan).  
- **Neden bir konturu değiştirirsiniz?** İş yükünü önceden yükleme veya geriden yükleme gibi gerçekçi çalışma modellerini yansıtmak için.  
- **Hangi kütüphane gereklidir?** Aspose.Tasks for Java (herhangi bir son sürüm).  
- **Lisans gerekiyor mu?** Evet, üretim kullanımı için geçerli bir Aspose.Tasks lisansı gereklidir.  
- **Sonuçları konsolda görebilir miyim?** Örnek, her zaman aşamalı segment için başlangıç tarihlerini ve değerleri yazdırır.

## “Konturu nasıl değiştiririz” nedir?
Bir konturu değiştirmek, bir `ResourceAssignment` nesnesinin `WORK_CONTOUR` özelliğini güncellemeyi ifade eder. Aspose.Tasks, zaman içinde işin nasıl tahsis edildiğini etkileyen birkaç ön tanımlı konturu (Düz, Kaplumbağa, Çan vb.) destekler.

## Zaman aşamalı veri üretmek için neden Aspose.Tasks kullanmalı?
- **Doğru raporlama:** Raporlama araçları için kesin iş dağılımını dışa aktarın.  
- **Senaryo planlaması:** Orijinal takvimi değiştirmeden farklı konturları test edin.  
- **Otomasyon:** CI boru hatlarına entegre ederek proje sağlığını otomatik olarak doğrulayın.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Java Development Kit (JDK): Sisteminizde JDK yüklü olduğundan emin olun. JDK’yı [buradan](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) indirebilir ve kurabilirsiniz.
2. Aspose.Tasks for Java Kütüphanesi: Aspose.Tasks for Java kütüphanesine ihtiyacınız var. Kütüphaneyi [web sitesinden](https://releases.aspose.com/tasks/java/) indirebilirsiniz.

## Paketleri İçe Aktarma
İlk olarak, Aspose.Tasks ile çalışmak için gerekli paketleri içe aktaralım:
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
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Adım 2: Görev ve Kaynak Atamasını Almak
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Konturu Değiştirme – Düz (Varsayılan)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Konturu Değiştirme – Kaplumbağa
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Konturu Değiştirme – Geriden Yükleme
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Konturu Değiştirme – Önceden Yükleme
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Konturu Değiştirme – Çan
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Konturu Değiştirme – Erken Zirve
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Konturu Değiştirme – Geç Zirve
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Konturu Değiştirme – Çift Zirve
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Yaygın Sorunlar ve İpuçları
- **Kontur güncellenmiyor mu?** Zaman aşamalı veriyi almadan önce `firstRA.set(Asn.WORK_CONTOUR, …)` *çağırdığınızdan* emin olun.  
- **Beklenmeyen değerler mi?** Görevin başlangıç ve bitiş tarihlerinin kaynak MPP’de doğru ayarlandığını doğrulayın.  
- **Performans ipucu:** Gereksiz dosya I/O’dan kaçınmak için birden fazla konturu dönerken aynı `Project` örneğini yeniden kullanın.

## SSS
### Aspose.Tasks'i diğer Java kütüphaneleriyle kullanabilir miyim?
Evet, Aspose.Tasks diğer Java kütüphaneleriyle entegre edilerek proje yönetimi yetenekleri artırılabilir.

### Aspose.Tasks büyük ölçekli kurumsal projeler için uygun mu?
Kesinlikle, Aspose.Tasks tüm ölçeklerdeki projeleri, büyük ölçekli kurumsal girişimler dahil, yönetebilecek şekilde tasarlanmıştır.

### Aspose.Tasks farklı proje dosya formatları için destek sağlıyor mu?
Evet, Aspose.Tasks MPP, XML ve MPX gibi çeşitli formatları destekler.

### Proje gereksinimlerime göre iş konturlarını özelleştirebilir miyim?
Evet, belirli zamanlama ihtiyaçlarınıza uygun özel iş konturları tanımlayabilirsiniz.

### Aspose.Tasks ile ilgili yardım alabileceğim bir topluluk forumu var mı?
Evet, destek ve tartışmalar için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edebilirsiniz.

---

**Son Güncelleme:** 2026-01-10  
**Test Edilen Versiyon:** Aspose.Tasks for Java (latest release)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}