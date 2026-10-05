---
date: 2026-10-05
description: Aprenda cómo crear un proyecto de prueba y calcular los días entre fechas
  usando Aspose.Tasks for Java, agregar un campo personalizado y manipular archivos
  MPP de manera eficiente.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Trabajar con fórmulas en Aspose.Tasks
og_description: Crear proyecto de prueba y calcular días entre fechas usando Aspose.Tasks
  for Java. Esta guía muestra cómo agregar un campo personalizado, establecer fechas
  límite de tareas y guardar el proyecto como un archivo MPP.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: Crear proyecto de prueba y calcular días entre fechas
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: Crear proyecto de prueba y calcular días entre fechas
url: /es/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear proyecto de prueba y calcular días entre fechas

En este tutorial **creará un proyecto de prueba** y **calculará días entre fechas** añadiendo un campo personalizado, definiendo un atributo extendido y aplicando una fórmula de Microsoft Project a través de la biblioteca Aspose.Tasks para Java. Ya sea que necesite generar cronogramas, calcular fechas límite o automatizar informes, Aspose.Tasks le permite manipular datos de Project programáticamente sin una instalación de escritorio, soportando más de 50 formatos de entrada y salida y manejando archivos de cientos de páginas en modo de eficiencia de memoria.

## Respuestas rápidas
- **¿Qué cubre el tutorial?** Muestra cómo crear un proyecto de prueba, definir un atributo extendido, establecer una fecha límite de tarea y usar una fórmula para calcular días entre fechas.  
- **¿Qué biblioteca se requiere?** Aspose.Tasks for Java (latest version).  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para uso en producción.  
- **¿Qué IDE puedo usar?** Cualquier IDE Java (IntelliJ IDEA, Eclipse, VS Code) que soporte JDK 8+.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para copiar el código y ejecutarlo.

## Qué es “calcular días entre fechas” en Aspose.Tasks?
En Aspose.Tasks, una fórmula es una cadena que puede referenciar campos de tareas y realizar cálculos. `[Deadline] - [Finish]` es la sintaxis de fórmula que Aspose.Tasks usa para devolver la diferencia numérica en días entre dos campos de fecha. El resultado se almacena como un valor numérico que representa días completos, que puede mostrar en un campo personalizado o usar en cálculos posteriores.

## Por qué usar Aspose.Tasks para calcular días entre fechas?
Aspose.Tasks ofrece **cobertura completa de la API** para cada propiedad de Project, Task y Resource, se ejecuta en Windows, Linux y macOS, y **no requiere Microsoft Project ni Office** instalados. El motor puede procesar proyectos con **más de 500 tareas** en menos de un segundo en hardware de servidor típico, lo que lo hace ideal para canalizaciones CI, contenedores Docker y procesamiento por lotes de alto volumen.

## Cómo establecer la fecha límite para una tarea
java.util.Calendar es una clase Java que representa un momento específico en el tiempo. Establece una fecha límite asignando un valor `java.util.Calendar` al campo `Tsk.DEADLINE` de una tarea. Después de crear la instancia Calendar, establezca su año, mes y día a la fecha límite deseada, luego llame a `task.set(Tsk.DEADLINE, calendar);`. La fecha límite se almacena en el archivo del proyecto y puede usarse en fórmulas como `[Deadline] - [Finish]`.

## Cómo definir un atributo extendido
Un atributo extendido es un campo personalizado que almacena el resultado de su fórmula. Lo crea una vez, le asigna un alias amigable y adjunta la expresión `[Deadline] - [Finish]` para que cada tarea pueda calcular automáticamente el intervalo. Créelo instanciando `ExtendedAttribute`, estableciendo su Alias, asignando la fórmula y añadiéndolo a la colección del proyecto.

## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:

- **Java Development Kit (JDK) 8+** – descargue desde el sitio web de Oracle o adopte OpenJDK.  
- **Aspose.Tasks for Java** – obtenga el último JAR de la [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) y agréguelo al classpath de su proyecto o a las dependencias Maven/Gradle.

## Importar paquetes
First, import the classes we’ll need:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Guía paso a paso

### Paso 1: Crear un proyecto de prueba con un campo personalizado
Comenzamos **creando un proyecto de prueba** y añadiendo un campo personalizado que más adelante contendrá el resultado de nuestra fórmula.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Consejo profesional:* `CreateTestProjectWithCustomField()` es un método auxiliar que construye un cronograma mínimo y registra un atributo extendido listo para la asignación de la fórmula.

### Paso 2: Definir un atributo extendido (añadir campo personalizado)
A continuación, **definimos un atributo extendido** – esencialmente el campo personalizado – y le asignamos un alias amigable. Aquí es donde implementamos la lógica de **añadir campo personalizado**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** hace que el campo sea legible en Project.  
- **Formula** calcula el número de días entre la fecha *Finish* de una tarea y su *Deadline* – el núcleo de *calcular días entre fechas*.

### Paso 3: Establecer la fecha límite para una tarea (añadir tarea de fecha límite y establecer fecha límite de la tarea)
Ahora **añadimos datos de tarea de fecha límite** estableciendo la propiedad *Deadline* en una tarea específica.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- La instancia `Calendar` define el momento exacto de la fecha límite.  
- `set(Tsk.DEADLINE, …)` **establece la fecha límite de la tarea** para la tarea seleccionada.

### Paso 4: Guardar el proyecto (manipular archivo Microsoft Project)
Finalmente, **manipulamos Microsoft Project** guardando los cambios en un archivo MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Puede abrir `SaveFile.mpp` en Microsoft Project para ver el campo personalizado, el resultado de la fórmula y la fecha límite reflejados en el cronograma.

## Problemas comunes y soluciones

| Problema | Solución |
|----------|----------|
| **Fórmula no se evalúa** | Asegúrese de que la cadena `Formula` del atributo use los nombres de campo correctos (p. ej., `[Deadline]`, `[Finish]`). |
| **Tarea no encontrada** | Verifique que el ID de la tarea (`1` en el ejemplo) exista; use `project.getRootTask().getChildren().size()` para depurar. |
| **Excepción de licencia** | Aplique una licencia válida de Aspose.Tasks antes de llamar a cualquier método de la API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Tasks con otros lenguajes de programación?**  
A: Sí, Aspose.Tasks ofrece APIs para .NET, Java y otras plataformas, lo que le permite manipular archivos Microsoft Project en el lenguaje que elija.

**Q: ¿Hay una prueba gratuita disponible para Aspose.Tasks?**  
A: Por supuesto. Descargue una prueba totalmente funcional desde la [Aspose.Tasks download page](https://releases.aspose.com/).

**Q: ¿Dónde puedo encontrar documentación detallada de Aspose.Tasks?**  
A: La documentación oficial está alojada en [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: ¿Cómo puedo obtener soporte para Aspose.Tasks?**  
A: Visite el [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) para hacer preguntas y compartir experiencias con la comunidad.

**Q: ¿Necesito una licencia temporal para la evaluación?**  
A: Una licencia temporal está disponible para pruebas a corto plazo; puede solicitar una en la [temporary license request page](https://purchase.aspose.com/temporary-license/).

---

**Última actualización:** 2026-10-05  
**Probado con:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo crear un archivo MPP – Crear y guardar proyecto vacío en formato MPP con Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Establecer la fecha de inicio del proyecto en MS Project usando Aspose.Tasks para Java](/tasks/java/project-properties/write-project-info/)
- [Cómo crear un atributo extendido en Java con Aspose.Tasks](/tasks/java/resource-management/extended-resource-attributes/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}