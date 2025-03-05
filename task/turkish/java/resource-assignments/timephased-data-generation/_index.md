---
title: Aspose.Tasks'ta Zaman Aşamalı Veri Oluşturma
linktitle: Aspose.Tasks'ta Kaynak Atamaları için Zaman Aşamalı Veri Oluşturun
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak kaynak atamaları için zaman aşamalı verileri nasıl oluşturacağınızı öğrenin. Bu kapsamlı kılavuzla proje yönetimi verimliliğini artırın.
type: docs
weight: 24
url: /tr/java/resource-assignments/timephased-data-generation/
---
## giriiş
Bu eğitimde Aspose.Tasks for Java'yı kullanarak kaynak atamaları için zaman aşamalı veri oluşturma sürecini anlatacağız. Zaman aşamalı veriler, bir proje içinde kaynakların zaman içinde nasıl tahsis edildiğine dair değerli bilgiler sağlayarak proje yöneticilerinin bilinçli kararlar almasına yardımcı olur.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun. JDK'yı şu adresten indirip yükleyebilirsiniz:[Burada](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks for Java Kütüphanesi: Aspose.Tasks for Java kütüphanesine sahip olmanız gerekir. adresinden indirebilirsiniz.[İnternet sitesi](https://releases.aspose.com/tasks/java/).

## Paketleri İçe Aktar
Öncelikle Aspose.Tasks ile çalışmak için gerekli paketleri içe aktaralım:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## Adım 1: Kaynak MPP Dosyasını Okuyun
```java
// Belgeler dizininin yolu.
String dataDir = "Your Data Directory";
// Kaynak MPP dosyasını okuyun
Project project = new Project(dataDir + "project.mpp");
```
## 2. Adım: Görev ve Kaynak Atamasını Alın
```java
// Projenin ilk görevini alın
Task task = project.getRootTask().getChildren().getById(1);
// Projenin ilk kaynak atamasını alın
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## Adım 3: Düz Kontur ile Zaman Aşamalı Veriler Oluşturun
```java
// Düz kontur varsayılan konturdur
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Adım 4: Konturu Kaplumbağa olarak değiştirin
```java
// Konturu Kaplumbağa olarak değiştir
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Adım 5: Konturu BackLoaded olarak değiştirin
```java
// Konturu BackLoaded olarak değiştir
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Adım 6: Konturu FrontLoaded olarak değiştirin
```java
// Konturu FrontLoaded olarak değiştir
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Adım 7: Konturu Zil olarak değiştirin
```java
// Konturu Bell olarak değiştir
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Adım 8: Konturu EarlyPeak olarak değiştirin
```java
// Konturu EarlyPeak olarak değiştir
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Adım 9: Konturu LatePeak olarak değiştirin
```java
// Konturu LatePeak olarak değiştir
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Adım 10: Konturu DoublePeak olarak değiştirin
```java
// Konturu DoublePeak olarak değiştir
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Çözüm
Bu eğitimde Aspose.Tasks for Java kullanarak kaynak atamaları için zaman aşamalı verilerin nasıl oluşturulacağını ele aldık. Farklı çalışma hatlarını anlamak, proje yöneticilerinin projelerinde kaynak tahsisini ve planlamayı etkili bir şekilde yönetmelerine yardımcı olabilir.
## SSS'ler
### Aspose.Tasks'ı diğer Java kütüphaneleriyle kullanabilir miyim?
Evet, Aspose.Tasks proje yönetimi yeteneklerini geliştirmek için diğer Java kütüphaneleriyle entegre edilebilir.
### Aspose.Tasks büyük ölçekli kurumsal projelere uygun mu?
Kesinlikle Aspose.Tasks, büyük ölçekli kurumsal projeler de dahil olmak üzere her boyuttaki projeyi yürütmek üzere tasarlanmıştır.
### Aspose.Tasks farklı proje dosyası formatları için destek sağlıyor mu?
Evet, Aspose.Tasks MPP, XML ve MPX dahil olmak üzere çeşitli proje dosyası formatlarını destekler.
### Çalışma konturlarını proje gereksinimlerime göre özelleştirebilir miyim?
Evet, Aspose.Tasks, kullanıcıların özel proje ihtiyaçlarına uyacak şekilde özel çalışma hatları tanımlamalarına olanak tanır.
### Aspose.Tasks konusunda yardım alabileceğim bir topluluk forumu var mı?
 Evet, ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) Destek ve tartışmalar için.