---
date: 2026-07-14
description: Bu adım adım rehberde, Java'da kaynak atamasını nasıl durduracağınızı,
  kaynak atamalarını nasıl yöneteceğinizi ve Aspose.Tasks for Java kullanarak örnekleri
  nasıl görüntüleyeceğinizi öğrenin.
keywords:
- stop resource assignment java
- Aspose.Tasks Java
- resource assignment management
- project scheduling Java
lastmod: 2026-07-14
linktitle: Aspose.Tasks'te Kaynak Atamalarını Durdurma ve Devam Ettirme
og_description: Aspose.Tasks ile Java'da kaynak atamasını durdurun. Bu öğreticide,
  atamaları nasıl duraklatıp devam ettireceğiniz, tarihleri nasıl yöneteceğiniz ve
  Microsoft Project olmadan API'yi nasıl entegre edeceğiniz gösterilmektedir.
og_image_alt: Guide to stop and resume resource assignments in Aspose.Tasks for Java
og_title: Java'da Kaynak Atamasını Durdurma – Aspose.Tasks Rehberi
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to stop resource assignment java, manage resource assignments,
    and view examples using Aspose.Tasks for Java in this step‑by‑step guide.
  headline: How to Stop Resource Assignment Java – Resume with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.
    question: How do I programmatically set a stop date for an assignment?
  - answer: The API does not enforce chronological order; however, the scheduler will
      treat the assignment as active only after the later of the two dates, so you
      should validate dates yourself.
    question: What happens if the resume date is earlier than the stop date?
  - answer: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP)
      != null`.
    question: Can I filter assignments to only those that have a stop date set?
  - answer: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save
      the project.
    question: Is it possible to remove a stop date once set?
  - answer: Absolutely. The `Asn` enum provides constants for all assignment fields,
      such as `Asn.START`, `Asn.FINISH`, etc.
    question: Does Aspose.Tasks support other date‑related fields like start, finish,
      or actual start?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- stop resource assignment
- Aspose.Tasks
- Java project scheduling
- resource management
title: Java'da Kaynak Atamasını Durdurma – Aspose.Tasks ile Devam Ettirme
url: /tr/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da Kaynak Atamasını Durdurmak – Aspose.Tasks ile Yeniden Başlatma

## Giriş
Bu öğreticide **Java'da kaynak atamasını durdurma** öğrenecek ve daha sonra Aspose.Tasks for Java kullanarak yeniden başlatacaksınız. Aspose.Tasks, Microsoft Project dosyalarını okumanıza ve yazmanıza, takvimleri değiştirmenize ve kaynak atamalarını kontrol etmenize olanak tanıyan sağlam bir Java API'sidir — Microsoft Project'in yüklü olmasına gerek kalmadan. Her adımı adım adım inceleyecek, her satırın neden önemli olduğunu açıklayacak ve gerçek dünya proje planlarına uygulayabileceğiniz pratik ipuçları paylaşacağız.

## Hızlı Yanıtlar
- **“stop assignment” ne anlama geliyor?** Belirli bir durdurma tarihinden itibaren bir kaynak atamasını geçici olarak pasif işaretler.  
- **Aynı atamayı daha sonra yeniden başlatabilir miyim?** Evet, aynı atamaya bir yeniden başlatma tarihi belirleyerek.  
- **Bu API'yi kullanmak için Microsoft Project gerekir mi?** Hayır, Aspose.Tasks Microsoft Project'ten bağımsız çalışır.  
- **Hangi Java sürümü gereklidir?** Java 8 veya üzeri önerilir.  
- **Kütüphaneyi nereden indirebilirim?** Resmi Aspose.Tasks Java indirme sayfasından.

## Java'da kaynak atamasını nasıl durdurulur?
Projenizi yükleyin, hedef `ResourceAssignment` öğesini bulun, `STOP` tarihini ayarlayın, isteğe bağlı olarak bir `RESUME` tarihi belirleyin ve ardından dosyayı kaydedin. Bu sıralama, belirtilen süre boyunca işi duraklatır ve yeniden başlatma tarihinden sonra otomatik olarak yeniden etkinleştirir, manuel dosya düzenlemelerine gerek kalmadan kaynak takvimleri üzerinde kesin kontrol sağlar.

## Aspose.Tasks bağlamında “atamayı durdurma” nedir?
Bir atamayı durdurmak, zamanlayıcıya **stop date** tarihinden sonra bir kaynağa tahsis edilen işi **resume date** tarihine (varsa) kadar yok saymasını söyler. Bu, tatilleri, ekipman arızalarını veya bir kaynağın aktif kabul edilmemesi gereken herhangi bir dönemi yönetmek için faydalıdır.

## Kaynak atamalarını yönetmek için neden Aspose.Tasks kullanmalı?
Aspose.Tasks, atama tarihlerini programlı olarak kontrol etmenizi sağlar, manuel düzenlemeleri ortadan kaldırır ve hata riskini azaltır. **50+ giriş ve çıkış formatını** destekler ve **10.000'e kadar görev** içeren projeleri işleyebilir; tüm dosyayı belleğe yüklemek yerine verileri akış halinde işlediği için bellek kullanımı 200 MB'nin altında kalır. API, Java'yı destekleyen herhangi bir işletim sisteminde çalışır ve size çapraz platform esnekliği sunar.

## Önkoşullar
- Java Development Kit (JDK) 8 veya daha yeni bir sürüm yüklü.  
- Aspose.Tasks for Java kütüphanesi indirildi. Kütüphaneyi [buradan](https://releases.aspose.com/tasks/java/) indirebilirsiniz.  
- Java programlamaya temel bir anlayış.

## Paketleri İçe Aktar
`Project`, `ResourceAssignment` ve `Asn` sınıfları `com.aspose.tasks` ad alanında bulunur. Bu sınıfları kaynak dosyanızın en üst kısmına içe aktarın:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Adım 1: Proje Dosyasını Yükle
`Project` sınıfı, Aspose.Tasks'in bellek içinde tek bir Microsoft Project dosyasını temsil eden üst‑seviye nesnesidir. Bir örnek oluşturmak dosyayı yükler ve görevlere, kaynaklara ve atamalara erişim sağlar.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

## Adım 2: Kaynak Atamalarını Döngüyle İşle
`ResourceAssignment` nesneleri tüm atama‑ile ilgili alanları ortaya çıkarır. Yer tutucu tarihleri filtrelemek için bir **minimum tarih** ayarlarız ve ardından her atamayı döngüyle işleriz. Bu desen, inceleme veya değiştirme için standart *resource assignment example* örneğidir.

```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

