---
title: Aspose.Tasks'ta Ebeveyn ve Çocuk Görevlerini Yönetin
linktitle: Aspose.Tasks'ta Ebeveyn ve Çocuk Görevlerini Yönetin
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java ile proje yönetimi verimliliğini artırın. Ebeveyn ve alt görevleri adım adım yönetmeyi öğrenin. Şimdi başla!
weight: 24
url: /tr/java/task-properties/parent-child-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Ebeveyn ve Çocuk Görevlerini Yönetin

## giriiş
Proje yönetimi alanında etkili görev organizasyonu çok önemlidir. Aspose.Tasks for Java, üst ve alt görevleri verimli bir şekilde yönetmek için güçlü bir çözüm sunar. Bu eğitimde, proje görevlerinizi kolaylaştırmak için Aspose.Tasks for Java'yı kullanma sürecinde size rehberlik edeceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- Java programlamanın temel anlayışı.
-  Aspose.Tasks for Java kütüphanesi kuruldu. İndirebilirsin[Burada](https://releases.aspose.com/tasks/java/).
- Sisteminizde kurulu bir Java Tümleşik Geliştirme Ortamı (IDE).
## Paketleri İçe Aktar
Başlamak için gerekli paketleri Java projenize aktarın. Bu paketler Aspose.Tasks for Java işlevleriyle kusursuz entegrasyonu kolaylaştırır.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```
## Adım 1: Proje Başlangıç Tarihini Ayarlayın
Projenin başlangıç tarihini ve diğer ilgili parametreleri ayarlayarak başlayın.
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Paket içe aktarmaları için ek kod buraya eklenebilir
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## Adım 2: Ana Görev Ekleme (Görev 1)
"Görev 1" adında bir ana görev oluşturun ve özelliklerini yapılandırın.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## 3. Adım: Alt Görevlerle birlikte Ana Görevi (Görev 2) ekleyin
Şimdi "Görev 2" adında başka bir ana görev ekleyin ve alt görevleri de ekleyin (Görev 3 ve Görev 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Görev 2'ye alt görevler ekleyin
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Görev 3 ve Görev 4 için ek yapılandırma buraya eklenebilir
```
## 4. Adım: Alt Görevleri Yapılandırın
Görev 3 ve Görev 4 için başlangıç tarihlerini, sürelerini ve kısıtlamalarını belirtin.
```java
// Görev 3'ü Yapılandır
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Görev 4'ü Yapılandır
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## 5. Adım: Görev Tamamlanma Yüzdesini Güncelleyin
Görev 3 ve Görev 4'ün tamamlanma yüzdesini ayarlayın.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## Adım 6: Projeyi Kaydet
Son olarak projeyi uygulanan değişikliklerle kaydedin.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
Bu adım adım kılavuz, Aspose.Tasks for Java kullanılarak ebeveyn ve alt görevlerin nasıl etkili bir şekilde yönetileceğini gösterir. Projenizin gereksinimlerine uyacak farklı konfigürasyonlarla denemeler yapın.
## Çözüm
Sonuç olarak Aspose.Tasks for Java, geliştiricilerin proje görevlerini verimli bir şekilde yerine getirmesine olanak tanıyarak kusursuz organizasyon ve izleme sağlar. Proje yönetimi yeteneklerinizi geliştirmek için özetlenen adımları uygulayın.
## SSS
### Aspose.Tasks for Java farklı proje dosyası formatlarıyla uyumlu mu?
Evet, Aspose.Tasks for Java, MPP ve XML dahil olmak üzere çeşitli proje dosyası formatlarını destekler.
### Görev özelliklerini bu eğitimde anlatılanların ötesinde özelleştirebilir miyim?
Kesinlikle! Aspose.Tasks for Java, görev özellikleri için kapsamlı özelleştirme seçenekleri sunar.
### Aspose.Tasks için destek arayabileceğim bir topluluk forumu var mı?
 Evet, ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) topluluk desteği için.
### Aspose.Tasks for Java için nasıl geçici lisans alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Tasks for Java'nın kapsamlı belgelerini nerede bulabilirim?
 Belgeler mevcut[Burada](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
