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

## Giriiş
Bu öğreticide **atamayı nasıl durduracağınızı** ve daha sonra Aspose.Tasks for Java'yı kullanarak nasıl yeniden başlatacağınızı keşfedeceksiniz. Aspose.Tasks, projenin Java formatlarında okunabilir, Microsoft Project lisanslarında manipüle edilebilir ve Microsoft Project yüklü olmadan kaynak atamalarını yönetebilen güçlü bir Java API'sidir. Her adım adım adım inceleyecek, bilgilerinin neden önemli olduğunu açıklayacak ve gerçek dünya projelerinde uygulayabileceğiniz pratik ipuçları sunacağız.

## Hızlı Yanıtlar
- **“Atamayı durdurma” ne anlama gelir?** Bir kaynak atamasından itibaren bir saklamayı geçici olarak pasif işaretler.
- **Aynı atamayı daha sonra yeniden başlatabilir miyim?** Evet, aynı üzerinde bir yeniden başlatma tarihini ayarlayarak.
- **Bu API'yi kullanmak için Microsoft Project gerekir mi?** Hayır, Aspose.Tasks Microsoft Project'ten bağımsız çalışır.
- **Hangi Java sürümü gereklidir?** Java8 veya üzeri önerilir.
- **Kütüphaneyi Nereden indirebilirim?** Resmi Aspose.Tasks Java indirme sayfasının.

## Aspose.Tasks bağlamında "ödeme nasıl durdurulur" nedir?
Bir atamayı verir, planlayıcıya **durdurma tarihi** sonrasındaki işi **yeniden başlatma tarihi** (varsa) gelene kadar yok saymasını söyler. Bu, tatiller, ekipman arızaları veya bir kaynağın aktif olmaması, herhangi bir dönem için faydalıdır.

## Kaynak atamalarını yönetmek için neden Aspose.Tasks'ı kullanmalısınız?
- **Microsoft Project gerekmez** – .mpp dosyalarıyla doğrudan dağıtılır.
- **Tarihler üzerinde tam kontrol** – durdurma tarihi, yeniden başlatma tarihi gibi değerleri programatik olarak kontrol edip ayarlayabilirsiniz.
- **Çapraz platformu** – Java'yı destekleyen herhangi bir işlem işlemi çalışır.
- **Zengin API** – *kaynak atama örneği* örneğini dağıtmak özel raporlamalar için genişletebilirsiniz.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Sisteminizde yüklü Java Development Kit (JDK).
- Aspose.Tasks for Java kütüphanesi indirilmiştir. Kütüphaneyi [buradan](https://releases.aspose.com/tasks/java/) indirebilirsiniz.
- Java programlamaya temel bir anlayış.

## Paketleri İçe Aktar
İlk olarak, gerekli paketleri Java projemize ekleyelim:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Adım 1: Proje Dosyasını Yükleyin
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

Burada **project file Java** formatındaki (`.mpp`) dosyayı okuyup tüm proje verilerine, özellikle kaynak atamalarına erişim sağlayan bir `Project` nesnesi oluşturuyoruz.

## Adım 2: Kaynak Atamaları Üzerinde Yineleme Yapın
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

Yer tutucu tarihleri filtrelemek için bir **minimum tarih** belirliyoruz ve ardından her atamayı döngüye alıyoruz. Bu, atamaları incelemek veya değiştirmek istediğinizde kullanılan tipik *resource assignment example* desenidir.

## Adım 3: Durdurma ve Devam Etme Tarihlerini Kontrol Edin
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

## Yaygın Sorunlar ve Çözümler
- **Null bağlı** – `ra.get(Asn.STOP)` `null` dönebilir. `.before(minDate)` günün öncesindeki null kontrolünü ekleyin.
- **Yanlış dosya yolu** – `dataDir`'in işletim sisteminize uygun bir yol ayırıcı (`/` veya `\\`) ile bittiğinden emin olun.
- **Sürüm uyumsuzluğu** – Eksik enum değerlerinden fiyatları için en yeni Aspose.Tasks for Java yazılımını kullanın.

## Sıkça Sorulan Sorular

**S: Atama için programlı olarak bir durdurma tarihi nasıl belirlenir?**
C: `ra.set(Asn.STOP, yourDateObject);` birimini kullanın; `yourDateObject` bir `java.util.Date` nesnesidir.

**S: Yeniden başlatma tarihini kaydetmeden önce olursa ne olur?**
C: API kronolojik sıralamayı zorlamaz; Ancak planlayıcı, iki devamlılığı daha sonraki tarih geldiğinde atamayı aktif olarak kabul eder, bu nedenle seçtiğinizi kendiniz doğrulamalısınız.

**S: Yalnızca tarihi ayarlanmış atamaları filtreleyebilir miyim?**
C: Evet, `prj.getResourceAssignments()` üzerinden dönerken `ra.get(Asn.STOP) != null` kontrolünü yapın.

**S: Bir durdurma tarihi bir kez ayarlandıktan sonra kaldırılabilir mi?**
C: `ra.set(Asn.STOP, null);` ile durmadan `null` görüntüdeki projeyi kaydedebilirsiniz.

**S: Aspose.Tasks, başlangıç, bitiş veya gerçek başlangıçlar gibi diğer tarihlerdeki sürücüler mi?**
C: elbette. `Asn` enum'ı `Asn.START`, `Asn.FINISH` gibi tüm atama alanları için sabitler sunar.

## Çözüm
Bu adımları izleyerek **atamayı nasıl durduracağınızı**, durdurma/yeniden başlatma tarihlerini nasıl inceleyeceğinizi ve atamalarınızı nasıl yeniden başlatmanızı sağlayacaksınız. Bu özellik, özellikle kaynak tatilleri veya ekipman arızaları gibi senaryolarda **kaynak atamalarını yönetme** sürecin daha hassas bir şekilde yapılmasını sağlar. Örneği isteğe bağlı güncellemek, rapor dökümü veya kendi zamanlama mantığınızla entegre etmek için genişletilmekten.

---

**Son Güncelleme:** 2026-01-10
**Şunlarla Test Edildi:** Aspose.Tasks for Java 24.12
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}