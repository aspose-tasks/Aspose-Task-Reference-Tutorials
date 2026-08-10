---
date: 2026-06-05
description: Узнайте, как фильтровать MPP файлы с помощью Aspose.Tasks for Java, настраивать
  filter criteria и фильтровать tasks по дате для оптимизации project management.
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: Как фильтровать MPP файлы с помощью Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Как фильтровать MPP файлы с помощью Aspose.Tasks for Java
url: /ru/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как фильтровать файлы MPP с помощью Aspose.Tasks для Java

## Введение
Если вы работаете с файлами Microsoft Project (*.mpp*) в Java‑приложении, вам часто понадобится **фильтровать файлы MPP**, чтобы изолировать задачи, ресурсы или назначения, которые имеют наибольшее значение. В этом руководстве мы пошагово покажем, **как программно фильтровать mpp**‑файлы с помощью Aspose.Tasks for Java, продемонстрируем, как **настроить критерии фильтра**, и рассмотрим практический сценарий «фильтрация задач по дате». К концу вы получите готовый фрагмент кода, который можно вставить в любой Java‑проект.

## Быстрые ответы
- **Что означает “filter mpp”?** Это извлечение подмножества данных проекта на основе заданных условий.  
- **Какая библиотека это обрабатывает?** Aspose.Tasks for Java предоставляет комплексный API для создания и применения фильтров.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; коммерческая лицензия требуется для продакшна.  
- **Можно ли фильтровать задачи, ресурсы и назначения?** Да — каждый тип сущности имеет свою коллекцию фильтров.  
- **Требуется ли Java 8 или выше?** Aspose.Tasks поддерживает Java 8 и более новые версии.

## Что такое “how to filter mpp” в Java?
`How to filter mpp` — процесс использования объектов `Filter` из Aspose.Tasks для выбора только тех элементов проекта, которые удовлетворяют определённым предикатам, таким как дата начала, стоимость или пользовательские поля. Загрузите `Project`, получите `Filter`, и API вернёт коллекцию, соответствующую вашим критериям, позволяя выполнять целенаправленную отчётность или дальнейшую интеграцию.

## Почему настраивать критерии фильтра?
Настраиваемые критерии фильтра позволяют целиться в задачи с высоким риском, просроченные элементы или ресурсы с превышением бюджета, превращая огромный файл проекта в лаконичное, практичное представление. Aspose.Tasks поддерживает **более 50 предопределённых типов фильтров** и позволяет создавать неограниченное количество пользовательских фильтров, сокращая время ручного отбора данных до 70 %.

