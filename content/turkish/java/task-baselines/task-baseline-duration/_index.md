---
title: Aspose.Tasks'ta Görev Temel Süre Yönetimi
linktitle: Aspose.Tasks'ta Görev Temel Süre Yönetimi
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak MS Project'te görev temellerini nasıl verimli bir şekilde yöneteceğinizi öğrenin. Bu eğitim, süreç boyunca size adım adım yol gösterir.
type: docs
weight: 12
url: /tr/java/task-baselines/task-baseline-duration/
---
## giriiş
MS Project'te görev temellerini yönetmek, proje planlama ve izleme için çok önemlidir. Bu eğitimde Aspose.Tasks for Java'yı kullanarak görev temel sürelerini etkili bir şekilde nasıl yönetebileceğimizi keşfedeceğiz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Java Geliştirme Ortamı: Sisteminizde Java Geliştirme Kitinin (JDK) kurulu olduğundan emin olun.
2.  Aspose.Tasks Kütüphanesi: Aspose.Tasks for Java kütüphanesini şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/java/).

## Paketleri İçe Aktar
Öncelikle Java projeniz için gerekli paketleri içe aktarın:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## 1. Adım: Proje Örneği Oluşturun
Aşağıdaki kodu kullanarak yeni bir proje örneği başlatın:
```java
Project project = new Project();
```
## Adım 2: Görev Temeli Oluşturun
Yeni bir görev oluşturun ve aşağıdaki kodu kullanarak temel çizgisini ayarlayın:
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## 3. Adım: Görev Temel Bilgilerini Görüntüleyin
Süre, başlangıç tarihi, bitiş tarihi ve daha fazlası gibi görev temel bilgilerini alın ve görüntüleyin:
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## Adım 4: Geçici Temel Değeri ve Sabit Maliyeti Kontrol Edin
Temelin geçici bir temel olup olmadığını kontrol edin ve onunla ilişkili sabit maliyetleri alın:
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## Adım 5: Zaman Aşamalı Verileri Yazdırın
Görev temeli ile ilişkili zaman aşamalı verileri yazdırın:
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
Bu adımları izleyerek Aspose.Tasks for Java'yı kullanarak MS Project'teki görev temel sürelerini etkili bir şekilde yönetebilirsiniz.

## Çözüm
Görev temel çizgilerini yönetmek, proje yönetimi için çok önemlidir ve planlanan programdan sapmaları izlemenize olanak tanır. Aspose.Tasks for Java ile bu süreç kolaylaştırılmış ve verimli hale gelerek daha iyi proje kontrolü ve teslimatı sağlıyor.
## SSS'ler
### MS Project'te görev temeli nedir?
MS Project'teki görev temeli, bir görevin başlangıç tarihi, bitiş tarihi ve süresi de dahil olmak üzere başlangıçta planlanan zamanlamasının anlık görüntüsüdür.
### Görev temellerini yönetmek neden önemlidir?
Görev temellerini yönetmek, planlanan programın projenin fiili ilerleyişiyle karşılaştırılmasına yardımcı olarak daha iyi izleme ve karar almayı kolaylaştırır.
### Bir görev temel çizgisini ayarladıktan sonra değiştirebilir miyim?
Evet, proje planındaki değişiklikleri yansıtacak şekilde MS Project'teki görev temellerini değiştirebilirsiniz. Ancak orijinal temel çizgiden herhangi bir sapmanın belgelenmesi önemlidir.
### Aspose.Tasks diğer proje yönetimi işlevlerini destekliyor mu?
Evet, Aspose.Tasks proje yönetimi için görev planlama, kaynak tahsisi ve Gantt şeması oluşturma gibi çok çeşitli özellikler sunar.
### Aspose.Tasks için desteği nerede bulabilirim?
 Aspose.Tasks için desteği şurada bulabilirsiniz:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15), soru sorabileceğiniz ve diğer kullanıcılarla etkileşim kurabileceğiniz yer.