---
title: Aspose.Tasks'ta Görev Bitiş Tarihini Böl
linktitle: Aspose.Tasks'ta Görev Bitiş Tarihini Böl
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak görev bitiş tarihlerini zahmetsizce nasıl bölebileceğinizi öğrenin. Doğru zaman çizelgeleriyle proje yönetimini geliştirin.
weight: 28
url: /tr/java/task-properties/split-task-finish-date/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Görev Bitiş Tarihini Böl

## giriiş
Proje yönetiminde görev zaman çizelgelerini anlamak, projenin başarılı bir şekilde tamamlanması için çok önemlidir. Aspose.Tasks for Java, proje görevlerini verimli bir şekilde yönetmek için güçlü özellikler sağlar. Bu eğitimde Aspose.Tasks'ı kullanarak görev bitiş tarihlerini bölmeyi inceleyerek proje zaman çizelgelerini etkili bir şekilde yönetmenize yardımcı olacağız.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Java programlamanın temel bilgisi.
-  Aspose.Tasks for Java kütüphanesi kuruldu. İndirebilirsin[Burada](https://releases.aspose.com/tasks/java/).
- Bir Java geliştirme ortamı kuruldu.
## Paketleri İçe Aktar
Java projenize gerekli paketleri ekleyerek başlayın:
```java
import com.aspose.tasks.*;
```
## 1. Adım: Bölünmüş Görevi Bulun
Proje içinde bölmek istediğiniz görevi bulun:
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Projeyi oku
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## Adım 2: Proje Takvimini Bulun
Doğru tarih hesaplamaları için proje takvimini alın:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## Adım 3: Farklı Sürelerle Görev Bitiş Tarihini Hesaplayın
Şimdi görevin çeşitli süreler için bitiş tarihini hesaplayın:
## Adım 3.1: 8 Saatlik Süre
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
Saatleri buna göre ayarlayarak yukarıdaki kodu farklı süreler için tekrarlayın.
## Çözüm
Görev bitiş tarihlerini değiştirme sanatında ustalaşmak, etkili proje yönetimi için çok önemlidir. Aspose.Tasks for Java bu süreci basitleştirerek proje zaman çizelgelerinizi zahmetsizce düzenlemenize olanak tanır.
## SSS
### S1: Aspose.Tasks for Java'yı nasıl indirebilirim?
 A1: İndirebilirsin[Burada](https://releases.aspose.com/tasks/java/).
### S2: Aspose.Tasks belgelerini nerede bulabilirim?
 A2: Belgelere bakın[Burada](https://reference.aspose.com/tasks/java/).
### S3: Aspose.Tasks için nasıl geçici lisans alabilirim?
 Cevap 3: Geçici bir lisans edinin[Burada](https://purchase.aspose.com/temporary-license/).
### S4: Aspose.Tasks için nereden destek alabilirim?
 Cevap4: Destek forumunu ziyaret edin[Burada](https://forum.aspose.com/c/tasks/15).
### S5: Aspose.Tasks'ı satın alabilir miyim?
 A5: Evet, satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
