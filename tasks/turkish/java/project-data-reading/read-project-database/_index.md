---
date: 2026-02-18
description: Aspose.Tasks for Java ile projeyi PDF olarak kaydetmeyi, Microsoft Project
  veritabanını okumayı, ayrıca Project Server’a bağlanmayı, projeyi HTML’ye dönüştürmeyi
  ve projeyi XML olarak dışa aktarmayı öğrenin.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projeyi PDF olarak kaydedin ve Aspose.Tasks for Java ile Proje Veritabanını
  okuyun
url: /tr/java/project-data-reading/read-project-database/
weight: 12
---

 construct final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projeyi PDF olarak kaydedin ve Aspose.Tasks for Java ile Microsoft Project veritabanını okuyun

## Giriş
Bu öğreticide, **Microsoft Project veritabanını** doğrudan bir Microsoft Project Server'dan nasıl okuyacağınızı ve ardından Aspose.Tasks Java API'sını kullanarak **projeyi PDF olarak kaydedeceğinizi** keşfedeceksiniz. Raporlar oluşturmanız, veri taşımanız veya proje bilgilerini kendi uygulamalarınıza entegre etmeniz gerektiğinde, bu kılavuz size veritabanı bağlantısını kurmaktan projeyi PDF, XML veya HTML olarak dışa aktarmaya kadar her adımda rehberlik eder. Sonunda, ana makinede Microsoft Project kurmadan çalışan sağlam, üretim‑hazır bir çözüme sahip olacaksınız.