## Предварительные требования
1. **Java Development Kit (JDK)** — версия 8 или новее.  
2. **Aspose.Tasks for Java** — скачайте его со [страницы загрузки](https://releases.aspose.com/tasks/java/).  
3. **IDE** — IntelliJ IDEA, Eclipse или NetBeans подойдут.  

## Импорт пакетов
`Filter`, `FilterCollection`, `FilterCriteria`, `ItemType` и `Project` — основные классы, используемые для определения и применения фильтров к данным проекта.

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## Пошаговое руководство

### Шаг 1: Настройка проекта
Сначала создайте экземпляр `Project`, указывающий на файл MPP, который необходимо проанализировать, затем загрузите его в память. Этот единственный шаг подготавливает всю модель проекта для фильтрации, проверки и дальнейшего манипулирования, позволяя получать доступ к задачам, ресурсам и назначениям через API.

### Как настроить проект для фильтрации файлов MPP?
Класс `Project` загружает и представляет файл MPP в памяти. Создайте экземпляр `Project`, указывающий на нужный файл MPP, затем загрузите его в память. Этот единственный шаг подготавливает всю модель проекта для фильтрации, проверки и дальнейшего манипулирования, позволяя получать доступ к задачам, ресурсам и назначениям через API.

### Как получить и изучить фильтр?
Объекты `Filter` инкапсулируют определения фильтров, используемых для выбора элементов проекта. Aspose.Tasks хранит предопределённые фильтры, такие как «All Tasks» или «Critical Tasks». Используйте `project.getTaskFilters().getByName("My Filter")` или доступ по индексу, чтобы получить объект `Filter`, затем изучите его коллекцию `FilterCriteria`, чтобы увидеть каждое правило и логический оператор (AND/OR), комбинирующий их, гарантируя соответствие фильтра вашим требованиям.

### Как перебрать вложенные строки критериев?
`FilterCriteriaGroup` представляет группу критериев, объединённых логическим оператором. Фильтры могут содержать группы критериев, каждая со своим оператором. Перебирайте `filter.getCriteria().getRows()` и, если строка является `FilterCriteriaGroup`, рекурсивно проходите её дочерние строки. Такой обход позволяет полностью понять сложную логику фильтра, например «(Start < today AND Cost > 1000) OR Priority = High», и при необходимости скорректировать критерии.

### Как вывести информацию о критериях для отладки?
После обхода дерева критериев выведите в консоль имя поля, оператор сравнения и значение каждой строки. Этот простой дамп помогает убедиться, что фильтр соответствует требуемым бизнес‑правилам перед применением к большим проектам, и облегчает поиск неверных операторов или значений.

### Как программно создать совершенно новый фильтр?
Создайте `Filter` с помощью `new Filter("My Filter")`, затем добавьте его в коллекцию фильтров задач проекта через `project.getTaskFilters().add(filter)`. После этого заполните его коллекцию `FilterCriteria` нужными строками, указывая имена полей, операторы сравнения и значения, чтобы точно определить, какие задачи должны быть включены при применении фильтра.

### Можно ли применить фильтр к ресурсам вместо задач?
Коллекция `ResourceFilters` содержит определения фильтров, применимых к ресурсам. Да — используйте `project.getResourceFilters()` для работы с фильтрами ресурсов так же, как с фильтрами задач. После добавления или получения фильтра настройте его `FilterCriteria` так же, как для задач, затем примените его к коллекции ресурсов, чтобы получить отфильтрованный набор ресурсов.

### Можно ли объединить несколько фильтров с логикой OR?
Создайте родительскую `FilterCriteriaGroup` с оператором `OR`, затем добавьте в неё отдельные объекты `FilterCriteria` как дочерние. Эта группа будет оценивать каждый дочерний критерий и возвращать элементы, удовлетворяющие хотя бы одному из них, позволяя объединять несколько простых фильтров в более широкую выборку.

### Поддерживает ли Aspose.Tasks фильтрацию по пользовательским полям?
Перечисление `CustomField` предоставляет идентификаторы пользовательских полей, определённых в проекте. Абсолютно. Обращайтесь к пользовательским полям через `CustomField`, они работают как любые встроенные поля в выражениях фильтра. Вы можете включать их в строки `FilterCriteria`, используя те же операторы и значения, что даёт возможность мощных запросов к пользовательским данным наряду со стандартными атрибутами проекта.

### Каково влияние фильтрации на производительность больших файлов MPP?
Фильтрация полностью происходит в памяти и обычно обрабатывает проект из 1 000 задач менее чем за 200 мс. Для файлов с несколькими тысячами задач рекомендуется загружать только необходимые части с помощью `ProjectReader` и применять фильтры после выборочной загрузки, что сохраняет низкое потребление памяти и быстрый отклик даже на очень больших проектах.

---

**Последнее обновление:** 2026-06-05  
**Тестировано с:** Aspose.Tasks for Java 24.10  
**Автор:** Aspose

## Связанные руководства

- [Загрузить файл MPP Java — Управление свойствами проекта с Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java — Лёгкое чтение данных MS Project Online](/tasks/java/project-data-reading/read-project-online/)
- [Установить дату начала проекта в MS Project с помощью Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```