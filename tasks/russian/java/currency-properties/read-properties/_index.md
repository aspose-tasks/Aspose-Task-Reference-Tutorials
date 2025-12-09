---
date: 2025-12-04
description: Узнайте, как считывать свойства валюты в Java из файлов MS Project с
  помощью Aspose.Tasks for Java. Следуйте этому пошаговому руководству, чтобы программно
  извлекать код валюты, её символ, количество знаков и позицию.
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Чтение свойств валюты Java с проектами Aspose.Tasks
url: /ru/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Чтение свойств валюты Java с Aspose.Tasks Projects

## Introduction
В этом учебнике вы **прочитаете свойства валюты Java** из файлов Microsoft Project, используя API Aspose.Tasks for Java. Aspose.Tasks позволяет работать с файлами .mpp без установки Microsoft Project, что делает его идеальным для автоматизированной отчетности, миграции данных или интеграции в Java‑ориентированные корпоративные приложения. К концу руководства вы сможете извлекать код валюты, символ, количество десятичных знаков и позицию символа непосредственно из файла проекта.

## Quick Answers
- **Что означает “read currency properties java”?** Это получение метаданных, связанных с валютой (код, символ, количество знаков, позиция), из файла MS Project с помощью кода на Java.  
- **Нужна ли лицензия для пробного использования?** Доступна бесплатная пробная версия Aspose.Tasks; для использования в продакшене требуется коммерческая лицензия.  
- **Какая версия JDK требуется?** Java 8 или новее.  
- **Можно ли изменить настройки валюты после их чтения?** Да, Aspose.Tasks поддерживает как чтение, так и запись свойств валюты.  
- **Совместимо ли это со всеми версиями .mpp?** API поддерживает файлы, созданные в Microsoft Project 2003‑2021.

## What is read currency properties java?
Чтение свойств валюты в Java означает доступ к настройкам уровня проекта, определяющим, как отображаются денежные значения в файле Microsoft Project. Эти настройки включают ISO‑код валюты (например, **USD**), символ (**$**), количество десятичных знаков и то, появляется ли символ перед суммой или после неё.

## Why read currency properties java with Aspose.Tasks?
- **Не требуется установка Microsoft Project** – API работает на любой платформе, поддерживающей Java.  
- **Быстрое извлечение в процессе** – идеально для пакетной обработки большого количества файлов проектов.  
- **Полный контроль** – вы можете комбинировать полученные значения с пользовательской отчетностью или интегрировать их в ERP‑системы.  
- **Поддержка разных версий** – работает с файлами .mpp от Project 2003 до последнего выпуска 2021 года.

## Prerequisites
Перед началом убедитесь, что у вас есть:

1. **Java Development Kit (JDK)** – установлен Java 8 или новее и настроен в `PATH`.  
2. **Aspose.Tasks for Java JAR** – скачайте последнюю библиотеку [здесь](https://releases.aspose.com/tasks/java/) и добавьте её в classpath вашего проекта.  

## Import Packages
Начните с импорта пространства имен Aspose.Tasks, необходимого для работы с проектом:

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up Your Project Directory
Определите папку, содержащую файл `.mpp`, который вы хотите проанализировать. Хранение пути в переменной делает код переиспользуемым:

```java
String dataDir = "Your Data Directory";
```

*Замените `"Your Data Directory"` на абсолютный или относительный путь к папке, где находится `project.mpp`.*

## Step 2: Create a Project Reader Instance
Загрузите файл Microsoft Project в объект `Project`. Этот объект предоставляет доступ ко всем свойствам проекта, включая настройки валюты:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Если ваш файл имеет другое имя, измените `"project.mpp"` соответственно.*

## Step 3: Display Currency Properties
Теперь получите каждый атрибут валюты, используя перечисление `Prj`, и выведите результаты в консоль. API возвращает объекты, которые можно преобразовать в строки для отображения:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**Что вы увидите:**  
- **Currency Code** – код ISO‑4217, например `USD`, `EUR`, `JPY`.  
- **Currency Digits** – обычно `2` для большинства **currencies**, `0` для японской иены.  
- **Currency Symbol** – символ, отображаемый в отчетах (`$`, `€`, `¥`).  
- **Currency Symbol Position** – `0` для **before** суммы, `1` для **after**.

## Step 4: Process Completion
Сигнализируйте, что извлечение завершилось успешно. Это простое сообщение полезно, когда код запускается как часть более крупного пакетного задания:

```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** | Путь `dataDir` указан неверно или имя файла написано с ошибкой. | Проверьте строку пути и убедитесь, что файл `.mpp` существует по указанному месту. |
| **NullPointerException on `project.get(...)`** | Файл проекта не содержит информации о валюте (маловероятно) или ключ свойства указан неверно. | Используйте `project.contains(Prj.CURRENCY_CODE)`, чтобы проверить наличие перед чтением. |
| **LicenseException** | Запуск без действующей лицензии Aspose.Tasks в продакшн‑окружении. | Примените файл лицензии с помощью `License license = new License(); license.setLicense("Aspose.Tasks.lic");` перед созданием объекта `Project`. |

## Frequently Asked Questions

**Q: Совместим ли Aspose.Tasks со всеми версиями Microsoft Project?**  
A: Aspose.Tasks поддерживает файлы .mpp, созданные в Microsoft Project 2003‑2021, охватывая как старые, так и последние форматы.

**Q: Можно ли изменить свойства валюты с помощью Aspose.Tasks?**  
A: Да, вы можете как читать, так и записывать настройки валюты. Используйте `project.set(Prj.CURRENCY_CODE, "EUR");` и затем сохраните проект.

**Q: Подходит ли Aspose.Tasks для коммерческого использования?**  
A: Абсолютно. Это коммерческая библиотека; приобрести лицензию можно [здесь](https://purchase.aspose.com/buy).

**Q: Предоставляет ли Aspose.Tasks бесплатную пробную версию?**  
A: Да, полностью функциональная пробная версия доступна [здесь](https://releases.aspose.com/).

**Q: Где можно получить помощь или поддержку по Aspose.Tasks?**  
A: Официальный форум Aspose.Tasks — лучшее место для получения помощи; посетите его [здесь](https://forum.aspose.com/c/tasks/15).

## Conclusion
Теперь вы знаете, как **read currency properties java** из файла MS Project с помощью Aspose.Tasks for Java. Эта возможность позволяет включать метаданные валюты в пользовательские отчеты, финансовый анализ или интеграционные конвейеры без необходимости использовать Microsoft Project. Не стесняйтесь экспериментировать с изменением свойств или комбинировать эти данные с другими атрибутами проекта для создания более богатых решений.

---

**Last Updated:** 2025-12-04  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}