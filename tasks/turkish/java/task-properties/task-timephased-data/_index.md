---
date: 2026-02-28
description: Aspose.Tasks for Java'ı kullanarak görev zaman aşamalı verilerini yönetmeyi
  öğrenin, kütüphaneyi indirin, ücretsiz deneyin ve proje takibini kolaylaştırın.
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'i Kullanarak Görev Zaman Aşamalı Verilerini Yönetme (Java)
url: /tr/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'i Görev Zaman Aşamalı Verileri İçin Nasıl Kullanılır

## Giriş
Eğer **Aspose'i nasıl kullanacağınızı** öğrenerek proje takviminizi sıkı bir şekilde kontrol etmek istiyorsanız, doğru yerdesiniz. Görev zaman aşamalı verilerinin hassas takibi başarılı proje yönetiminin temel taşlarından biridir ve Aspose.Tasks for Java bu süreci otomatikleştirmeniz için gereken araçları sunar. Bu öğreticide, Aspose.Tasks'i kullanarak bir proje oluşturmayı, kaynakları atamayı, temel hatları (baseline) ayarlamayı ve sonunda zaman aşamalı verileri alıp görüntülemeyi gösteren eksiksiz, uçtan uca bir örnek üzerinden ilerleyeceğiz.

## Hızlı Yanıtlar
- **“timephased data” ne anlama geliyor?** Proje zaman çizelgesi boyunca iş, maliyet veya kalan işi gösteren, zaman aralıklarına (gün, hafta, ay) bölünmüş verilerdir.  
- **Bu yeteneği hangi kütüphane sağlar?** Aspose.Tasks for Java.  
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim için lisans gereklidir.  
- **Hangi Java sürümü gereklidir?** Java 8 veya üzeri.  
- **Sonuçları Excel'e aktarabilir miyim?** Evet – `TimephasedData` koleksiyonunu döngüyle gezebilir ve değerleri ihtiyacınız olan herhangi bir formata yazabilirsiniz.

## Görev Zaman Aşamalı Verileri Nedir?
Görev zaman aşamalı verileri, proje takvimindeki her zaman diliminde bir görev için planlanan iş (veya maliyet) miktarını temsil eder. İşin nasıl dağıtıldığını görmenizi, aşırı tahsisatı fark etmenizi ve planlanan ile gerçekleşen ilerlemeyi karşılaştırmanızı sağlar.

## Zaman Aşamalı Verileri Yönetmek İçin Aspose.Tasks'i Neden Kullanmalısınız?
- **Tam kontrol** – Microsoft Project'i açmadan programatik olarak zaman aşamalı bilgileri oluşturabilir, değiştirebilir ve sorgulayabilirsiniz.  
- **Çapraz platform** – Java'yı destekleyen herhangi bir işletim sisteminde çalışır.  
- **COM bağımlılığı yok** – sunucu tarafı otomasyon için idealdir.  
- **Zengin API** – temel hatları (baseline), iş konturlarını ve özel alanları kutudan çıkar çıkmaz destekler.

## Önkoşullar
Koda başlamadan önce şunların olduğundan emin olun:

- **Java Geliştirme Ortamı** – JDK 8+ yüklü ve `JAVA_HOME` yapılandırılmış.  
- **Aspose.Tasks for Java Kütüphanesi** – Aspose.Tasks kütüphanesini projenize indirin ve ekleyin. Kütüphaneyi [burada](https://releases.aspose.com/tasks/java/) bulabilirsiniz.  
- **Belge Dizini** – Örnek proje dosyasının (`project.xml`) okunup yazılacağı makinenizdeki bir klasör.

## Paketleri İçe Aktarma
Java projenizde, gerekli Aspose.Tasks sınıflarını içe aktarın:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```

## Adım 1: Proje Başlangıç Tarihini Ayarla
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Açıklama:* Bir `Project` örneği oluşturur, `Calendar`'ı istenen başlangıç tarihine başlatır ve bunu projenin `START_DATE` özelliğine atar.

## Adım 2: Görev ve Kaynağı Tanımla
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Açıklama:* Kök görev altında **Task** adlı yeni bir görev eklenir. Ayrıca **Rsc** adlı bir kaynak oluşturur ve standart ile fazla mesai ücretlerini ayarlarız.

## Adım 3: Görev Süresini Ayarla
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Açıklama:* Görev **6 gün** süresiyle planlanır.

## Adım 4: Kaynağı Göreve Ata
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Açıklama:* Önceden tanımlanan kaynak, bir `ResourceAssignment` aracılığıyla göreve bağlanır.

## Adım 5: Kaynak Atamasını Yapılandır
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Açıklama:* Atamanın durdurma ve devam tarihlerini (yer tutucu bir değer kullanarak) ayarlarız ve **Back‑Loaded** iş konturunu uygularız; bu, daha fazla işi atamanın sonuna doğru kaydırır.

## Adım 6: Temel Hattı (Baseline) Ayarla
```java
project.setBaseline(BaselineType.Baseline);
```
*Açıklama:* Bir temel hat yakalamak, daha sonra planlanan değerleri gerçekleşenlerle karşılaştırmanıza olanak tanır.

## Adım 7: Görev Tamamlanmasını Güncelle
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Açıklama:* Görev **%50 tamamlanmış** olarak işaretlenir; bu, kalan iş hesaplamalarını etkiler.

## Adım 8: Zaman Aşamalı Verileri Al
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Açıklama:* Bu çağrı, atama için **kalan işi** proje zaman aralıklarına göre bölünmüş olarak alır.

## Adım 9: Zaman Aşamalı Verileri Görüntüle
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Açıklama:* Sadece zaman aşamalı giriş sayısını ve ilk girişin değerini yazdırırız. Gerçek bir senaryoda listeyi döngüyle gezerek verileri bir rapora veya UI'ye aktarırdınız.

## Yaygın Sorunlar ve Çözümler
- **`getTimephasedData` üzerinde NullPointerException** – Yöntemi çağırmadan önce atamanın `START` ve `FINISH` tarihlerinin ayarlandığından emin olun.  
- **Yanlış iş konturu** – Seçtiğiniz `WorkContourType`'ın planlama stratejinize uygun olduğunu doğrulayın; `BackLoaded` sadece birkaç seçenekten biridir.  
- **Temel hat değişiklikleri yansıtmıyor** – Görevleri, kaynakları ve atamaları tanımladıktan *sonra* `project.setBaseline` metodunu çağırmayı unutmayın.

## Sıkça Sorulan Sorular
### S: Aspose.Tasks for Java'ı herhangi bir Java projesinde kullanabilir miyim?
C: Evet, Aspose.Tasks for Java herhangi bir Java tabanlı proje ile uyumludur.

### S: Aspose.Tasks for Java için ek destek nereden bulabilirim?
C: Destek ve tartışmalar için [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) adresini ziyaret edin.

### S: Aspose.Tasks for Java için ücretsiz deneme mevcut mu?
C: Evet, ücretsiz denemeyi [burada](https://releases.aspose.com/) keşfedebilirsiniz.

### S: Aspose.Tasks for Java için geçici lisans nasıl alabilirim?
C: Geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

### S: Aspose.Tasks for Java'ı nereden satın alabilirim?
C: Aspose.Tasks for Java'ı [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

---

**Son Güncelleme:** 2026-02-28  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12 (yazım sırasında en son)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}