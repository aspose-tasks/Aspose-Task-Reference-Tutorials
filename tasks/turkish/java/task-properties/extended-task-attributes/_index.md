---
title: Aspose.Tasks'ta Genişletilmiş Görev Nitelikleri
linktitle: Aspose.Tasks'ta Genişletilmiş Görev Nitelikleri
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'daki genişletilmiş görev niteliklerini keşfedin. Adım adım kılavuz, SSS ve destek. Proje yönetiminizi bugün optimize edin!
weight: 16
url: /tr/java/task-properties/extended-task-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Genişletilmiş Görev Nitelikleri

## giriiş
Aspose.Tasks for Java'da genişletilmiş görev niteliklerinden yararlanmaya ilişkin kapsamlı kılavuzumuza hoş geldiniz. Aspose.Tasks, Microsoft Project belgeleriyle sorunsuz bir şekilde çalışmanıza olanak tanıyan güçlü bir Java kitaplığıdır. Bu eğitimde, genişletilmiş görev niteliklerini derinlemesine inceleyeceğiz ve proje yönetimi yeteneklerinizi geliştirmek için bunları nasıl kullanabileceğinizi göstereceğiz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- Java programlamanın temel bilgisi.
- Makinenize Java Development Kit'i (JDK) yüklediniz.
- IntelliJ veya Eclipse gibi entegre bir geliştirme ortamı (IDE).
## Paketleri İçe Aktar
Aspose.Tasks projenizi başlatmak için gerekli paketleri içe aktararak başlayın:
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```
Şimdi, süreç boyunca size yol göstermesi için örneği birden fazla adıma ayıralım:
## 1. Adım: Göreve ve Genişletilmiş Niteliklere Erişim
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```
## 2. Adım: Alan Kimliğini ve Değer GUID'ini Alma
```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```
## Adım 3: Farklı Öznitelik Türlerini Ele Alma
```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```
Genişletilmiş görev niteliklerini keşfetmek ve değiştirmek için projenizdeki her görev için bu adımları tekrarlayın.
## Çözüm
Sonuç olarak, Aspose.Tasks for Java'daki genişletilmiş görev niteliklerini anlamak ve kullanmak, proje yönetimi becerilerinizi önemli ölçüde geliştirebilir. Bu kılavuz, bu yolculuğa başlamanız için sağlam bir temel sağlar.
## Sıkça Sorulan Sorular
### Genişletilmiş görev niteliklerini programlı olarak değiştirebilir miyim?
Evet, Aspose.Tasks for Java'yı kullanarak genişletilmiş görev niteliklerini değiştirebilirsiniz. Ayrıntılı talimatlar için belgelere bakın.
### Deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Tasks for Java desteğini nerede bulabilirim?
 Destek için şu adresi ziyaret edin:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).
### Geçici lisansı nasıl alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Tasks for Java'nın tam sürümünü nereden satın alabilirim?
 Tam sürümünü satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
