---
date: 2026-06-05
description: Aprenda cómo filtrar archivos MPP usando Aspose.Tasks para Java, personalice
  los criterios de filtro y filtre tareas por fecha para optimizar la gestión de proyectos.
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: Cómo filtrar archivos MPP usando Aspose.Tasks para Java
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
title: Cómo filtrar archivos MPP usando Aspose.Tasks para Java
url: /es/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo filtrar archivos MPP usando Aspose.Tasks para Java

## Introducción
Si estás trabajando con archivos de Microsoft Project (*.mpp*) en una aplicación Java, a menudo necesitarás **filtrar archivos MPP** para aislar las tareas, recursos o asignaciones que más importan. En este tutorial recorreremos **cómo filtrar mpp** archivos programáticamente con Aspose.Tasks para Java, te mostraremos cómo **personalizar criterios de filtro**, y demostraremos un escenario práctico de “filtrar tareas por fecha”. Al final tendrás un fragmento listo‑para‑usar que puedes insertar en cualquier proyecto Java.

## Respuestas rápidas
- **¿Qué significa “filter mpp”?** Significa extraer un subconjunto de datos del proyecto basado en condiciones definidas.  
- **¿Qué biblioteca maneja esto?** Aspose.Tasks for Java proporciona una API completa para crear y aplicar filtros.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Puedo filtrar tareas, recursos y asignaciones?** Sí – cada tipo de entidad tiene su propia colección de filtros.  
- **¿Se requiere Java 8 o superior?** Aspose.Tasks soporta Java 8 y versiones posteriores.

## Qué es “how to filter mpp” en Java?
`How to filter mpp` es el proceso de usar los objetos `Filter` de Aspose.Tasks para seleccionar solo aquellos elementos del proyecto que cumplen predicados específicos como fecha de inicio, costo o campos personalizados. Carga un `Project`, recupera un `Filter`, y la API devuelve una colección que coincide con tus criterios, permitiendo informes focalizados o integración posterior.

## Por qué personalizar criterios de filtro?
Los criterios de filtro personalizados te permiten apuntar a tareas de alto riesgo, elementos atrasados o recursos con sobrepresupuesto, convirtiendo un archivo de proyecto masivo en una vista concisa y accionable. Aspose.Tasks soporta **más de 50 tipos de filtro predefinidos** y te permite crear filtros personalizados ilimitados, reduciendo el tiempo de filtrado manual de datos hasta en un 70 %.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