## Hızlı Yanıtlar
- **Aspose.Tasks ne yapar?** Microsoft Project dosyalarını ve veritabanlarını okuma, yazma ve manipüle etme için saf‑Java bir API sağlar.  
- **Microsoft Project yüklü olmalı mı?** Hayır, Aspose.Tasks Microsoft Project'ten bağımsız çalışır.  
- **Hangi veritabanı türü desteklenir?** Microsoft SQL Server (Project Server'ın arka ucu).  
- **Diğer formatlara dışa aktarabilir miyim?** Evet, PDF dışında XML, HTML, CSV ve daha fazlasına kaydedebilirsiniz.  
- **Ana önkoşullar nelerdir?** JDK, Aspose.Tasks for Java kütüphanesi, SQL Server JDBC sürücüsü ve **Project Server'a bağlanmak** için kimlik bilgileri.

## Microsoft Project veritabanını okuma
Microsoft Project veritabanını okumak, Project Server'ın SQL Server deposuna bağlanmak, depolanmış proje verilerini çıkarmak ve bunları Aspose.Tasks'in manipüle edebileceği bir `Project` nesnesine yüklemek anlamına gelir. Bu yaklaşım, otomatik raporlama, veri taşıma veya özel analizler için idealdir.

## Aspose.Tasks for Java neden kullanılmalı?
- **Microsoft Project bağımlılığı yok** – herhangi bir sunucu veya CI ortamında çalışır.  
- **Zengin nesne modeli** – görevleri, kaynakları, atamaları, takvimleri ve özel alanları programlı olarak erişebilirsiniz.  
- **Birden fazla dışa aktarma seçeneği** – PDF, XML, HTML, PNG vb., tek bir API çağrısıyla.  
- **Yüksek performans** – büyük kurumsal projeler için optimize edilmiştir.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. Çalışan bir Java geliştirme ortamı (JDK 8 veya daha yeni).  
2. Aspose.Tasks for Java kütüphanesinin projenizin sınıf yoluna eklenmiş olması.  
3. Project Server SQL veritabanı için erişim kimlik bilgileri (sunucu adı, port, veritabanı adı, kullanıcı adı, şifre) **Project Server'a bağlanmak** için.  
4. Microsoft JDBC Sürücüsü for SQL Server (ör. `sqljdbc4.jar`).  

## Paketleri İçe Aktarma
İlk olarak, ihtiyacınız olan sınıfları içe aktarın. Liste, Aspose.Tasks çekirdek sınıflarını ve standart Java yardımcı sınıflarını içerir.

```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```

## Project Server'a nasıl bağlanılır
Güvenilir bir bağlantı kurmak, proje verilerini okumanın temelidir. SQL Server örneğinin Java ana bilgisayarınızdan erişilebilir olduğundan ve kullandığınız girişin Project Server şemasında **SELECT** izinlerine sahip olduğundan emin olun.

## Adım 1: Veritabanı Bağlantısını Kurun
`MspDbSettings` örneği oluşturun; bu, JDBC bağlantı dizesini tutar. Yer tutucu değerleri gerçek sunucu detaylarınızla değiştirin.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro ipucu:** Bağlantı dizesini kimlik bilgilerini doğrudan kod içinde yazmak yerine güvenli bir yapılandırma dosyasında veya ortam değişkeninde saklayın.

## Adım 2: JDBC Sürücüsünü Ekleyin
Microsoft SQL Server JDBC sürücüsünü çalışma zamanında yükleyin, böylece JVM veritabanı ile iletişim kurabilir.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Uyarı:** Sürücü sürümünün SQL Server sürümünüzle eşleştiğinden emin olun. Uyumsuz bir sürücü kullanmak bağlantı hatalarına neden olabilir.

## Adım 3: Proje Verilerini Oku
`MspDbSettings`i geçirerek bir `Project` nesnesi oluşturun. Aspose.Tasks, proje verilerini otomatik olarak veritabanından çekecektir.

```java
Project project = new Project(settings);
```

Bu noktada `project` nesnesini keşfedebilirsiniz—görevleri, kaynakları listeleyebilir veya gerektiği gibi alanları değiştirebilirsiniz.

## Adım 4: Projeyi PDF Olarak Kaydedin
Yüklenen projeyi istediğiniz dosya formatına dışa aktarın. Aşağıdaki örnek projeyi **PDF** olarak kaydeder; bu, yazdırılabilir raporlar için mükemmeldir. `SaveFileFormat` enum'ını değiştirerek **projeyi XML olarak dışa aktarabilir** veya **projeyi HTML'e dönüştürebilirsiniz**.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

XML tercih ediyorsanız, `SaveFileFormat.Pdf` yerine `SaveFileFormat.Xml` koymanız yeterlidir. HTML çıktısı için `SaveFileFormat.Html` kullanın.

## Yaygın Sorunlar ve Çözümler
| Sorun | Yaygın Neden | Çözüm |
|-------|--------------|------|
| **Bağlantı zaman aşımı** | Yanlış sunucu/port veya güvenlik duvarı engellemesi | Sunucu adresini doğrulayın, 1433 portunu açın ve basit bir JDBC test programı ile bağlantıyı test edin. |
| **Kimlik doğrulama hatası** | Geçersiz kullanıcı adı/şifre veya SQL Server'ın SQL kimlik doğrulaması için yapılandırılmamış olması | Geçerli bir SQL girişi kullanın veya sunucuda karışık‑mod kimlik doğrulamayı etkinleştirin. |
| **Sürücü bulunamadı** | JDBC jar dosyası sınıf yolunda değil | `addJDBCDriver`'ın doğru `.jar` dosyasına işaret ettiğinden ve yolun çift ters eğik çizgi (`\\`) kullandığından emin olun. |
| **Yükleme sonrası boş proje** | Project Server tablolarını okuma izni yetersiz | Girişe Project Server veritabanı şemasında SELECT hakları verin. |

## Sıkça Sorulan Sorular

**S: Aspose.Tasks, Microsoft Project dışındaki diğer veritabanlarından proje verilerini okuyabilir mi?**  
C: Evet, Aspose.Tasks XML dosyaları, Primavera ve Microsoft Project veritabanları dahil olmak üzere çeşitli kaynaklardan proje verilerini okumayı destekler.

**S: Aspose.Tasks, farklı Microsoft Project sürümleriyle uyumlu mu?**  
C: Evet, Aspose.Tasks birden çok Microsoft Project sürümüyle çalışacak şekilde tasarlanmıştır, sorunsuz entegrasyon sağlar.

**S: Proje verilerini kaydetmeden önce manipüle edebilir miyim?**  
C: Kesinlikle, Aspose.Tasks, dışa aktarmadan önce görev ekleme, kaynakları güncelleme ve proje özelliklerini ayarlama için zengin bir API sunar.

**S: Aspose.Tasks birden çok çıktı formatını destekliyor mu?**  
C: Evet, projeleri PDF, XML, HTML, CSV, PNG, JPEG ve daha fazlası olarak kaydedebilirsiniz.

**S: Aspose.Tasks ile ilgili daha fazla destek veya yardım nereden bulabilirim?**  
C: Ek yardım için Aspose.Tasks forumunu ziyaret edebilir veya web sitesinde bulunan belgeleri [buradan](https://forum.aspose.com/c/tasks/15) inceleyebilirsiniz.

## Sonuç
Bu adım‑adım kılavuzu izleyerek, artık **Microsoft Project veritabanını** nasıl **projeyi PDF olarak kaydedeceğinizi** ve Aspose.Tasks for Java kullanarak diğer formatlara nasıl dışa aktaracağınızı biliyorsunuz. Bu yaklaşım, Microsoft Project bağımlılığını ortadan kaldırır, otomatik raporlamayı kolaylaştırır ve güçlü özel entegrasyonların kapısını açar.

---

**Son Güncelleme:** 2026-02-18  
**Test Edilen:** Aspose.Tasks for Java 24.5 (yazım anındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}