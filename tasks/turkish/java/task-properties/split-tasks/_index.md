---
title: Aspose.Tasks'ta Görevleri Böl
linktitle: Aspose.Tasks'ta Görevleri Böl
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks ile Java'da görev yönetiminde ustalaşın! Optimize edilmiş proje zaman çizelgeleri için görevleri verimli bir şekilde nasıl böleceğinizi öğrenin. Şimdi İndirin!
weight: 29
url: /tr/java/task-properties/split-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Görevleri Böl

## giriiş
Java projenizde görev yönetimi konusunda sorun mu yaşıyorsunuz? Aspose.Tasks for Java, görevleri verimli bir şekilde bölmek ve proje yönetimi yeteneklerini geliştirmek için güçlü bir çözüm sunar. Bu eğitimde Aspose.Tasks for Java'yı kullanarak görevleri bölme sürecinde size rehberlik ederek proje zaman çizelgelerinizi ve kaynak tahsislerinizi optimize etmenize yardımcı olacağız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- Makinenizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Tasks for Java kütüphanesi indirildi ve projenize eklendi. adresinden indirebilirsiniz.[Java belgeleri için Aspose.Tasks](https://reference.aspose.com/tasks/java/).
## Paketleri İçe Aktar
Gerekli paketleri Java projenize aktararak başlayın:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```
## Adım 1: Yeni Bir Proje Oluşturun
Aspose.Tasks kütüphanesini kullanarak yeni bir proje oluşturarak başlayın:
```java
// Yeni bir proje oluştur
Project splitTaskProject = new Project();
```
## Adım 2: Proje Takvimini Ayarlayın
Zaman çizelgesini oluşturmak için projenin takvim ayarlarını yapın:
```java
// Standart bir takvim edinin
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Projenin takvim ayarlarını belirleyin
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (örneğe devam edin)
```
## 3. Adım: Kök Görev Ekleme
Projenize bir kök görev ekleyin:
```java
// Kök görev
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## 4. Adım: Bölünecek Yeni Bir Görev Ekleme
Projenize bölmek istediğiniz yeni bir görev ekleyin:
```java
// Yeni bir görev ekle
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## Adım 5: Kaynak Ataması Oluşturun
Görev için yeni bir kaynak ataması oluşturun:
```java
// Yeni bir kaynak ataması oluştur
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## Adım 6: Zaman Aşamalı Veri Oluşturun
Kaynak ataması zaman aşamalı verilerini oluşturun:
```java
// Kaynak ataması zaman aşamalı verileri oluşturma
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## Adım 7: Görevi Bölün
Görevi birden fazla parçaya bölün:
```java
// Görevi 3 parçaya bölün
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (örneğe devam edin)
```
## Çözüm
Tebrikler! Aspose.Tasks for Java'yı kullanarak görevleri nasıl böleceğinizi başarıyla öğrendiniz. Bu güçlü kitaplık, Java projelerinde görev yönetimini basitleştirerek proje zaman çizelgelerini ve kaynak tahsislerini optimize etmek için etkili çözümler sunar.
## Sıkça Sorulan Sorular
### Farklı sürelere sahip görevleri bölebilir miyim?
Evet, proje gereksinimlerinize göre görevlerin süresini ayarlayabilirsiniz.
### Aspose.Tasks for Java tüm Java sürümleriyle uyumlu mu?
Aspose.Tasks for Java, çeşitli Java sürümleriyle sorunsuz çalışacak ve uyumluluk sağlayacak şekilde tasarlanmıştır.
### Aspose.Tasks for Java'yı ücretsiz kullanabilir miyim?
Aspose.Tasks for Java, satın almadan önce özelliklerini keşfetmenize olanak tanıyan ücretsiz bir deneme sunar.
### Aspose.Tasks for Java için nasıl destek alabilirim?
 Ziyaret edin[Aspose.Tasks for Java destek forumu](https://forum.aspose.com/c/tasks/15) yardım almak ve toplulukla bağlantı kurmak için.
### Aspose.Tasks for Java için geçici bir lisansa ihtiyacım var mı?
 adresinden geçici lisans alabilirsiniz.[bu bağlantı](https://purchase.aspose.com/temporary-license/) test ve değerlendirme amaçlıdır.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