## Adım 3: Durdurma ve Yeniden Başlatma Tarihlerini Kontrol Et
Bu blokta her atama için `STOP` ve `RESUME` alanlarını inceleriz. Bir tarih `minDate`'imizden önceyse, ayarlanmamış olarak (`"NA"`) kabul ederiz; aksi takdirde gerçek tarihi yazdırırız. Bu mantık, **manage resource assignments** doğru bir şekilde yönetmek için gereklidir.

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

## Yaygın Sorunlar ve Çözümler
- **Null tarihleri** – `ra.get(Asn.STOP)` `null` döndürebilir. `.before(minDate)` çağırmadan önce null kontrolü ekleyerek buna karşı önlem alın.  
- **Yanlış dosya yolu** – `dataDir`'in işletim sisteminize uygun bir yol ayırıcı (`/` veya `\\`) ile bittiğinden emin olun.  
- **Sürüm uyumsuzluğu** – Eksik enum değerlerinden kaçınmak için en son Aspose.Tasks for Java sürümünü kullanın.

## Sık Sorulan Sorular

**S: Bir atama için programlı olarak bir durdurma tarihi nasıl ayarlanır?**  
**C:** `ra.set(Asn.STOP, yourDateObject);` ifadesini kullanın; burada `yourDateObject` bir `java.util.Date` nesnesidir.

**S: Yeniden başlatma tarihi durdurma tarihinden daha erken olursa ne olur?**  
**C:** API kronolojik sıralamayı zorlamaz; ancak zamanlayıcı, iki tarihten daha sonraki tarih geçtikten sonra atamayı aktif olarak kabul eder, bu yüzden tarihleri kendiniz doğrulamalısınız.

**S: Sadece durdurma tarihi ayarlanmış atamaları filtreleyebilir miyim?**  
**C:** Evet, `prj.getResourceAssignments()` üzerinden döngü yapın ve `ra.get(Asn.STOP) != null` kontrol edin.

**S: Bir kez ayarlanmış durdurma tarihini kaldırmak mümkün mü?**  
**C:** Durdurma tarihini `null` olarak `ra.set(Asn.STOP, null);` ile ayarlayın ve ardından projeyi kaydedin.

**S: Aspose.Tasks, başlangıç, bitiş veya gerçek başlangıç gibi diğer tarih‑ile ilgili alanları destekliyor mu?**  
**C:** Kesinlikle. `Asn` enumu, `Asn.START`, `Asn.FINISH` gibi tüm atama alanları için sabitler sunar.

## Sonuç
Bu adımları izleyerek artık **Java'da kaynak atamasını durdurma** yöntemini biliyor, durdurma/yeniden başlatma tarihlerini inceleyebiliyor ve gerektiğinde atamayı yeniden başlatabiliyorsunuz. Bu özellik, özellikle kaynak tatilleri veya ekipman arızaları gibi senaryolarda **kaynak atamalarını** daha hassas bir şekilde yönetmenizi sağlar. Örneği tarihleri güncellemek, raporlar oluşturmak veya kendi zamanlama mantığınızla bütünleştirmek için genişletmekten çekinmeyin.

**Son Güncelleme:** 2026-07-14  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose

## İlgili Eğitimler

- [Aspose.Tasks'te Kaynak Atamaları Oluşturma](/tasks/java/resource-assignments/create-resource-assignments/)
- [Aspose.Tasks ile Maliyet Varyansını Hesaplama ve Atama Maliyetlerini Yönetme](/tasks/java/resource-assignments/assignment-cost/)
- [Aspose.Tasks'te Kaynak Atamalarına Not Ekleme](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}