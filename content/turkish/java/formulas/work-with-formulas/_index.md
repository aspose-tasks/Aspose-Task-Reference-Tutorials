---
title: Java için Aspose.Tasks ile MS Project Formülleri
linktitle: Aspose.Tasks'ta Formüllerle Çalışma
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks kitaplığını kullanarak MS Project dosyalarını Java'da nasıl değiştireceğinizi öğrenin. Nitelikleri kolaylıkla oluşturun, değiştirin ve hesaplayın.
type: docs
weight: 11
url: /tr/java/formulas/work-with-formulas/
---
## giriiş
Bu eğitimde Aspose.Tasks for Java'yı kullanarak MS Project Formülleri ile çalışmayı derinlemesine inceleyeceğiz. Aspose.Tasks, geliştiricilerin Microsoft Project dosyalarını programlı olarak değiştirmesine olanak tanıyan güçlü bir kitaplıktır. Kapsamlı özellikleri sayesinde Java uygulamalarında proje dosyalarını kolaylıkla oluşturabilir, okuyabilir, değiştirebilir ve dönüştürebilirsiniz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşulları oluşturduğunuzdan emin olun:
### Java Geliştirme Ortamı
Sisteminizde Java Development Kit'in (JDK) kurulu olduğundan emin olun. En son JDK'yı Oracle web sitesinden indirip yükleyebilirsiniz.
### Aspose.Tasks Kitaplığı
Aspose.Tasks kütüphanesinin Java projenize eklenmesi gerekir. Kütüphaneyi adresinden indirebilirsiniz.[Aspose.Tasks for Java indirme sayfası](https://releases.aspose.com/tasks/java/) ve bunu projenizin bağımlılıklarına ekleyin.

## Paketleri İçe Aktar
Örneklere dalmadan önce gerekli paketleri Java kodunuza aktarın:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Sağlanan örneği birden çok adıma ayıralım:
## 1. Adım: Özel Alanla Test Projesi Oluşturun
```java
Project project = CreateTestProjectWithCustomField();
```
 İlk olarak, aşağıdakileri kullanarak özel bir alanla bir test projesi oluşturun:`CreateTestProjectWithCustomField()` yöntem. Bu yöntem, yeni oluşturulan projeyi temsil eden bir Project nesnesini döndürecektir.
## Adım 2: Genişletilmiş Bir Nitelik Tanımı Tanımlayın
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
Genişletilmiş öznitelik tanımını projeden alın ve takma adını ve formülünü ayarlayın. Bu örnekte, bitiş tarihinden son teslim tarihine kadar geçen gün sayısını hesaplamak için bir özellik tanımlıyoruz.
## 3. Adım: Bir Görev için Son Tarihi Belirleyin
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
Bir Takvim nesnesi oluşturun ve son tarihi ayarlayın. Ardından projeden bir görev alın ve Takvim nesnesini kullanarak son tarihini ayarlayın.
## Adım 4: Projeyi Kaydet
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
Son olarak projeyi belirtilen ad ve formatta bir dosyaya kaydedin. Bu durumda onu bir MPP dosyası olarak kaydediyoruz.

## Çözüm
Bu eğitimde Aspose.Tasks for Java kullanarak MS Project Formülleriyle nasıl çalışılacağını öğrendik. Bu adımları izleyerek, özel alanlar ekleyerek ve formüllere dayalı öznitelikleri hesaplayarak proje dosyalarını programlı olarak etkili bir şekilde yönetebilirsiniz.

## SSS'ler
### S: Aspose.Tasks'ı diğer programlama dilleriyle kullanabilir miyim?
C: Evet, Aspose.Tasks, Java, .NET ve daha fazlasını içeren çeşitli programlama dillerini destekler.
### S: Aspose.Tasks için ücretsiz deneme sürümü mevcut mu?
 C: Evet, Aspose.Tasks'ın ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks belgelerini nerede bulabilirim?
 C: Aspose.Tasks belgelerini burada bulabilirsiniz.[Burada](https://reference.aspose.com/tasks/java/).
### S: Aspose.Tasks için nasıl destek alabilirim?
 C: Destek için şu adresi ziyaret edebilirsiniz:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).
### S: Aspose.Tasks'ı kullanmak için geçici bir lisansa ihtiyacım var mı?
C: Ek özelliklere ihtiyacınız varsa, adresinden geçici bir lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).