1. **Java Development Kit (JDK)** – versión 8 o más reciente.  
2. **Aspose.Tasks for Java** – descárgalo desde la [download page](https://releases.aspose.com/tasks/java/).  
3. **Un IDE** – IntelliJ IDEA, Eclipse o NetBeans funcionarán bien.  

## Importar paquetes
`Filter`, `FilterCollection`, `FilterCriteria`, `ItemType` y `Project` son clases principales usadas para definir y aplicar filtros a los datos del proyecto.

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## Guía paso a paso

### Paso 1: Configurar el proyecto
Primero, crea una instancia de `Project` que apunte al archivo MPP que deseas analizar, luego cárgala en memoria. Este único paso prepara todo el modelo del proyecto para filtrado, validación y manipulación adicional, permitiéndote acceder a tareas, recursos y asignaciones a través de la API.

### ¿Cómo configuro el proyecto para filtrar archivos MPP?
La clase `Project` carga y representa un archivo MPP en memoria. Crea una instancia de `Project` que apunte al archivo MPP que deseas analizar, luego cárgala en memoria. Este único paso prepara todo el modelo del proyecto para filtrado, validación y manipulación adicional, permitiéndote acceder a tareas, recursos y asignaciones a través de la API.

### ¿Cómo puedo recuperar e inspeccionar un filtro?
Los objetos `Filter` encapsulan definiciones de filtro usadas para seleccionar elementos del proyecto. Aspose.Tasks almacena filtros predefinidos como “All Tasks” o “Critical Tasks”. Usa `project.getTaskFilters().getByName("My Filter")` o acceso por índice para obtener un objeto `Filter`, luego examina su colección `FilterCriteria` para ver cada regla y el operador lógico (AND/OR) que las combina, asegurando que el filtro coincida con tus requisitos.

### ¿Cómo iterar a través de filas de criterios anidadas?
`FilterCriteriaGroup` representa un grupo de criterios de filtro combinados con un operador lógico. Los filtros pueden contener grupos de criterios, cada uno con su propio operador. Recorre `filter.getCriteria().getRows()` y, para cualquier fila que sea un `FilterCriteriaGroup`, recursivamente itera sus filas hijas. Este recorrido te permite comprender completamente la lógica de filtro compleja como “(Start < today AND Cost > 1000) OR Priority = High”, y ajustar los criterios según sea necesario.

### ¿Cómo imprimir información de criterios para depuración?
Después de recorrer el árbol de criterios, muestra en la consola el nombre de campo, el operador de prueba y el valor de cada fila. Este volcado sencillo te ayuda a verificar que el filtro coincide con las reglas de negocio previstas antes de aplicarlo a proyectos grandes, y facilita detectar operadores o valores incorrectos.

### ¿Cómo crear un filtro completamente nuevo programáticamente?
Instancia un `Filter` con `new Filter("My Filter")`, luego añádelo a la colección de filtros de tareas del proyecto usando `project.getTaskFilters().add(filter)`. Después, rellena su colección `FilterCriteria` con las filas deseadas, especificando nombres de campo, operadores de prueba y valores para definir exactamente qué tareas deben incluirse cuando se aplique el filtro.

### ¿Puedo aplicar un filtro a recursos en lugar de tareas?
La colección `ResourceFilters` contiene definiciones de filtros aplicables a recursos. Sí – usa `project.getResourceFilters()` para trabajar con filtros específicos de recursos de la misma manera que con los filtros de tareas. Después de añadir o recuperar un filtro, configura su `FilterCriteria` igual que lo harías con tareas, luego aplícalo a la colección de recursos para obtener el conjunto filtrado de recursos.

### ¿Es posible combinar varios filtros con lógica OR?
Crea un `FilterCriteriaGroup` padre con su `Operation` establecida en `OR`, luego añade objetos `FilterCriteria` individuales como hijos. Este grupo evaluará cada criterio hijo y devolverá los elementos que cumplan cualquiera de ellos, permitiéndote combinar varios filtros simples en una selección más amplia.

### ¿Aspose.Tasks soporta filtrado en campos personalizados?
El enum `CustomField` proporciona identificadores para campos personalizados definidos en un proyecto. Absolutamente. Referencia los campos personalizados mediante el enum `CustomField`, y se comportan como cualquier campo incorporado en expresiones de filtro. Puedes incluirlos en filas `FilterCriteria`, usando los mismos operadores y valores, habilitando consultas potentes sobre datos definidos por el usuario junto con atributos estándar del proyecto.

### ¿Qué impacto de rendimiento tiene el filtrado en archivos MPP grandes?
El filtrado se ejecuta completamente en memoria y típicamente procesa un proyecto de 1 000 tareas en menos de 200 ms. Para archivos con varios miles de tareas, considera cargar solo las secciones necesarias usando `ProjectReader` y aplicar filtros después de la carga selectiva, lo que mantiene bajo el uso de memoria y mantiene tiempos de respuesta rápidos incluso en proyectos muy grandes.

**Última actualización:** 2026-06-05  
**Probado con:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose

## Tutoriales relacionados

- [Cargar archivo MPP Java - Administrar propiedades del proyecto con Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java - Lectura sin esfuerzo de datos de MS Project Online](/tasks/java/project-data-reading/read-project-online/)
- [Establecer fecha de inicio del proyecto en MS Project usando Aspose.Tasks para Java](/tasks/java/project-properties/write-project-info/)


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