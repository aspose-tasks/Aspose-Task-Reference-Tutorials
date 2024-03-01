---
title: Aspose.Tasks'ta Görev Zaman Aşamalı Verileri
linktitle: Aspose.Tasks'ta Görev Zaman Aşamalı Verileri
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı keşfedin ve ana görev zaman aşamalı veri yönetimini keşfedin. Kitaplığı indirin, ücretsiz deneme sürümünün keyfini çıkarın ve proje takibinizi kolaylaştırın.
type: docs
weight: 34
url: /tr/java/task-properties/task-timephased-data/
---
## giriiş
Proje yönetimi alanında, görevin zaman aşamalı verilerinin hassas bir şekilde izlenmesi, verimli proje yürütülmesi için çok önemlidir. Aspose.Tasks for Java, bu süreci kolaylaştırmak için güçlü özellikler ve esneklik sunan güçlü bir araç olarak ortaya çıkıyor. Bu eğitim, görev zaman aşamalı verilerini etkili bir şekilde yönetmek için Aspose.Tasks for Java'yı kullanma konusunda size rehberlik edecektir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- Java Geliştirme Ortamı: Sisteminizde Java'nın kurulu olduğundan emin olun.
-  Aspose.Tasks for Java Library: Aspose.Tasks kütüphanesini indirin ve projenize ekleyin. Kütüphaneyi bulabilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
- Belge Dizini: Proje belgeleriniz için bir dizin oluşturun.
## Paketleri İçe Aktar
Aspose.Tasks için gerekli paketleri Java projenize aktarın:
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
## Adım 1: Proje Başlangıç Tarihini Ayarlayın
```java
Project project = new Project(dataDir + "project.xml");
// Paket içe aktarmaları için ek kod
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
Açıklama: Bir takvim nesnesini başlatın, başlangıç tarihini ayarlayın ve bunu projeye uygulayın.
## Adım 2: Görevi ve Kaynağı Tanımlayın
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
Açıklama: Standart ve fazla mesai ücretlerini ayarlayarak bir görev ve kaynak oluşturun.
## 3. Adım: Görev Süresini Ayarlayın
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
Açıklama: Görevin süresini tanımlayın (örn. 6 gün).
## Adım 4: Kaynağı Göreve Atayın
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
Açıklama: Kaynağı göreve atayın.
## Adım 5: Kaynak Atamasını Yapılandırma
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
Açıklama: Kaynak ataması için durdurma, devam ettirme ve iş dağılımı gibi parametreleri ayarlayın.
## Adım 6: Taban Çizgisini Ayarlayın
```java
project.setBaseline(BaselineType.Baseline);
```
Açıklama: Proje için bir temel oluşturun.
## Adım 7: Görev Tamamlamayı Güncelleyin
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
Açıklama: Görevin tamamlanma yüzdesini belirtin.
## Adım 8: Zaman Aşamalı Verileri Alın
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
Açıklama: Kalan işin atanması için zaman aşamalı verileri alın.
## Adım 9: Zaman Aşamalı Verileri Görüntüleyin
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Diğer değerleri görüntülemek için ek kod
```
Açıklama: Zaman aşamalı verilerin çıktısını alın ve görüntüleyin.
## Çözüm
Görev zaman aşamalı verilerinin etkili bir şekilde yönetilmesi, projenin başarısı için vazgeçilmezdir. Aspose.Tasks for Java, kapsamlı işlevler sunarak bu süreci basitleştirir. Bu öğreticiyi takip ederek Aspose.Tasks'i Java projenize sorunsuz bir şekilde entegre edebilir, proje zaman çizelgeleri ve kaynak tahsisi üzerinde hassas kontrol sağlayabilirsiniz.
## Sıkça Sorulan Sorular
### S: Aspose.Tasks for Java'yı herhangi bir Java projesinde kullanabilir miyim?
C: Evet, Aspose.Tasks for Java, tüm Java tabanlı projelerle uyumludur.
### S: Aspose.Tasks for Java için ek desteği nerede bulabilirim?
 C: Ziyaret edin[Aspose.Tasks Forumu](https://forum.aspose.com/c/tasks/15) Destek ve tartışmalar için.
### S: Aspose.Tasks for Java'nın ücretsiz deneme sürümü mevcut mu?
 C: Evet, ücretsiz deneme sürümünü keşfedebilirsiniz[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks for Java için nasıl geçici lisans alabilirim?
 C: Geçici bir lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### S: Aspose.Tasks for Java'yı nereden satın alabilirim?
 C: Java için Aspose.Tasks'ı satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).