---
title: Aspose.Tasks'ta Seviyelendirme Gecikmesi Özelliklerini Yönetme
linktitle: Aspose.Tasks'ta Kaynak Atamaları için Seviyelendirme Gecikmesi Özelliklerini Yönetme
second_title: Aspose.Tasks Java API'si
description: Bu kapsamlı eğitimle Aspose.Tasks for Java'da kaynak atamaları için seviyelendirme gecikmesi özelliklerini nasıl kullanacağınızı öğrenin.
weight: 17
url: /tr/java/resource-assignments/leveling-delay-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Seviyelendirme Gecikmesi Özelliklerini Yönetme

## giriiş
Bu eğitimde Aspose.Tasks for Java'da kaynak atamaları için seviyelendirme gecikme özelliklerinin ele alınması sürecini anlatacağız. Aspose.Tasks, sisteminizde Microsoft Project'in kurulu olmasına gerek kalmadan Microsoft Project dosyalarıyla çalışmanıza olanak tanıyan güçlü bir Java kütüphanesidir.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  Java Geliştirme Kiti (JDK): Sisteminizde Java JDK'nın kurulu olduğundan emin olun. adresinden indirip kurabilirsiniz.[İnternet sitesi](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks for Java Kütüphanesi: Aspose.Tasks for Java kütüphanesini şu adresten indirin:[indirme sayfası](https://releases.aspose.com/tasks/java/).

## Paketleri İçe Aktar
Aspose.Tasks işlevlerini kullanmak için öncelikle gerekli paketleri Java projenize aktarın:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Adım 1: Proje Nesnesi Oluşturun
 Bir örnek oluştur`Project` nesne:
```java
Project prj = new Project();
```
## 2. Adım: Görev Oluşturun
Projeye bir görev ekleyin:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## 3. Adım: Görev Başlangıç Tarihini ve Süresini Ayarlayın
Görevin başlangıç tarihini ve süresini ayarlayın:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## 4. Adım: Kaynak Ekleme
Projeye bir kaynak ekleyin:
```java
Resource resource = prj.getResources().add("Resource 1");
```
## Adım 5: Kaynak Ataması Oluşturun
Görev ve kaynak için bir kaynak ataması oluşturun:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## Adım 6: Seviyelendirme Gecikmesini Ayarlayın
Atama için seviyelendirme gecikmesini ayarlayın:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## Adım 7: Sonuçları Görüntüleyin
Tesviye gecikmesini ve diğer ilgili bilgileri yazdırın:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Çözüm
Bu eğitimde Aspose.Tasks for Java'da kaynak atamaları için seviyelendirme gecikmesi özelliklerinin nasıl ele alınacağını öğrendik. Bu adımları izleyerek Java projelerinizdeki kaynak atamalarını verimli bir şekilde yönetebilirsiniz.
## SSS'ler
### S: Aspose.Tasks'ı diğer Java kütüphaneleriyle kullanabilir miyim?

C: Evet, Aspose.Tasks, proje yönetimi özelliklerini geliştirmek için diğer Java kitaplıklarıyla entegre edilebilir.

### S: Aspose.Tasks, Microsoft Project dosyalarının farklı sürümleriyle uyumlu mudur?

C: Evet, Aspose.Tasks, Microsoft Project dosyalarının çeşitli sürümlerini destekleyerek farklı ortamlar arasında uyumluluk sağlar.

### S: Aspose.Tasks için ek desteği nerede bulabilirim?

 C: Destek ve kaynakları şu adreste bulabilirsiniz:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).

### S: Satın almadan önce Aspose.Tasks'ı deneyebilir miyim?

 C: Evet, Aspose.Tasks'ın ücretsiz deneme sürümünü şu adresten edinebilirsiniz:[sürümler sayfası](https://releases.aspose.com/).

### S: Aspose.Tasks için nasıl geçici lisans alabilirim?

 C: Geçici lisans talebinde bulunabilirsiniz.[geçici lisans sayfası](https://purchase.aspose.com/temporary-license/) değerlendirme amaçlı.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
