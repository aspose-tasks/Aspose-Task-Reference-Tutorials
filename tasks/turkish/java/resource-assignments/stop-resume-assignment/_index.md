---
date: 2026-01-10
description: Bu adım adım öğreticide, Aspose.Tasks for Java’da atamayı durdurmayı,
  kaynak atamalarını yönetmeyi ve bir kaynak atama örneğini görüntülemeyi öğrenin.
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Atamayı Durdurmak ve Kaynak Atamalarını Yeniden Başlatmak
url: /tr/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Atamayı Durdurma ve Kaynak Atamalarını Yeniden Başlatma Nasıl Yapılır

## Introduction
Bu öğreticide **atamayı nasıl durduracağınızı** ve daha sonra Aspose.Tasks for Java kullanarak nasıl yeniden başlatacağınızı keşfedeceksiniz. Aspose.Tasks, proje dosyalarını Java formatlarında okuyabilen, Microsoft Project verilerini manipüle edebilen ve Microsoft Project yüklü olmadan kaynak atamalarını yönetebilen güçlü bir Java API'sidir. Her adımı adım adım inceleyecek, her satırın neden önemli olduğunu açıklayacak ve gerçek dünya projelerinde uygulayabileceğiniz pratik ipuçları sunacağız.

## Quick Answers
- **“Atamayı durdurma” ne anlama gelir?** Belirli bir durdurma tarihinden itibaren bir kaynak atamasını geçici olarak pasif işaretler.  
- **Aynı atamayı daha sonra yeniden başlatabilir miyim?** Evet, aynı atama üzerinde bir yeniden başlatma tarihi ayarlayarak.  
- **Bu API'yi kullanmak için Microsoft Project gerekir mi?** Hayır, Aspose.Tasks Microsoft Project'ten bağımsız çalışır.  
- **Hangi Java sürümü gereklidir?** Java 8 veya üzeri önerilir.  
- **Kütüphaneyi nereden indirebilirim?** Resmi Aspose.Tasks Java indirme sayfasından.

## What is “how to stop assignment” in the context of Aspose.Tasks?
Bir atamayı durdurmak, planlayıcıya **durdurma tarihi** sonrasındaki işi **yeniden başlatma tarihi** (varsa) gelene kadar yok saymasını söyler. Bu, tatiller, ekipman arızaları veya bir kaynağın aktif olmaması gereken herhangi bir dönem için faydalıdır.

## Why use Aspose.Tasks to manage resource assignments?
- **Microsoft Project gerekmez** – .mpp dosyalarıyla doğrudan çalışın.  
- **Tarihler üzerinde tam kontrol** – durdurma tarihi, yeniden başlatma tarihi gibi değerleri programatik olarak kontrol edip ayarlayabilirsiniz.  
- **Çapraz platform** – Java'yı destekleyen herhangi bir işletim sisteminde çalışır.  
- **Zengin API** – *resource assignment example* örneğini alıp özel raporlamalar için genişletebilirsiniz.

## Prerequisites
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Sisteminizde yüklü Java Development Kit (JDK).  
- Aspose.Tasks for Java kütüphanesi indirilmiş. Kütüphaneyi [buradan](https://releases.aspose.com/tasks/java/) indirebilirsiniz.  
- Java programlamaya temel bir anlayış.

## Import Packages
İlk olarak, gerekli paketleri Java projemize ekleyelim:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Step 1: Load the Project File
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

Burada **project file Java** formatındaki (`.mpp`) dosyayı okuyup tüm proje verilerine, özellikle kaynak atamalarına erişim sağlayan bir `Project` nesnesi oluşturuyoruz.

## Step 2: Iterate Through Resource Assignments
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

Yer tutucu tarihleri filtrelemek için bir **minimum tarih** belirliyoruz ve ardından her atamayı döngüye alıyoruz. Bu, atamaları incelemek veya değiştirmek istediğinizde kullanılan tipik *resource assignment example* desenidir.

## Step 3: Check Stop and Resume Dates
```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

Bu blokta her atama için **durdurma tarihini** ve **yeniden başlatma tarihini** kontrol ediyoruz. Tarih `minDate`'den önceyse ayarlanmamış (`"NA"`) olarak kabul ediyor, aksi takdirde gerçek tarihi yazdırıyoruz. Bu mantık, **manage resource assignments** işlemini doğru bir şekilde yapabilmek için kritiktir.

## Common Issues and Solutions
- **Null tarihleri** – `ra.get(Asn.STOP)` `null` dönebilir. `.before(minDate)` çağrısı öncesinde null kontrolü ekleyin.  
- **Yanlış dosya yolu** – `dataDir`'in işletim sisteminize uygun bir yol ayırıcı (`/` veya `\\`) ile bittiğinden emin olun.  
- **Sürüm uyumsuzluğu** – Eksik enum değerlerinden kaçınmak için en yeni Aspose.Tasks for Java sürümünü kullanın.

## FAQ's
### Aspose.Tasks'i Microsoft Project yüklü olmadan kullanabilir miyim?
Evet, Aspose.Tasks Microsoft Project dosyalarıyla çalışmanıza olanak tanır ve Microsoft Project'in sisteminizde yüklü olmasını gerektirmez.

### Daha fazla belgeyi nerede bulabilirim?
Detaylı belgeleri [burada](https://reference.aspose.com/tasks/java/) bulabilirsiniz.

### Ücretsiz deneme mevcut mu?
Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) alabilirsiniz.

### Sorun yaşarsam nasıl destek alabilirim?
Topluluk desteğini [buradan](https://forum.aspose.com/c/tasks/15) alabilirsiniz.

### Geçici bir lisans satın alabilir miyim?
Evet, geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) satın alabilirsiniz.

## Frequently Asked Questions

**S: Atama için programlı olarak bir durdurma tarihi nasıl ayarlanır?**  
C: `ra.set(Asn.STOP, yourDateObject);` ifadesini kullanın; `yourDateObject` bir `java.util.Date` nesnesidir.

**S: Yeniden başlatma tarihi durdurma tarihinden önce olursa ne olur?**  
C: API kronolojik sıralamayı zorlamaz; ancak planlayıcı, iki tarihten daha sonraki tarih geldiğinde atamayı aktif kabul eder, bu yüzden tarihleri kendiniz doğrulamalısınız.

**S: Sadece durdurma tarihi ayarlanmış atamaları filtreleyebilir miyim?**  
C: Evet, `prj.getResourceAssignments()` üzerinden dönerken `ra.get(Asn.STOP) != null` kontrolü yapın.

**S: Bir durdurma tarihi bir kez ayarlandıktan sonra kaldırılabilir mi?**  
C: `ra.set(Asn.STOP, null);` ile durdurma tarihini `null` yapıp projeyi kaydedebilirsiniz.

**S: Aspose.Tasks, başlangıç, bitiş veya gerçek başlangıç gibi diğer tarih alanlarını destekliyor mu?**  
C: Kesinlikle. `Asn` enum'ı `Asn.START`, `Asn.FINISH` gibi tüm atama alanları için sabitler sunar.

## Conclusion
Bu adımları izleyerek **atamayı nasıl durduracağınızı**, durdurma/yeniden başlatma tarihlerini nasıl inceleyeceğinizi ve gerektiğinde atamayı nasıl yeniden başlatacağınızı öğrendiniz. Bu özellik, özellikle kaynak tatilleri veya ekipman arızaları gibi senaryolarda **manage resource assignments** işlemini daha hassas bir şekilde yapmanızı sağlar. Örneği tarihleri güncellemek, raporlar üretmek veya kendi zamanlama mantığınızla entegre etmek için genişletmekten çekinmeyin.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}